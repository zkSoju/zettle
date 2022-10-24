202210232351
Status: 
Tags: #cypher #security #certora

- Invariant testing with Certora
	- Consider a function that transfers tokens from and to accounts
		- A possible invariant could be to ensure that 
			- `totalSupply = sum of all addresses balances`
		- If there exists bugs, given examples are shown that prove the invariant doesn't hold
		- If there are no bugs, then a proof is provided to show that invariant holds 
- Advantage of formal verification
	- Exhaustive
		- Finds easy to miss bugs
	- Concrete counter examples
		- Found bugs that are verifiable
	- Proofs of correctness
		- Hard to verify
		- May be misleading!
- **However!** Proofs may prove something completely different from what we intend
- Might lead to uploading code that may contain bugs
- Anatomy of a property
	- Precondition (constraint)
	- Operation
	- Post condition (assert)
- Wanted behavior results in starting state leading to one of the desired state
- A violation results in a starting state not resulting in a desired state (counter example)
- A statement is true if we cannot find a counter example
	- So in the case where there are no starting states (ex. I have no children) then we assume the statement (ex.  Children sleep better when drinking Columbian coffee) to be true
- **Vacuous rule**
	- Potential for bad proofs
	- We can assert a ridiculous rule like 0 > 1 and we cannot come up with any counter examples, so the statement will be true
	- If there is no starting states (precondition before operation doesn't allow it to start), then statement will be true

![[Pasted image 20221024000326.png]]
- Reachability check
	- We assert something absurd at the end like assert false to check that the rule created is vacuous
	- If the rule doesn't fail then it does not reach the end of the rule meaning the rule is vacuous
- **Tautology**
	- Not testing anything valuable (ex. testing a situation after the operation and not necessarily a state change)
	- Essentially not testing for a desired state so it's always true
	- We can remove all the preconditions and operation to see if it still passes
	- If it passes then there are no starting states and the rule does not depend on the operation
- Invariant
	- Always true and never changing
	- Proof by induction
		- Base case
		- Step
			- Assume invariant
			- Call function
			- Check if invariant is true
- Notional had a tautology in one of their specifications that led to a bug which was later reported by a whitehat
	- Statement was always true without any state change from operation meaning it did not test anything
	- Assertion was supposed to ensure two assets `active` and `bitmap` were never the same, but starting state without operation always resulted in desired state
- Certora now integrates automatic checking for bad proofs like tautologies and vacuous rules
- Takeaways
	- Writing specs are hard
	- Suspect don't trust
		- When prover reports bug it is usefl
		- When you get proof be suspciious
		- Check spec
		- Right specs can prevent bugs










---
# References
https://www.youtube.com/watch?v=U-4D7tWLNNo
