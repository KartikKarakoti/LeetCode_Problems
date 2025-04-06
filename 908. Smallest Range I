class Solution:
    def smallestRangeI(self, nums: List[int], k: int) -> int:
        left = min(nums) + k
        right = max(max(nums) - k, left)

        return right - left
