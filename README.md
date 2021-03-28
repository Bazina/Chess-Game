# Chess-Game

## Table of Contents

- [Design Overview](#Design-Overview)
    - [The Main Functions](#The-Main-Functions)
- [Setup](#Setup)
- [Game Description and Features](#Game-Description-and-Features)
- [Used Data Structures](#Used-Data-Structures)
- [User Manual](#User-Manual)

### Design Overview

- Built with C language and for the GUI, SDL Library was used.
- Structures of arrays and variables save the data of the game and check every move which happens on the pitch.
- The game loop starts with the process input to catch the movement of the user and check the validity of the moves.
- By pressing the escape button in the keyboard or the close window button the games shutdown.
- The clicks are controlled by the `SDL_WaitEvent` so that the game waits until there an input and then start to handle it as a result the CPU usage is low.
- The process input stage depends on three main events:
    - Mouse Button Down
    - Mouse Motion
    - Mouse Button Up
- With these events the movement of the user can be handled by the coordanites of the mouse.
- #### The Main Functions:
    - Built function for every type of movement in the game as in the table below:

| Function                                                               | Used for                                            |
| :--------------------------------------------------------------------: |:--------------------------------------------------: |
| `white_move` , `black_move`                                            | Checking the movement of the pieces for every color |
| `white_kill` , `black_kill` , `white_kill_passant` , `black_kill_passant` | Check if there is a dead piece due to the last move |
| `white_left_castling` , `white_right_castling` , `black_right_castling` , `black_left_castling` | when a move evolve castling these are a helping functions |
| `dead_pos` , `stalemate` , `check_mate` | Checking for the end of a game or if there was a check for the king |
| `get_valid_moves` | Get the valid moves for the chosen piece |
- The game has a unique UI / UX with a responsive design, and when the user tries to move any piece, legal moves get highlighted with a green mark, and illegal moves get highlighted with a red mark.

### Setup

1. These files should run with [code blocks with mingw32](https://www.fosshub.com/Code-Blocks.html?dwl=codeblocks-20.03mingw-setup.exe).
2. Files for SDL Library should be downloaded, 
    - The version is `SDL2-devel-2.0.14-mingw.tar.gz`, [SDL Library](https://libsdl.org/release/SDL2-devel-2.0.14-mingw.tar.gz)
    - The version is `SDL2_image-devel-2.0.5-mingw.tar.gz`, [SDL Image Library](https://www.libsdl.org/projects/SDL_image/release/SDL2_image-devel-2.0.5-mingw.tar.gz).
    - The version is `SDL2_mixer-devel-2.0.4-mingw.tar.gz`, [SDL Mixer Library](https://libsdl.org/projects/SDL_mixer/release/SDL2_mixer-devel-2.0.4-mingw.tar.gz).
    - The version is `SDL2_ttf-devel-2.0.15-mingw.tar.gz`, [SDL TTF Library](https://www.libsdl.org/projects/SDL_ttf/release/SDL2_ttf-devel-2.0.15-mingw.tar.gz).
3. After installing `code blocks with mingw32` and downloading `SDL libraries`, extract the files of SDL library twice then we have the folder of the library.
4. Open the folder, then go into the folder with the name `x86_64-w64-mingw32`, we will take the folder with `bin, lib, include` names and copy them in this directory in `C:\Program Files\CodeBlocks\MinGW\x86_64-w64-mingw32`, and replace all the files.
5. Finally, open the `include` folder in this location `C:\Program Files\CodeBlocks\MinGW\x86_64-w64-mingw32\include` and there is a folder called `SDL` copy all the files in it and paste them in the `include` folder.
6. Repeat these steps for the remaining libraries.
7. Now the game can be build in `code blocks`.

### Game Description and Features

- User can interact with the game using the mouse only.
- Validation check for every move on the pitch and the game shows up the legal moves for a piece with a green mark.
- Special moves like:
    1. Castling.
    2. En passant.
    3. Promotion.
- A tomb is built for the dead pieces.
- Movement Record is built to show the last move on the board.
- Legend music to help to keep calm and focus.
- When the game comes to an end, a screens appear to describe the end.
- Undo, Redo buttons which undo or redo the moves at anytime and anywhere as well as the game can be continued anywhere the user want.
- Save, Load button which save or load the last saved game with all the data and previous moves.

#### Features in Videos

- Showing the turns and how it goes on.

    ![](https://media.giphy.com/media/A7V5EV0VwKWk27KBPp/giphy.gif)