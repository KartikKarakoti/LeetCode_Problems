class Solution:
    def findMinDifference(self, timePoints: List[str]) -> int:
        # Convert time from "HH:MM" to minutes since 00:00
        def timeToMinutes(time: str) -> int:
            hours, minutes = map(int, time.split(':'))
            return hours * 60 + minutes
        
        # Step 1: Convert all times to minutes
        minutes = [timeToMinutes(tp) for tp in timePoints]
        
        # Step 2: Sort the minutes
        minutes.sort()
        
        # Step 3: Calculate the minimum difference between consecutive times
        min_diff = float('inf')  # Initialize to a large number
        
        for i in range(1, len(minutes)):
            min_diff = min(min_diff, minutes[i] - minutes[i - 1])
        
        # Step 4: Check the circular difference between the last and first time points
        circular_diff = 1440 - minutes[-1] + minutes[0]
        min_diff = min(min_diff, circular_diff)
        
        return min_diff
