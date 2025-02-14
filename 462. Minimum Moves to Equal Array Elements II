class Solution:
    def minMoves2(self, nums: List[int]) -> int:
        nums.sort()
        count = 0
        median = nums[len(nums) // 2]
        for num in nums:
            count += abs(median - num)
        return count
