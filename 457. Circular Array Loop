class Solution:
    def circularArrayLoop(self, nums: List[int]) -> bool:
        n = len(nums)
        if n == 1:
            return False

        visited = set()
        for i in range(n):
            if i not in visited:
                cycleset = set()
                while True:
                    if i in cycleset:
                        return True
                    visited.add(i)
                    cycleset.add(i)
                    prev, i = i, (i + nums[i]) % n

                    if prev == i:
                        break

                    if nums[prev] > 0 != nums[i] < 0:
                        break

        return False
                

        
