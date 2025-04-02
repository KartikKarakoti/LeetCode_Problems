class Solution:
    def buddyStrings(self, A: str, B: str) -> bool:
        # check same length
        if len(A) != len(B): return False
        
        # if strings are equal - check if there is a double to swap
        if A == B:
            return True if len(A) - len(set(A)) >= 1 else False
        
        # count differences between strings
        diff = []
        for i in range(len(A)):
            if A[i] != B[i]:
                diff.append(i)
                if len(diff) > 2: return False
                
        # not exactly two differences
        if len(diff) != 2: return False
        
        # check if can be swapped
        if A[diff[0]] == B[diff[1]] and A[diff[1]] == B[diff[0]]:
            return True
        
        return False
