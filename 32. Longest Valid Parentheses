class Solution:
    def longestValidParentheses(self, s: str) -> int:
        n = len(s)
        arr = [0]*n
        stack = []

        for i in range(n):
            if s[i]=='(':
                stack.append(i)
            if s[i]==')' and stack:
                arr[stack.pop()]=1
                arr[i]=1
        
        ans = 0
        temp = 0
        for i in arr:
            if i==1:
                temp+=1
                ans = max(ans,temp)
            else:
                temp=0

        return ans
        
