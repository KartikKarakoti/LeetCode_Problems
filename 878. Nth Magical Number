class Solution:
    def nthMagicalNumber(self, n, a, b):
        mod = 10**9 + 7

        lcm = math.lcm(a, b)
        l = min(a, b)
        r = n * min(a, b)


        while l < r:

            m = l + r >> 1

            aa = m//a
            bb = m//b
            ab = m//lcm

             
            if n <= (aa + bb - ab): # a U b = a + b - ab   inclusion exclusion
                r = m
            else:
                l = m + 1
        
        return l % mod
