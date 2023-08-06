# Pumping Lemma for Context-free Languages

Let $L$ be a context-free language (see [[Formal Languages and Grammar]]), there is some $n \geq 1$ such that for all strings $w \in L$ such that $|w| \geq n$, there exists strings $x, y, z, u$ and $v$ such that $w = xyzuv$ and:

1. $|yzu| \leq n$
2. $y \neq \, \lambda \, or\, u\, \neq \lambda$
3. $xy^izu^iv \in L \, for \, all \, i \geq \lambda$

## Context-free

- If $L$ is context-free, it satisfies Pumping Lemma
- If $L$ does not satisfy Pumping Lemma it is not context-free

## Proving $L$ is not context-free

1. Assume $L$ is context-free
2. Apply [[Pumping Lemma]]
3. Choose string $w \in L$
4. Use $|yzu| \leq n$ to get information on $y$ and $u$
5. Choose $i$ such that $xy^izu^iv \notin L$
	1. $i = 2$ normally works apparently
6. Contradiction therefore $L$ is not context-free