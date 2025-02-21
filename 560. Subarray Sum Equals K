class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int: 
        dic = defaultdict(int) # sum 0 occurs once
        dic[0] = 1
        runningSum = 0
        count = 0
        for num in nums:
            runningSum += num
            difference = runningSum - k
            if difference in dic:
                count += dic[difference]
            dic[runningSum] += 1
        return count
            
