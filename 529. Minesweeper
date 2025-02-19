class Solution:
    def updateBoard(self, board: List[List[str]], click: List[int]) -> List[List[str]]:
        x,y = click[0],click[1]
        options = []
        if board[x][y] == "M":
            board[x][y] = "X"
        else:
            options = [(0,1),(0,-1),(1,0),(1,-1),(1,1),(-1,-1),(-1,0),(-1,1)]

            count = 0
            for i,j in options:
                if x+i > -1 and x+i < len(board) and y+j > -1 and y+j < len(board[0]):
                    if board[x+i][y+j] == "M":
                        count += 1
            if count == 0:
                board[x][y] = "B"
                for i,j in options:
                    if x+i > -1 and x+i < len(board) and y+j > -1 and y+j < len(board[0]):
                        if board[x+i][y+j] == "M" or board[x+i][y+j] == "E":
                            self.updateBoard(board,[x+i,y+j])
            else:
                board[x][y] = str(count)

        return board
