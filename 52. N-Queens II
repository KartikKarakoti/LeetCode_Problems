class Solution:
    def totalNQueens(self, n: int) -> int:
        res,col,pos,neg=0,set(),set(),set()
        def backtracking(r):
            if n==r:
                nonlocal res
                res+=1
            for c in range(n):
                if c in col or (c+r) in pos or (r-c) in neg:
                    continue
                col.add(c)
                pos.add(c+r)
                neg.add(r-c)
                backtracking(r+1)
                col.remove(c)
                pos.remove(c+r)
                neg.remove(r-c)
                
        backtracking(0)

        return res
