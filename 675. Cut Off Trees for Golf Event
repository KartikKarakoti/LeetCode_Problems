class Solution:

    def cutOffTree(self, forest: List[List[int]]) -> int:

        def bfs(beg, end):
            queue, uns = deque([(beg,0)]), unseen.copy()
            uns.discard(beg)

            while queue:
                (r,c), steps = queue.popleft()

                if (r,c) == end: return steps

                for R,C in ((r-1,c), (r,c-1), (r+1,c), (r,c+1)):

                    if (R,C) not in uns: continue

                    queue.append(((R,C),steps+1))
                    uns.discard((R,C))

            return -1
        
        m, n, ans = len(forest), len(forest[0]), 0
        start, trees = (0,0), []

        grid = tuple(product(range(m), range(n)))
        unseen = set(filter(lambda x: forest[x[0]][x[1]] != 0, grid))

        for r,c  in grid:
            if forest[r][c] > 1: heappush(trees,(forest[r][c], (r,c)))

        while trees:
            if (res:= bfs(start,(pos:= heappop(trees)[1]))) < 0: return -1

            ans += res
            start = pos

        return ans
