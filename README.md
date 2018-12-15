# Perfect-Squares

For the dynamic programming solution, we will create an array `dp[]` and populate that array with all the solutions from `0,1,...,n`.

To calculate those solutions, we find the minimum in `dp[]` of all possible squares <= the target number and add 1 and store that in `dp[n]`.
The first 4 are pretty much our base cases.
`dp[0] = 0`
`dp[1] = 1`
`dp[2] = 2`
`dp[3] = 3`

**Examples:**

To find the solution to `n = 5`, we will start calculating at `n = 4`.  
`dp[4] = min(dp[4-1*1] + 1, dp[4-2*2] + 1)` since `1` and `2` are the only squares `<= 4`  
`dp[4] = min(dp[3] + 1, dp[0] + 1)`  
`dp[4] = min(4, 1) = 1`  

Now that we have `dp[4]`, we can start on `dp[5]`.  
`dp[5] = min(dp[5-1*1] + 1, dp[5-2*2] + 1)` since `1` and `2` are the only squares `<= 5`  
`dp[5] = min(dp[4] + 1, dp[1] + 1)`  
`dp[5] = min(4, 2) = 2`  

For `dp[13]`:  
`dp[13] = min(dp[13-1*1] + 1, dp[13-2*2] + 1, dp[13-3*3] + 1)` since `1`, `2`, and `3` are the squares `<= 13`  
`dp[13] = min(dp[12] + 1, dp[9] + 1, dp[4] + 1)`  
`dp[13] = min(4, 3, 2) = 2`  
