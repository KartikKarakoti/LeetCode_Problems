class Solution:
    def largeGroupPositions(self, s: str) -> List[List[int]]:
            # Initialize variables
            result = []
            start = 0
            
            # Loop through the string to find groups
            while start < len(s):
                end = start
                # Move 'end' until the character changes
                while end < len(s) and s[end] == s[start]:
                    end += 1
                    
                # Check if the group is large
                if end - start >= 3:
                    result.append([start, end - 1])
                
                # Move 'start' to the end of the current group
                start = end
            
            return result
