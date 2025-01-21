class Solution:
    def evalRPN(self, tokens: list[str]) -> int:                #  Ex:  tokens = ["4","13","5","/","+"]
        stack = []
                                                                #      t     operation    stack
        for t in tokens:                                        #    –––––   –––––––––    ––––––––– 
            if t not in '/+-*':                                 #      4                    [4]
                stack.append(int(t))                            #     13                    [4,13]
                                                                #      5                    [4,13,5]
            else:                                               #      /     13 / 5 = 2     [4,2]
                num = stack.pop()                               #      +      4 + 2 = 6     [6]
                if   t == '+': stack[-1]+=  num
                elif t == '-': stack[-1]-=  num
                elif t == '*': stack[-1]*=  num
                else         : stack[-1]= int(stack[-1]/num)    

        return stack[0]
