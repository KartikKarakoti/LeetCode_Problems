class Solution:
    def checkPerfectNumber(self, num: int) -> bool:
        if num == 1:
            return False
        res = 1
        for i in range(2,int(num**0.5)+1):
            if num%i == 0:
                res += i + num//i
        return res == num
