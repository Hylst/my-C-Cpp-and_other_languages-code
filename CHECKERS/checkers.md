Checkers (Draughts)  0.9e     UNFINISHED 

Detailed Explanation of the Code

Data Structures and Initialization

Board Representation: The board is represented as an 8x8 matrix (char board[SIZE][SIZE]), where each cell can hold:
'X': Player 1's regular piece.
'O': Player 2's regular piece (AI or Player 2).
'K': Player 1's King.
'Q': Player 2's King.
'.': Empty playable square.
' ': Non-playable square (light squares).
Initialization: The init_board() function sets up the initial positions of the pieces according to standard Checkers rules.
Displaying the Board and Intro

print_board(): Renders the board in a user-friendly ASCII format with row and column numbers for easy reference.
display_intro(): Provides an introduction to the game and outlines the rules clearly.
Game Modes and AI Difficulty

choose_game_mode(): Allows players to select between Player vs Player and Player vs AI modes. If AI is selected, players can choose the difficulty level, which determines the depth of the Minimax algorithm:
Easy: Depth 3
Medium: Depth 5
Hard: Depth 7
Move Validation and Execution

is_valid_move(): Checks whether a proposed move is valid based on the game's rules, including capturing logic.
make_move(): Executes the move on the board, handles capturing of opponent pieces, and promotes pieces to Kings if they reach the opposite end.
promote_if_possible(): Specifically handles the promotion of pieces to Kings when they reach the opposite end of the board.
AI Implementation

evaluate(): Assigns a score to the current board state from the AI's perspective. Positive scores favor Player 1, and negative scores favor Player 2 (AI).
minimax(): Implements the Minimax algorithm with Alpha-Beta pruning to efficiently evaluate the best possible moves up to a certain depth.
ai_move(): Uses the minimax() function to determine and execute the best move for the AI. It also handles multiple captures if available.
Player Moves

player_move(): Handles input from human players, ensuring that moves are valid, capturing is enforced when possible, and multiple captures are managed correctly.
Endgame Detection

has_any_moves(): Checks if a player has any valid moves left.
is_game_over(): Determines if the game has ended either by one player having no remaining pieces or no available moves. It sets the winner accordingly.
Main Game Loop

The main() function initializes the game, displays the intro, allows players to choose the game mode and AI difficulty, and then enters the main loop where players and AI take turns making moves until the game ends. Upon completion, it announces the winner.
How to Compile and Run
Save the Code: Save the above code in a file named checkers.c.

A lot more to do...

In Bas

***********************************
*           WELCOME TO            *
*         ASCII CHECKERS GAME      *
***********************************

Rules:
1. Player 1 (X) moves first, followed by Player 2 (O).
2. Move diagonally on dark squares.
3. Capture opponent's pieces by jumping over them.
4. If you can capture, you must capture.
5. Multiple captures are allowed in a single turn.
6. Reach the opposite end to promote your piece to a King (K for Player 1, Q for Player 2).
7. Kings can move and capture both forwards and backwards.

Choose Game Mode:
1. Player vs Player
2. Player vs AI
Enter your choice: 2

Choose AI Difficulty Level:
1. Easy
2. Medium
3. Hard
Enter your choice: 2
    0  1  2  3  4  5  6  7 
   +---+---+---+---+---+---+---+---+
 0 |   | O |   | O |   | O |   | O |
   +---+---+---+---+---+---+---+---+
 1 | O |   | O |   | O |   | O |   |
   +---+---+---+---+---+---+---+---+
 2 |   | O |   | O |   | O |   | O |
   +---+---+---+---+---+---+---+---+
 3 |   |   |   |   |   |   |   |   |
   +---+---+---+---+---+---+---+---+
 4 |   |   |   |   |   |   |   |   |
   +---+---+---+---+---+---+---+---+
 5 | X |   | X |   | X |   | X |   |
   +---+---+---+---+---+---+---+---+
 6 |   | X |   | X |   | X |   | X |
   +---+---+---+---+---+---+---+---+
 7 | X |   | X |   | X |   | X |   |
   +---+---+---+---+---+---+---+---+

Player X, enter your move (startX startY endX endY): 5 0 4 1

    0  1  2  3  4  5  6  7 
   +---+---+---+---+---+---+---+---+
 0 |   | O |   | O |   | O |   | O |
   +---+---+---+---+---+---+---+---+
 1 | O | X | O |   | O |   | O |   |
   +---+---+---+---+---+---+---+---+
 2 |   | O |   | O |   | O |   | O |
   +---+---+---+---+---+---+---+---+
 3 |   |   |   |   |   |   |   |   |
   +---+---+---+---+---+---+---+---+
 4 |   | X |   |   |   |   |   |   |
   +---+---+---+---+---+---+---+---+
 5 |   |   | X |   | X |   | X |   |
   +---+---+---+---+---+---+---+---+
 6 |   | X |   | X |   | X |   | X |
   +---+---+---+---+---+---+---+---+
 7 | X |   | X |   | X |   | X |   |
   +---+---+---+---+---+---+---+---+

AI is making a move...
AI moves from (2, 1) to (3, 0)
    0  1  2  3  4  5  6  7 
   +---+---+---+---+---+---+---+---+
 0 |   | O |   | O |   | O |   | O |
   +---+---+---+---+---+---+---+---+
 1 | O | X | O |   | O |   | O |   |
   +---+---+---+---+---+---+---+---+
 2 |   |   |   | O |   | O |   | O |
   +---+---+---+---+---+---+---+---+
 3 | O |   |   |   |   |   |   |   |
   +---+---+---+---+---+---+---+---+
 4 |   | X |   |   |   |   |   |   |
   +---+---+---+---+---+---+---+---+
 5 |   |   | X |   | X |   | X |   |
   +---+---+---+---+---+---+---+---+
 6 |   | X |   | X |   | X |   | X |
   +---+---+---+---+---+---+---+---+
 7 | X |   | X |   | X |   | X |   |
   +---+---+---+---+---+---+---+---+

Player O, enter your move (startX startY endX endY): 5 2 4 1

... (Gameplay continues until the game ends)

