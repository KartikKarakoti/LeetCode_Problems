from math import inf

class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        
        p = 0
        
        first_neg = 0
        first_neg_excluded = False
        
        p_max = -inf
        
        for x in nums:
            
            if x == 0:
                p = 0
                first_neg = 0
                first_neg_excluded = False
            
            elif x > 0:
                
                if p == 0:
                    p = x
                    
                else:
                    p *= x
                
                    if p < 0:
                        p //= first_neg
                        first_neg_excluded = True
            
            else:
                p = p * x if p != 0 else x
                
                if p < 0:
                
                    if first_neg == 0:
                        first_neg = p
                    
                    elif first_neg_excluded:
                        p *= first_neg
                        first_neg_excluded = False
                    
                    else:
                        p //= first_neg
                        first_neg_excluded = True
            
            if p > p_max:
                p_max = p
        
        return p_max
