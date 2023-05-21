# [[Algorithms]] - Analysis Simplifying Rules

Handy to have, but not necessary to memorise. Just get the context.

1.   If f(n) is in O(g(n)) and g(n) is in O(h(n)), then f(n) is in O(h(n));
2.  If f(n) is in O(kg(n)) for any constant k>0, then f(n) is in O(g(n));
3.  If f1(n) is in O(g1(n)) and f2(n) is in O(g2(n)), then f1(n)+f2(n) is in O(max(g1(n),g2(n))); and
4.  If f1(n) is in O(g1(n)) and f2(n) is in O(g2(n)), then f1(n)f2(n) is in O(g1(n)g2(n)).