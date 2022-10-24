202208311226
Status: 
Tags: #cosmos

# Main concepts when building a Cosmos blockchain

- Accounts
	- Pair of keys
		- `PubKey` - unique id for user that is safe to disclose
		- `PrivKey` - proves to others message was signed by someone using privkey corresponding to public
	- Private keys can be used to sign messages so that receiver can verify the signature matches public key of sender they expect
	- Keys stored in object called **keyring**
		- Sender in payload must match sender and the derived sender from associated signature
	- Address
		- `AccAddress` - users
		- `ValAddress` - validator operators
		- `ConsAddress` - validator nodes participating in consensus






---
# References

