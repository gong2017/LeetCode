### 931.Minimum-Falling-Path-Sum

最传统的走迷宫的DP题，是问从左上角走到右下角的最小权和路径，每次走只能向右或者向下。此题本质上一样，是问从第一行到最后一行的最小权和路径，每次只能朝是那个方向（左下，正下，右下）。

因此状态转移方程也很类似：
```
dp[i][j] = min (dp[i-1][j-1],dp[i-1][j],dp[i-1][j+1]) + A[i][j];
```
相比与传统的走迷宫的DP，此题不确定的是“最小权和路径”的结束点的具体位置。所以最后的答案是在最后一行的```dp[m-1][j]```中扫描一个，找最小的那个。注意，我们不关心第一行的出发点的位置，因为对于任何的dp[m-1][j]都隐含了一个确定的出发点。
