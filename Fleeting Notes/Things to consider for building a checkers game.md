202209151159
Status: 
Tags: #cosmos

# Things to consider for building a checkers game

- Stored game object
	- Black player
	- Red player
	- Board proper
	- Player to play next
- How to store?
	- Game ID has to be deterministic so tx can be verificable, so instead of using something like a UUID() we should increment a value
- Clearing stale games
	- To advance a game we can play or reject
	- But what if we want to wager in the future we don't want a game to be stuck in limbo for forever
		- Consider game inactivity?
		- How do we do this without user input?
			- EndBlock
		- How do we find all games that have expired?
			- `findAll(game => game.deadline < now)` is O(n) which is expensive
			- FIFO data structure
				- When games are played they are moved to tail (recent)
				- When games haven't been played for awhile they rise to head
			- FIFO with extraction from anywhere? (doubly linked list)
- Incorporate logic into EndBlock
- Incorporating wager
	- Bank holds tokens in escrow and transfers in and out
	- You could implement burn and mint for wagers but supply will falsely fluctuate 
	- Define interface in types
	- Add interface to keeper struct and update constructor
	- Pass proper instance of Keeper to app.go
		




---
# References

