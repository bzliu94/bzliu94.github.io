---
title: Gambles
---

# Gambles

## Han 2020 version 16

Section 2.1 talks about an approach using index indices that takes time in O(n ^ 2 * log(n) ^ log(n)).

Section 2.2 talks about an approach that collects coefficients that takes time in O(n ^ 2 * log(n) ^ log(n) (assuming we avoid "mixed power problem") by spacing out terms more.

Section 3.1 talks about an approach that ends up not working because we assume we do not push a\_i * b\_j  inside lines 2 through 5; once we do, if e >= 2 we just get r\_1 ^ e instead of r\_e. It's not clear what the reason is for introducing an expression  that is divisible by x + 1. If we do not push a\_i * b\_j inside lines 2 through 5, then a query will take big-omega of n ^ 2 time, which is clearly too much.

Section 3.2 explains how to cancel terms.

Section 3.3 talks about an approach that also has issue regarding assuming we do not push a\_i * b\_j in (this time for lines 2 through 5 in a different equation) s.t. we then for e >= 2 get r\_1 ^ e instead of r\_e. The effect again is that to get r\_e we need big-omega of n ^ 2 time for a query. Also, it's not clear why we know getting rid of dividing by x + 1 makes it safer to keep different-sign terms separate when aiming to resolve for r\_e using coefficients. Also, it's not clear why we need to treat polynomials associated with left or right asymmetrically and how we come up with a replacement formula and why we take modulo using a different modulus. Presumably we are covering whole truth table for i, j, k\_1, k\_2, but we are not following the specific proofs; in other words, when looking for a mistake, it's hard to know if these cases on their own are enough. How is equation 24 equal to equation 25 (s.t. latter uses alternating signs)?

We have attempted to implement approaches from sections 3.1 and 3.3. For the former, we choose the approach that is more correct and slower (but not as slow as big-omega of n ^ 2 per query) and get correct result when e == 1 and we get r\_1 ^ e for e >= 2. For approach from section 3.3 (s.t. we push a\_i and b\_j into lines 2 through 5 and so avoid big-omega of n ^ 2 time per query), we get wrong results for all e values (i.e. for e == 1 and e >= 2). Getting wrong answers for section 3.3 for e >= 2 is explained by us solving instead for r\_1 ^ e for e >= 2 again; however, something else must be happening as we have no good reason currently for explaining why we are unable to solve for r\_1 accurately using approach from section 3.3. Given how many steps in section 3.3 that come without much explanation, there is certainly room for misunderstanding on our part and it may be understandable that we find it difficult to explain away the error.

Finally, section four discusses complexity. We claim the given recursive approach is somewhat incorrect. We have to visit each node in call tree for a query using at least time in O(1), so time must be at least in O(log(n) ^ 3) for each query. Even if we are constructing a constant number of pairs of polynomials for a query, we would need to filter out mismatched pairs in the product and spend time that matches number of nodes in call tree at least. This suggests our time is loosely in O(log(n) ^ 4) because we have more than two levels in call tree, which is in contrast to their time, which is loosely in O(log(n) ^ 3).

The most interesting part of their approach is using a Vandermonde system to recover how many contributions we have scaled by log(n).

When implementing, we for some arbitrary input vector pair get via where we raise to e once with time for a query not in big-omega of n ^ 2 the values 400 and 160000 (s.t. the latter is the square of the former) instead of 400 and 610.


