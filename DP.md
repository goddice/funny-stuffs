# DP problem's *State*

**1. Coin Change Problem:** For m **distinct** coins { c[0] ... c[m-1] }. How many ways of making change for n? (Each coin have **infinite** amounts).

**Solution:** Define state dp[i][j] as the ways of using first j coins to make change for i. So the solution to our problem is to find dp[n][m].

