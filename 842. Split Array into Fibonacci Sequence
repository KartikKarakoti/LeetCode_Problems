class Solution:
    def splitIntoFibonacci(self, num: str) -> List[int]:
        n=len(num)


        def f(pos,res,n,fin):
            if pos>=n:
                if len(res)>2:
                    fin.append(res.copy())# ADD TO RESULT ARRAY  IF IT CONTAINS ATLEAST 3 ELEMENTS
                return

            cur=""
            for i in range(pos,n):
                cur+=num[i]

                if cur[0]=="0" and i!=pos:
                    continue # CHECK IF FIRST  NUMBER OF MORE THAN ONE DIGIT NUMBER IS EQUALS TO ZERO OR NOT 

                if int(cur)>(2**31):
                    break # 

                if len(res)>=2:
                    if int(cur)==int(res[-1])+int(res[-2]):
                        res.append(cur)
                        f(i+1,res,n,fin)
                        res.pop()#checking each splitted num is equals to previous two numbers

                else:
                    res.append(cur)
                    f(i+1,res,n,fin)
                    res.pop() # IF CURRENT ARRAYS HAVE LESS THAN TWO NUMBERS WE CAN ADD TO ARRAY
        fin,res=[],[]
        f(0,res,n,fin)
        ans=[]
        if len(fin)==0 or fin==[]:
            return []
        for i in fin[0]:
            ans.append(int(i))
        return ans
            
