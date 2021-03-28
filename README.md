# Chess-Game

## Table of Contents

- [Design Overview](#Design-Overview)
- [Setup](#Setup)
- [Game Description and Features](#Game-Description-and-Features)
- [Used Data Structures](#Used-Data-Structures)
- [The Main Functions](#The-Main-Functions)
- [User Manual](#User-Manual)

### Design Overview

- Built with C language and for the GUI, SDL Library was used.
- Structures of arrays and variables save the data of the game and check every move which happens on the pitch.
- The game loop starts with the process input to catch the movement of the user and check the validity of the moves.
- By pressing the escape button in the keyboard or the close window button the games shutdown.
- The clicks are controlled by the `SDL_WaitEvent` so that the game waits until there an input and then start to handle it as a result the CPU usage is low
- The process input stage depends on three main events:
    - Mouse Button Down
    - Mouse Motion
    - Mouse Button Up
- With these events the movement of the user can be handled by the coordanites of the mouse.
- Built function for every type of movement in the game as in the table below:

| Function                                                               | Used for                                            |
| :--------------------------------------------------------------------: |:--------------------------------------------------: |
| `white_move` , `black_move`                                            | Checking the movement of the pieces for every color |
| `white_kill` , `black_kill` , `white_kill_passant` , `black_kill_passant` | Check if there is a dead piece due to the last move |
| `white_left_castling` , `white_right_castling` , `black_right_castling` , `black_left_castling` | when a move evolve castling these are a helping functions |
| `dead_pos` , `stalemate` , `check_mate` | Checking for the end of a game or if there was a check for the king |
