class Solution:
	def scoreOfParentheses(self, S: str) -> int:
		return self.helper(S,0,len(S)-1)        
	def helper(self,S,l,r):
		if r-l==1:
			return 1
		count=0
		for i in range(l,r):
			if S[i]=='(':
				count+=1
			if S[i]==')':
				count-=1
			if count==0:
				return self.helper(S,l,i)+self.helper(S,i+1,r)
		return 2*self.helper(S,l+1,r-1)
