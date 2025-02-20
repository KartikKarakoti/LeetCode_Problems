class Solution:
    def reverseStr(self, s: str, k: int) -> str:
        c = 0
        while c*k < len(s):
            s = s[:c*k] + s[c*k:c*k+k][::-1] + s[c*k+k:]
            c+=2
        return s
