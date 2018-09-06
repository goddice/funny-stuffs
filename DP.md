# DP problem's *State*

**1. Coin Change Problem:** 

For `m` **distinct** coins `{c[1] ... c[m]}`. How many ways of making change for `n`? (Each coin have **infinite** amounts).

**Solution:** Define state `dp[i][j]` as the ways of using first `j` coins to make change for `i`. So the solution to our problem is to find `dp[n][m]`. Then we can construct the sub-problems by using specific number of the last coin. The state transition equation is: 

`dp[i][j] = dp[i][j-1] + dp[i-c[j]][j-1] + dp[i-2*c[j]][j-1] + ... = sum(dp[i-k*c[j]][j-1]) for k in [0, i/c[j]]`

Reference: [Positive solutions for a linear diophantine equation](https://math.stackexchange.com/questions/30638/count-the-number-of-positive-solutions-for-a-linear-diophantine-equation)
