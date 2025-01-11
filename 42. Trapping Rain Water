class Solution:
    def trap(self, height: List[int]) -> int:
        i = 0
        left_max = height[0]
        sum = 0
        j = len(height) - 1
        right_max = height[j]
        while i < j:
            if left_max <= right_max:
                sum += left_max - height[i]
                i += 1
                left_max = max(left_max, height[i])
            else:
                sum += right_max - height[j]
                j -= 1
                right_max = max(right_max, height[j])
        return sum
