class Solution:
    def findReplaceString(self, s: str, indices: List[int], sources: List[str], targets: List[str]) -> str:
        
        # go thru indices / sources and check whether it matches in s
        # if it does, then mark it somehow
        toReplace = {}
        for i in range(len(sources)):
            s_idx = indices[i]
            if s[s_idx:s_idx+len(sources[i])] == sources[i]:
                toReplace[s_idx] = i

        res = []
        i = 0
        # go thru each char of s in a while loop
        while i < len(s):
            # if the index is marked, add the target to the res string and increment index by len(sources[i]) elements
            if i in toReplace:
                res.append(targets[toReplace[i]])
                i += len(sources[toReplace[i]])
            else:
                res.append(s[i])
                i += 1

        # return joined string
        return ''.join(res)
