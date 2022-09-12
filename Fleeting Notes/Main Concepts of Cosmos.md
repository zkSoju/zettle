202209121331
Status: 
Tags: #cosmos

# Main Concepts of Cosmos

- Accounts
	- Components
		- PubKey - user or identity
		- PrivKey - sign message to prove it was signed by corresponding pubkey
	- Asymmetric cryptography 
		- System that employs pairs of keys
		- Authentication
			- Public key can verify private key pair
		- Encryption
			- Private key can decrypt messages signed by pk
		- Typically applied to small data blocks due to complexity
		- Length of keys is vital, longer the key the harder it is to brute force
		- Sign and verify
			- Derived signer from signature should match sender in payload
		- Accounts are usually not referenced by public keys but by addresses derived from public keys using ADR-28
			- AccAddress - users
			- ValAddress - validator operators
			- ConsAddress - validator nodes participating in consensus
		- Keyring stores and manages multiple accounts
- Transactions
	- Objects created by end users to trigger state change
	- Process
		- Decide message to put into transaction, usually done by wallet/ui
		- Generate tx using `TxBuilder`
		- Sign tx before validator includes in block
		- Broadcast tx to available interface
	- Transaction object
		- Implements `Tx`  interface
		- Methods
			- `GetMsg` which returns list of contained `sdk.Msg`
			- `ValidateBasic` includes lightweight test to ensure transactions are valid
				- Keep in mind there is a `ValidateBasic` func for `sdk.Msg` that just checks message validity
	- Messages (sdk.Msg)
		- Module specific objects that trigger state changes
		- Module messages are defined by adding methods to Protobuf `Msg` service and `MsgServer`
			- Each message is related to one service RPC defined in each module's `tx.proto` which routes it to method
		- Messages contain state transition logic, `TxBuilder`  and `Context` contain metadata and other relevant data
	- Signing Transactions
		- Must be signed by a message's `GetSigners`
		- How to sign?
			- `SIGN_MODE_DIRECT` - most used implementation of `Tx`
				- Once signed by all signers, `BodyBytes`, `AuthInfoBytes`, `Signatures` gathered into `TxRaw`
				- Then serialized and broadcasted to network
			- `SIGN_MODE_LEGACY_AMINO_JSON` - being deprecated
	- Generating Transactions
		- `TxBuilder`
			- `Msgs` - array of messages in tx
			- `GasLimit`
			- `Memo` - note or comment
			- `FeeAmount` - max users willing to pay in fees
			- `TimeoutHeight` - block height until which tx is valid
			- `Signatures` - array of signatures from all signers
		- There is `StdTxBuilder` for alternative signing method but is hidden to end users who prefer `TxConfig` 
			- TxConfig is appwide config for managing tx accessible from context
			- `txBuilder := txConfig.NewTxBuilder()` correctly uses the corresponding method to sign when txBuilder is populated 
	- Broadcasting the Tx
		- CLI
			- Bundles entire step into one command
		- gRPC
			- Cosmos SDK exposes Tx service which can be used to simulate, query, and broadcast tx
		- REST endpoints
			- Each gRPC has REST endpoint
			- ex. ``POST` `/cosmos/tx/v1beta1/txs``
- Messages
	- Messages and queries are the two primary obj handled by Cosmos SDK
	- Messages inform and can modify state
	- Queries inspect module state and read-only
	- Tx contains one or more messages
		- Tx serialized and confirmed by consensus (absolute finality)
		- Confirmed tx relayed to Cosmos SDK app (blockchain?)
			-  `BaseApp` uses `MsgServiceRouter` to route each message to approp module
			- `BaseApp` decodes tx and has its own `MsgService` that processes each received msg
	- MsgService
		- While you could create a novel MsgService, reccomended to create `Msg` service in `tx.proto` and define rpc method for each message type
		- Each method has one argument that defines message type and implements `sdk.Msg`
		- The following is the standard naming convention
	- Cosmos uses Protobuf defs to generate client and server
		- `MsgServer` defines server API for `Msg`
```go
// Msg defines the bank Msg service. 
service Msg { 
	// Send defines a method for sending coins from one account to another account. 
	rpc Send(MsgSend) returns (MsgSendResponse); 
	// MultiSend defines a method for sending coins from some accounts to other accounts. 
	rpc MultiSend(MsgMultiSend) returns (MsgMultiSendResponse); 
}
```

- Modules
	- SDK modules make up unique properties of each chain
	- "State machines within larger state machine"
	- Tx broadcasted -> Tendermint consensus confirms -> BaseApp decomposes messages and routes to appropriate module -> Module message handler routes to function that contains state altering logic


---
# References

