class Solution:
    def totalHammingDistance(self, nums: List[int]) -> int:
        ans=0
        for i in range(32):
            cnt=0
            for j in range(len(nums)):
                cnt+=(nums[j]>>i&1)
            ans+=(len(nums)-cnt)*cnt
        return ans
