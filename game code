# Function to print the board with box style
def print_board(board):
    print("  1   2   3")
    print("-----------")
    for i in range(3):
        print(f"{i+1} {board[i][0]} | {board[i][1]} | {board[i][2]}")
        if i < 2:
            print("  ---|---|---")

# Function to check if a player has won
def check_win(board, player):
    # Check rows, columns, and diagonals
    for i in range(3):
        if all([board[i][j] == player for j in range(3)]) or all([board[j][i] == player for j in range(3)]):
            return True
    if board[0][0] == player and board[1][1] == player and board[2][2] == player:
        return True
    if board[0][2] == player and board[1][1] == player and board[2][0] == player:
        return True
    return False

# Function to check if the board is full (draw)
def is_full(board):
    return all(board[i][j] != " " for i in range(3) for j in range(3))

# Function to get valid input for row and column
def get_valid_input():
    while True:
        try:
            row = int(input("Enter row (1-3): ")) - 1
            col = int(input("Enter column (1-3): ")) - 1
            if row not in range(3) or col not in range(3):
                print("Invalid position! Please enter a number between 1 and 3.")
            else:
                return row, col
        except ValueError:
            print("Invalid input! Please enter integers between 1 and 3.")

# Main function for the game
def tic_tac_toe():
    while True:  # This loop allows for replaying the game
        board = [[" " for _ in range(3)] for _ in range(3)]  # Initialize empty board
        current_player = "X"  # Player "X" starts

        print("Welcome to Tic-Tac-Toe!")
        
        while True:
            print_board(board)
            
            # Get the current player's move
            print(f"Player {current_player}'s turn:")
            row, col = get_valid_input()

            # Check if the move is valid (position is empty)
            if board[row][col] != " ":
                print("This position is already taken. Choose another one.")
                continue

            # Place the player's move on the board
            board[row][col] = current_player

            # Check if the current player wins
            if check_win(board, current_player):
                print_board(board)
                print(f"Player {current_player} wins!")
                break
            
            # Check if the board is full (draw)
            if is_full(board):
                print_board(board)
                print("It's a draw!")
                break
            
            # Switch to the other player
            current_player = "O" if current_player == "X" else "X"

        # Ask if the players want to play again
        play_again = input("Do you want to play again? (yes/no): ").strip().lower()
        if play_again != "yes":
            print("Thanks for playing!")
            break

# Run the game
if __name__ == "__main__":
    tic_tac_toe()
