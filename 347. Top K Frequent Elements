class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        frequency = {}

        # count each element 
        for num in nums:
            frequency[num] = frequency.get(num, 0) + 1
        
        # intialize list of empty lists
        bucket = []
        for i in range(len(nums)+1):
            bucket.append([])

        # map each element count to corresponding index (bucket sort)
        for key, val in frequency.items():
            bucket[val].append(key)

        result = []
        for curList in bucket[::-1]:
            # skip empty lists
            if not curList:
                continue
            else:
                for num in curList:
                    if k > 0:
                        result.append(num)
                        k -= 1
                    else:
                        break

        return result
