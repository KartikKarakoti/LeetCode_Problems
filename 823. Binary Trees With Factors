class Solution:
    def numFactoredBinaryTrees(self, arr: List[int]) -> int:
        arr.sort()
        ans = 0
        dp = {}
        for n in arr:
            temp = 1
            for k in dp.keys():
                if n%k==0 and n//k in dp:
                    temp+=dp[k]*dp[n//k]
            ans+= temp
            dp[n] = temp
        return ans%(10**9+7)
        
