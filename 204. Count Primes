class Solution:
    def countPrimes(self, n: int) -> int:
        ## RC ##
        ## APPROACH :  Sieve of Eratosthenes ##
        
        #   1. Checking till sqrt(n) is enough for prime numbers i.e i*i < n
        #   2. mark all as prime.
        #   3. as you move along (i to i*i<n) mark every multiple until n as False.
        #   4. you donot need start from i for that we can start from i*i i.e j=i*i
        
		## TIME COMPLEXITY : O(NLogN) ##
		## SPACE COMPLEXITY : O(N) ##

        isPrime = [False,False] + [True] * (n-2)
        i = 2
        while( i*i < n ):               # Loop's ending condition is i * i < n instead of i < sqrt(n) to avoid repeatedly calling an expensive function sqrt().
            if(isPrime[i]):             # if not prime, it is some prime multiple.
                j = i*i                 # ex: we can mark off multiples of 5 starting at 5 × 5 = 25, because 5 × 2 = 10 was already marked off by multiple of 2, similarly 5 × 3 = 15 was already marked off by multiple of 3. Therefore, if the current number is p, we can always mark off multiples of p starting at p2, then in increments of p: p2 + p, p2 + 2p, ...
                while(j < n):
                    isPrime[j] = False
                    j += i
            i += 1
        return sum(isPrime)
