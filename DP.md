# DP problem's *State*

**1. Coin Change Problem:** For `m` **distinct** coins `{c[0] ... c[m-1]}`. How many ways of making change for `n`? (Each coin have **infinite** amounts).

**Solution:** Define state `dp[i][j]` as the ways of using first `j` coins to make change for `i`. So the solution to our problem is to find `dp[n][m]`. The state transition equation is: 

`dp[i][j] = dp[i][j-1] + dp[i-c[j-1]][j-1] + dp[i-2*c[j-1]][j-1] + ... = sum(dp[i-k*c[j-1]][j-1] for k in [0, i/c[j-1]])`
