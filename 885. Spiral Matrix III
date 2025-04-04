class Solution:
    def spiralMatrixIII(self, rows: int, cols: int, rStart: int, cStart: int) -> List[List[int]]:
        directions = [(0, 1), (1, 0), (0, -1), (-1, 0)]  # East, South, West, North
        result = [[rStart, cStart]]
        total_cells = rows * cols
        steps = 0
        direction_index = 0
        
        while len(result) < total_cells:
            if direction_index % 2 == 0:
                steps += 1
            
            for _ in range(steps):
                rStart += directions[direction_index][0]
                cStart += directions[direction_index][1]
                
                if 0 <= rStart < rows and 0 <= cStart < cols:
                    result.append([rStart, cStart])
                    if len(result) == total_cells:
                        return result
            
            direction_index = (direction_index + 1) % 4
        
        return result
