class Solution:
    def eventualSafeNodes(self, g: List[List[int]]) -> List[int]:
        return [*filter(f:=cache(lambda n,v=set():n not in v and (v.add(n) or all(map(f,g[n])))),range(len(g)))]
