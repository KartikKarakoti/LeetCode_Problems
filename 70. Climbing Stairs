class Solution:
    def climbStairs(self, n: int) -> int:
        dp=[-1]*(n+2)
        def solve(i):
            if i==0 or i==1:
                return 1
            if dp[i]!=-1:
                return dp[i]
            left=solve(i-1)
            right=solve(i-2)
            dp[i]=left+right
            return left+right
        return solve(n)
