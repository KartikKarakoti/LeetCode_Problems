class Solution:
    def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
        
        ans, c = [], Counter(candidates)

        def dfs(s, n, res):
            if s == target: return ans.append(res)
            if s > target or n < 1: return
            for i in range(0, c[n]+1): dfs(s+i*n, n-1, res+[n]*i)

        dfs(0, 50, [])
        return ans
