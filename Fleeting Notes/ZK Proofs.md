202205281802
Status: #fleeting
Tags: #zkrollup 

# ZK Proofs
You want to prove that you know an `x` such that `f(x)=y` **without revealing x.** In reference to the former example, you want to prove that the database does not include the politician without revealing the database.

Requirements to a ZK Proof:

-   Encoding as a polynomail problem
-   Succinctness by random sampling (acquire non-linear property - proof is smaller than size of data set)
-   Zero knowledge (privacy)

**Example #1** You want to prove that you got a particular value after a certain number of steps.

1.  "This program reaches value x=42 after 1000 steps"
    1.  `x=1`
    2.  `while true { x = x^2 - 5x + 7 }`
2.  Naive verification
    1.  Check for each i < 999 that x - x - 6x + 7 = 0
3.  Problem? Prover can cheat at any point x to reach faulty answer
    1.  Solution: add redundancy by encoding execution trace with ECC, so that errors in one place would snowball into many other errors

**Example #2**

1.  You want to prove that you have a polynomial such that `1 <= P(x) <= 9` for all `1 <= x <= 1,000,000`
    1.  Computing all 1,000,000 would result in a certificate size equal to the data set size, which violates non-linear property
2.  Let C(x) be a polynomial such that C(x) = 0 only if `1 <= x <= 9`
    1.  C(x) = (x-1)(x-2)(x-3)(x-4)...(x-9)
3.  Now the problem becomes prove you know P(x) such that C(P(x)) = 0 for 1 <= x <= 1000000

`Theorem: Any polynomial that equals zero at all x within a range is a multiple of Z(x)

Z(x) = (x-1)(x-2)....(x-100000)`

1.  Now the problem becomes prove you know P(x) and D(x) such that C(P(x)) = Z(x)D(x)
2.  Commit all values of P(x) up to 1,000,000,000 (more values than before) to a merkle tree. Polynomials amplify errors that become more prevalant when computing more data.
3.  However, there is a possibility that a valid P(x) was provided but not the exact P(x)
    1.  Low Degree Testing

## **zk-SNARKS**

1.  **Succint** - proof is small and easy to verify even if context is complex
2.  **Non-interactive** - no need for back and forth interaction between verifier and prover
3.  **Argument** - cryptography and non-determinism, not traditional formal proofs
4.  **of Knowledge** - prover knows the subject he/she is proving not just proving a proof of it's existence







---
# References
<iframe width="560" height="315" src="https://www.youtube.com/embed/kk1Oo42TVQk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
