---
tags:
  - math
  - dsa
---
Also known as Bachet's conjecture.

States that every natural number can be represented as a sum of four non-negative integer squares.

$$p=a^{2}+b^{2}+c^{2}+d^{2}$$

Proven by Joseph Louis Lagrange in 1770.

Adrien-Marie Legendre extended the theorem ~27 years later in 1797-8 with [[Legendre's three-square theorem]].

## Use cases

[Solving Perfect Squares with both the four-square and three-square theorem.](https://leetcode.com/problems/perfect-squares/solutions/71532/O(sqrt(n\))-about-0.034-ms-(and-0.018-ms)/) (or see [Approach 5 in the editorial](https://leetcode.com/problems/perfect-squares/editorial/))

- According to this theorem, the maximum number of squares is 4.
- According to [[Legendre's three-square theorem]], if `n` is not of the form $n = 4^{a}(8b + 7)$, a natural number can be represented as the sum of three square of integers, i.e. $n = x^2 + y^2 + z^2$.
- If it fits the form above, we short-circuit the function and return `4`.
- If not, we go on to check if `n` is a square in itself or contains 2 squares.
- If not, the only answer left is 3.

```python
def isSquare(self, n: int) -> bool:
	sq = int(math.sqrt(n))
	return sq*sq == n

def numSquares(self, n: int) -> int:
	# four-square and three-square theorems
	while (n & 3) == 0:
		n >>= 2      # reducing the 4^k factor from number
	if (n & 7) == 7: # mod 8
		return 4

	if self.isSquare(n):
		return 1
	# check if the number can be decomposed into sum of two squares
	for i in range(1, int(n**(0.5)) + 1):
		if self.isSquare(n - i*i):
			return 2
	# bottom case from the three-square theorem
	return 3
```

