202209141628
Status: 
Tags:

# Technical process of building a Cosmos chain
1. `ignite scaffold chain github.com/alice/checkers`
2. `ignite chain serve`
3. `ignite scaffold message createPost title body`

Storing counter in an object in storage
1. `ignite scaffold single systemInfo nextId:uint --module checkers --no-message`
	1. Specify uint otherwise default is string
	2. `--no-message` indicates you don't want Ignite to create msg and associated service because in this case you want the app and not players modifying

Create a map type to map from ID
1. `ignite scaffold map storedGame board turn black red --index index --module checkers --no-message`
	1. Name the type storedGame
	2. board, turn, black, red are strings
	3. index is default name because you can't select id when scaffolding in Ignite CLI
	4. no message prevents creation of type with a simple message (we can create properly constructed ones to do this though)

Narrow store search using the key just created and then get store of a game at an index
1. `store := prefix.NewStore(ctx.KVStore(k.storeKey), types.KeyPrefix(types.StoredGameKeyPrefix))`
2. `b := store.Get(types.StoredGameKey( index, ))`

Make systemInfo for genesis should not be nil as `genesis.go` suggests
1. Set `SystemInfo systemInfo = 2 [(gogoproto.nullable) = false];` in genesis proto
2. `ignite generate proto-go`
3. Change `genesis.go` to SystemInfo to  `SystemInfo: SystemInfo{ NextId: uint64(DefaultIndex), },

Generated protobuf services which define how to access objects
Generated request and response types and how to serialize for querying
New storage getters and setters functions in keeper
Getters for storage as they come from gRPC

Query values in store
1. `checkersd query checkers show-system-info`
2. `checkersd query checkers list-stored-game`

Create custom messages to create games, since we set `no-message` , user should not be able to specify gameId or the board
1. `ignite scaffold message createGame black red --module checkers --response gameIndex`
- Creates a protobuf object in tx
- Registers createGame as a message type with two serialization methods
- Creates new function to gRPC interface to receive all tx messages for module

export alice=$(checkersd keys show alice -a) 
export bob=$(checkersd keys show bob -a)

$ checkersd tx checkers create-game $alice $bob --from $alice --gas auto

We have now created a message but we have not specified to the application what it should do when receiving the message

Test create game but we need to initialize keeper with default genesis (better to keep initialization closest to test)

Create a message to join and process a move and then return a captured piece (if any) or winner (if any)
1. `ignite scaffold message playMove gameIndex fromX:uint fromY:uint toX:uint toY:uint --module checkers --response capturedX:int,capturedY:int,winner`
Fill out logic in msg_server_play_move and create unit tests

Create events to notify outside world of state changes
- Define new keys in keys.go
- Emit event using EventManager

keeper uses ctx
msgServer uses context

go test github.com/zksoju/checkers/x/checkers/keeper

We can use `EndBlock` which is part of the ABCI to terminate games using a deadline 

Frontend
1. `cd vue`
2. `npm install `
3. `npm run dev`





---
# References

