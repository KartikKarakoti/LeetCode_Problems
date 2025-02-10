class Solution:
    def countBattleships(self, board: List[List[str]]) -> int:
        count = 0
        for i in range(len(board)):
            for j in range(len(board[0])):
                if board[i][j] == 'X':
                    if i == 0 and j == 0:
                        count += 1
                    elif i == 0 and j > 0:
                        if board[i][j-1] == '.':
                            count += 1
                    elif i > 0 and j == 0:
                        if board[i-1][j] == '.':
                            count += 1
                    else:
                        if board[i][j-1] == '.' and board[i-1][j] == '.':
                            count += 1
        return count
