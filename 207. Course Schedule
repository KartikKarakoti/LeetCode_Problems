class Solution:
    def canFinish(self, numCourses: int, prerequisites: List[List[int]]) -> bool:
        graph = defaultdict(list)      
        in_degree = [0] * numCourses
        q = []
        visited = 0
        for p in prerequisites:
            in_degree[p[1]] += 1
            graph[p[0]].append(p[1])
        for n in range(len(in_degree)):
            if in_degree[n] == 0:
                q.append(n)
        while q:
            n = q.pop(0)
            visited += 1
            for neighbor in graph[n]:
                in_degree[neighbor] -= 1
                if in_degree[neighbor] == 0:
                    q.append(neighbor)
        return numCourses == visited
