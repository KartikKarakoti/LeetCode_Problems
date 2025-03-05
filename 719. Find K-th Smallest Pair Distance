class Solution:
    def smallestDistancePair(self, nums: List[int], k: int) -> int:
        def count_pairs(mid):
            count, left = 0, 0
            for right, num in enumerate(nums):
                while num - nums[left] > mid:
                    left += 1
                count += right - left
            return count

        nums.sort()
        l, r = 0, max(nums)

        while l < r:
            m = l + ((r-l) // 2)
            if count_pairs(m) >= k:
                r = m
            else:
                l = m + 1
        return l
