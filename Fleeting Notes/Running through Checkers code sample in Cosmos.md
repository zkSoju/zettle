202209121436
Status: 
Tags: #cosmos

# Running through Checkers code sample in Cosmos
- Initially the ABCI application has only 1 message type only capable of processing a tx as processing 4 `Int` move
	- Insufficient for multiple games
- We need to conform to SDK by placing messages into tx
	- Understanding messages required to build checkers
		- Issues with current implementation
			- `Int`s need to move from transaction into message to fit `sdk.Msg` interface
			- Process game for which the move is meant for
			- Distinguish move message from others
		- Required features
			- Add message type to create game that mentions other players
			- Generated ID for newly created game and return to user
		- Considerations
			- Allow user to reject game
			- Clear state of stale games

```go
type MsgCreateGame struct {
	Creator string
	Red string
	Black string
}

type MsgCreateGameResponse struct {
	IdValue string
}
```

- Declare how the messages are handled
	- How to serialize messages?
	- Handle message and place game in storage
	- Put hooks and callbacks
- `$ ignite scaffold message createGame red black --module checkers --response idValue`
	- Ignite removes boilerplate
		1. `GetSigner` which gets signer/`Creator` of message required by `sdk.Msg`
		2. `GetSignBytes` to ensure bytes to sign is deterministic
		3. Adds callback for new message type in module message handlers
		4. Empty shell for coding logic and response message







---
# References

