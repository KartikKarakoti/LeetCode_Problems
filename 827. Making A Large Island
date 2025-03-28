class Solution:
    def largestIsland(self, grid: List[List[int]]) -> int:
        DIR = {(0,1),(1,0),(-1,0),(0,-1)}
        r,c=len(grid),len(grid[0])
        ans,cid=0,2
        components = {}
        zeros=set()
        grid_comp={}
        def bfs(pos,cid):
            queue=[pos]
            k=0
            while queue:
                cx,cy=queue.pop(0)
                if (cx,cy) not in grid_comp:
                    k+=1
                    grid_comp[(cx, cy)] = cid
                    for dx,dy in DIR:
                        nx,ny=cx+dx,cy+dy
                        if 0 <= nx < r and 0 <= ny < c and grid[nx][ny] and (nx, ny) not in grid_comp:
                            queue.append((nx,ny))
            components[cid]=k
         
        for i in range(r):
            for j in range(c):
                if grid[i][j]==1:
                    if (i,j) not in grid_comp:
                        bfs((i,j),cid)
                        cid+=1
                else:
                    zeros.add((i,j))
        if not zeros:
            return r*c
        
        for i,j in zeros:
            s=1
            ids=set()
            for dx,dy in DIR:
                nx,ny=dx+i,dy+j
                if (nx,ny) in grid_comp:
                    id=grid_comp[(nx,ny)]
                    if id not in ids:
                        s+=components[id]
                        ids.add(id)     
            ans=max(ans,s)

        return ans

