class Solution:
    def minPatches(self, nums: List[int], n: int) -> int:
        count = 0
        missing = 1
        i = 0
        
        while missing <= n:
            if i < len(nums) and nums[i] <= missing:
                missing += nums[i]
                i += 1
            else:
                missing += missing
                count += 1
        
        return count
