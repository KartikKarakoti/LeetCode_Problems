class Solution:
    def minEatingSpeed(self, piles: List[int], h: int) -> int:
        l, r = 1, max(piles)
        
        def isSufficientSpeed(cnt):
            return sum(ceil(i/cnt) for i in piles) <= h

        while l < r:
            m = (l + r)//2
            if isSufficientSpeed(m):
                r = m
            else:
                l = m + 1
                
        return l
