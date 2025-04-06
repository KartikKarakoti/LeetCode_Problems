from collections import deque


class Solution:
    def board_to_list(self, board: list[list[int]]) -> list[int]:
        parse_left = True
        output = []

        for row in range(len(board) - 1, -1, -1):
            if parse_left:
                output.extend(board[row])
                parse_left = False
            else:
                output.extend(reversed(board[row]))
                parse_left = True

        for i in range(len(output)):
            if output[i] != -1:
                output[i] -= 1

        return output

    def snakesAndLadders(self, board: list[list[int]]) -> int:
        linear = self.board_to_list(board)
        size = len(linear)

        queue = deque()
        queue.append((0, 0))
        seen = set([0])

        while queue:
            (spot, moves) = queue.popleft()

            for roll in range(1, 7):
                new_spot = spot + roll

                if new_spot >= size:
                    continue

                next_spot = linear[new_spot]
                if next_spot == -1:
                    next_spot = new_spot

                if next_spot == size - 1:
                    return moves + 1

                if next_spot not in seen:
                    seen.add(next_spot)
                    queue.append((next_spot, moves + 1))

        # should not get here unless it is impossible to get to the end
        return -1
