# Pumping Lemma

Key concept: There must be a cycle in the first n processes. This is used for proving a language is not regular.

We use a contradiction proof to disprove this, with this knowledge move on to the following notes.

Alright mate, here we go again, let $L$ be a regular language. There is also a Pumping Lemma for context-free languages.

There then exists a constant $n$ such that for every string $w$ in $L$: $|w| \geq n$ 

We can then break $w$ into three strings, $w = xyz$, such that -
- $|y| > 0$
- $|xy| \leq n$
- For all $k \geq 0$, the string $xy^kz$ is also in $L$

## Regularity

- If $L$ is regular, it satisfies Pumping Lemma
- If $L$ does not satisfy Pumping Lemma, it is non-regular

## Proving $L$ Is Not Regular

1. First assume $L$ is regular
2. Therefore, Pumping Lemma should hold for $L$
3. Use the Pumping Lemma to obtain a [[Proofs]] by contradiction
	1. Select $w$ such that $|w| \geq n$ and $w \in L$
	2. Select $y$ such that $|y| \geq 1$
	3. Select $x$ such that $|xy| \leq c$
	4. Assign remaining string to $z$
	5. Select $k$ such that the resulting string is not in $L$

Therefore, $L$ is not regular.

## [[Pumping Lemma for Context-free Languages]]


See also:
- [[Formal Languages and Grammar]]
- 