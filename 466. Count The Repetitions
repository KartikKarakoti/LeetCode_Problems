class Solution:
    def getMaxRepetitions(self, s1: str, n1: int, s2: str, n2: int) -> int:
        # Early exit if s1 is too small to contain s2
        if n1 == 0:
            return 0
        
        s1_count, s2_count, index = 0, 0, 0
        recall = {}

        # Process s1 n1 times
        while s1_count < n1:
            s1_count += 1
            for char in s1:
                if char == s2[index]:
                    index += 1
                if index == len(s2):
                    s2_count += 1
                    index = 0
            
            # Detect and handle loops
            if index in recall:
                prev_s1_count, prev_s2_count = recall[index]
                loop_s1_count = s1_count - prev_s1_count
                loop_s2_count = s2_count - prev_s2_count
                
                # Calculate how many times the loop can repeat
                remaining_loops = (n1 - s1_count) // loop_s1_count
                s1_count += remaining_loops * loop_s1_count
                s2_count += remaining_loops * loop_s2_count

            recall[index] = (s1_count, s2_count)
        
        return s2_count // n2
