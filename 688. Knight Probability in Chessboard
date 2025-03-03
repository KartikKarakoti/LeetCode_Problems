class Solution:
    def knightProbability(self, n: int, k: int, row: int, column: int) -> float:
        @lru_cache(None)
        def dp(cur_r,cur_c,k):
            if k==0:
                return 1

            else:
                ans=0
                for r,c in moves:
                    now_r=cur_r+r
                    now_c=cur_c+c
                    if 0<=now_r<=n-1 and 0<=now_c<=n-1:
                        ans+=dp(now_r,now_c,k-1)

                return ans

        if k==0:
            return 1

        moves=[[1,2],[2,1],[1,-2],[2,-1],[-1,2],[-2,1],[-1,-2],[-2,-1]]
        return dp(row,column,k)/8**k            
