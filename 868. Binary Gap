class Solution:
    def binaryGap(self, n: int) -> int:
        binary = list(bin(n)[2:])
        indicies=[]
        for i in range(len(binary)):
            if (binary[i]=='1'):
                indicies.append(i)
        distance=0
        for i in range(1,len(indicies)):
            if (indicies[i]-indicies[i-1]>distance):
                distance=indicies[i]-indicies[i-1]
        return distance
