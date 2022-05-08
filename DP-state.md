# DP problem's *State*

**1. 零钱问题:** 

有`m`种**不同的**硬币`{c[1] ... c[m]}`，每种硬币数量无限。求凑出金额为`n`的方法数。

**思路：**
定义状态`dp[i][j]`为使用前`j`个硬币凑出金额`i`的方法数。则状态转移方程为: 

`dp[i][j] = dp[i][j-1] + dp[i-c[j]][j-1] + dp[i-2*c[j]][j-1] + ... = sum(dp[i-k*c[j]][j-1]) for k in [0, i/c[j]]`

Reference: [Positive solutions for a linear diophantine equation](https://math.stackexchange.com/questions/30638/count-the-number-of-positive-solutions-for-a-linear-diophantine-equation#answer-929664)

**2. 最佳加法表达式**

有一个由`1...9`组成的数字串`s`，将`m`个加号插入到这个数字串，在各种可能形成的表达式中，求值最小的表达式的值。

**思路：**
定义状态`dp[i][j]`为在前`i`个字符中添加`j`个加号能够得到的最大表达式的值，那么其满足以下状态转移方程：

`if j = 0`

`   dp[i][j] = to_number(s[1...i])`

`else if j >= i`

`   dp[i][j] = Infinity (j >= i)`

`else`

`   dp[i][j] = min{dp[k][j-1] + to_number(s[k+1...i]) for k in [j, i-1]}`