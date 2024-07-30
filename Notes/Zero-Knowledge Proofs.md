A proof in which one party (Prover) can prove to another party (Verifier) that a statement is true without conveying any extra information except that the statement is true.

Pretty wild, there's one of those Wired Expert Explains vidss on this shit.

A zero-knowledge proof of some statement must satisfy three properties:

1.  **Completeness**: if the statement is true, an honest verifier (that is, one following the protocol properly) will be convinced of this fact by an honest prover.
2.  **Soundness**: if the statement is false, no cheating prover can convince an honest verifier that it is true, except with some small probability.
3.  **Zero-knowledge**: if the statement is true, no verifier learns anything other than the fact that the statement is true. In other words, just knowing the statement (not the secret) is sufficient to imagine a scenario showing that the prover knows the secret. This is formalized by showing that every verifier has some _simulator_ that, given only the statement to be proved (and no access to the prover), can produce a transcript that "looks like" an interaction between an honest prover and the verifier in question.


See also:
- [[Proofs]]
- [[Cryptography]]