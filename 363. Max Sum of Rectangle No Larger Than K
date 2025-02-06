class Solution:
    def maxSumSubmatrix(self, matrix: List[List[int]], k: int) -> int:
        ans = float("-inf")
        m, n = len(matrix), len(matrix[0])
        for i in range(n):
            lstSum = [0] * m
            for j in range(i, n):
                currSum = 0
                curlstSum = [0]
                for t in range(m):
                    lstSum[t] += matrix[t][j]
                    currSum += lstSum[t]
                    pos = bisect_left(curlstSum, currSum - k)
                    if pos < len(curlstSum):
                        if curlstSum[pos] == currSum - k:
                            return k
                        else:
                            ans = max(ans, currSum - curlstSum[pos])
                    insort(curlstSum, currSum)
        return ans
