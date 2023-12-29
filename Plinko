import random

def generate_board(rows):
    """Generate a Plinko board with the given number of rows."""
    board = [[' ' for _ in range(rows)] for _ in range(rows)]
    for i in range(rows):
        for j in range(rows - i):
            board[i][j] = '|'
    return board

def drop_ball(board, risk):
    """Drop a ball from the top of the board and return its final position."""
    pos_x, pos_y = 0, random.randint(0, len(board) - 1)
    for row in board:
        if row[pos_y] == '|':
            if random.random() < risk:
                # Ball bounces to the left
                pos_y -= 1
            else:
                # Ball bounces to the right
                pos_y += 1
    return pos_y

def play_plinko(bet_amount, risk, rows):
    """Play a game of Plinko with the given settings."""
    board = generate_board(rows)
    final_pos = drop_ball(board, risk)
    multiplier = board[0][final_pos]
    if multiplier == 'X':
        # Ball landed in a multiplier slot
        winnings = bet_amount * int(multiplier[1:])
        print(f'Congratulations! You won {winnings} coins!')
    else:
        print('Sorry, you didn\'t win this time. Better luck next time!')

# Example usage
play_plinko(bet_amount=10, risk=0.6, rows=10)
