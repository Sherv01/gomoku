# Gomoku (Five in a Row) Game Logic

This Python code implements the core logic for a Gomoku (Five in a Row) game, including functions for detecting rows, scoring the board, searching for the best move, and checking for a win. This project is a part of ESC180 (Introduction to Computer Programming) at the University of Toronto.

## Description

The code provides the following functionalities:

*   `is_empty(board)`: Checks if the game board is empty.
*   `is_bounded(board, y_end, x_end, length, d_y, d_x)`: Checks if a sequence of stones is bounded (closed or semi-open). Returns "CLOSED", "SEMIOPEN", or "OPEN".
*   `detect_row(board, col, y_start, x_start, length, d_y, d_x)`: Detects open and semi-open rows of a given length for a specific color (`col`) starting from a given position and direction.
*   `detect_rows(board, col, length)`: Detects all open and semi-open rows of a given length for a specific color on the entire board.
*   `search_max(board)`: Searches for the best move for the black player based on the current board state using a scoring function.
*   `score(board)`: Scores the board based on the number of open and semi-open rows of different lengths for both black and white players.
*   `is_win(board)`: Checks if there is a winner (five in a row) or a draw.
*   `print_board(board)`: Prints the game board to the console in a user-friendly format.
*   `make_empty_board(sz)`: Creates an empty game board of a given size.
*   `analysis(board)`: Analyzes the board and prints the number of open and semi-open rows for each color.
*   `play_gomoku(board_size)`: Implements the main game loop, allowing a human player to play against the computer.
*   `put_seq_on_board(board, y, x, d_y, d_x, length, col)`: Helper function to place a sequence of stones on the board for testing purposes.

## Board Representation

The game board is represented as a 2D list of strings, where:

*   " " represents an empty cell.
*   "b" represents a black stone.
*   "w" represents a white stone.

## Bounding Logic

The `is_bounded` function determines whether a sequence is "OPEN", "SEMIOPEN", or "CLOSED" based on the stones adjacent to the sequence.

*   **OPEN:** Both ends of the sequence are empty.
*   **SEMIOPEN:** One end of the sequence is empty, and the other end is either a stone of a different color or the edge of the board.
*   **CLOSED:** Both ends of the sequence are either stones of a different color or the edge of the board.

## Scoring Logic

The `score` function assigns scores based on the number of open and semi-open rows, prioritizing longer sequences. A five-in-a-row results in a large positive (black win) or negative (white win) score.

## Game Play

The `play_gomoku` function allows a human player to play against a simple AI that uses the `search_max` function to choose its moves.

## Testing

The code includes several test functions:

*   `test_is_empty()`
*   `test_is_bounded()`
*   `test_detect_row()`
*   `test_detect_rows()`
*   `test_search_max()`
*   `easy_testset_for_main_functions()`
*   `some_tests()`

These tests help ensure the correct functionality of the core game logic. The `some_tests()` function provides more complex test cases with expected outputs. The test cases at the end of the file are particularly useful for testing edge cases and specific scenarios.

## Usage

To play the game, call the `play_gomoku(board_size)` function with the desired board size.

## Example Usage (in Python)

```python
if __name__ == '__main__':
    easy_testset_for_main_functions()
    some_tests()
    # play_gomoku(8)  # Uncomment to play the game
    # ... (additional test cases)
