class Solution:
    def checkInclusion(self, p: str, s: str) -> bool:
        if len(p) > len(s): return False
        f1, f2 = [0] * 26, [0] * 26
        for i in range(len(p)):
            f1[ord(p[i]) - ord('a')] += 1
            f2[ord(s[i]) - ord('a')] += 1
        for i in range(len(p), len(s)):
            if f1 == f2: return True
            f2[ord(s[i]) - ord('a')] += 1
            f2[ord(s[i - len(p)]) - ord('a')] -= 1
        return f1 == f2
