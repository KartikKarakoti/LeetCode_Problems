class Solution:
    def racecar(self, target: int) -> int:
        q = deque()
        q.append((0,1,0)) #curr pos, curr speed, number of moves
        
        while q:
            cp,cs,nm = q.popleft()
            
            if cp==target:
                return nm
            
            #every pos we have 2 choice
            #A or R
            q.append((cp+cs,cs*2,nm+1))
            
            if cs<0:
                q.append((cp,1,nm+1))
            else:
                q.append((cp,-1,nm+1))
                
