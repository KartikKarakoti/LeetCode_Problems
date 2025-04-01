class ExamRoom:

    def __init__(self, n: int):
        self.n = n
        self.heap = []

        self.heap.append((-self.dist(0, n - 1), 0, n - 1))

    def seat(self) -> int:
        res = 0

        curr_dist, l, r = heappop(self.heap)
        curr_dist = -curr_dist

        if l == 0:
            res = 0
        elif r == self.n - 1:
            res = self.n - 1
        else:
            res = l + curr_dist
        
        if res > l:
            heappush(self.heap, (-self.dist(l, res - 1), l, res - 1))
        
        if res < r:
            heappush(self.heap, (-self.dist(res + 1, r), res + 1, r))

        return res

    def leave(self, p: int) -> None:
        prev_interval, next_interval = None, None

        for item in self.heap:
            if item[1] - 1 == p:
                next_interval = item
            if item[2] + 1 == p:
                prev_interval = item
        
        start = p
        end = p
        if prev_interval:
            start = prev_interval[1]
            self.heap.remove(prev_interval)
        if next_interval:
            end = next_interval[2]
            self.heap.remove(next_interval)

        heappush(self.heap, (-self.dist(start, end), start, end))
        
    def dist(self, l, r):
        if l == 0 or r == self.n - 1:
            return r - l
        else:
            return (r - l) // 2
