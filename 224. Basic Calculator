class Solution:
    def calculate(self, s):
        def evaluate(i):
            res, digit, sign = 0, 0, 1
            
            while i < len(s):
                if s[i].isdigit():
                    digit = digit * 10 + int(s[i])
                elif s[i] in '+-':
                    res += digit * sign
                    digit = 0
                    sign = 1 if s[i] == '+' else -1
                elif s[i] == '(':
                    subres, i = evaluate(i+1)
                    res += sign * subres
                elif s[i] == ')':
                    res += digit * sign
                    return res, i
                i += 1

            return res + digit * sign
        
        return evaluate(0)
