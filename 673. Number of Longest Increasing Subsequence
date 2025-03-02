class Solution:
    def findNumberOfLIS(self, nums: List[int]) -> int:
        if not nums: return 0
        n = len(nums)
        m, dp, cnt = 0, [1] * n, [1] * n
        for i in range(n):
            for j in range(i):
                if nums[j] < nums[i]:
                    if dp[i] < dp[j]+1: dp[i], cnt[i] = dp[j]+1, cnt[j]
                    elif dp[i] == dp[j]+1: cnt[i] += cnt[j]
            m = max(m, dp[i])                        
        return sum(c for l, c in zip(dp, cnt) if l == m)
