# GODGIVEN
TOOK ME SOME TIME



class ChessGame:
    def __init__(self):
        self.board = [
            ['R', 'N', 'B', 'Q', 'K', 'B', 'N', 'R'],
            ['P', 'P', 'P', 'P', 'P', 'P', 'P', 'P'],
            ['.', '.', '.', '.', '.', '.', '.', '.'],
            ['.', '.', '.', '.', '.', '.', '.', '.'],
            ['.', '.', '.', '.', '.', '.', '.', '.'],
            ['.', '.', '.', '.', '.', '.', '.', '.'],
            ['p', 'p', 'p', 'p', 'p', 'p', 'p', 'p'],
            ['r', 'n', 'b', 'q', 'k', 'b', 'n', 'r']
        ]

    def print_board(self):
        print("  a b c d e f g h")
        print("  -----------------")
        for i in range(8):
            print(8 - i, end="|")
            for j in range(8):
                print(self.board[i][j], end=" ")
            print("|", 8 - i)
        print("  -----------------")
        print("  a b c d e f g h")

    def move_piece(self, start_pos, end_pos):
        start_row, start_col = start_pos
        end_row, end_col = end_pos

        piece = self.board[start_row][start_col]
        self.board[start_row][start_col] = '.'
        self.board[end_row][end_col] = piece

    def play(self):
        print("Welcome to the Chess Game!")
        print("Enter your moves in the format 'a2 to a4'")

        while True:
            self.print_board()
            start_pos = input("Enter the position of the piece you want to move: ")
            end_pos = input("Enter the position where you want to move the piece: ")

            start_row = 8 - int(start_pos[1])
            start_col = ord(start_pos[0]) - ord('a')
            end_row = 8 - int(end_pos[1])
            end_col = ord(end_pos[0]) - ord('a')

            self.move_piece((start_row, start_col), (end_row, end_col))


if __name__ == "__main__":
    game = ChessGame()
    game.play()
