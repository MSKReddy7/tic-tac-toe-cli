# Tic Tac Toe

A colorful terminal-based Tic-Tac-Toe game written in C for Windows. It supports:

- Two-player gameplay
- Board selection (default, blue, and plane styles)
- Player name entry
- Restart and new-game options
- Animated end-of-game screen
- ANSI color and text effects in the terminal

## Project Overview

This project uses a classic 3x3 Tic-Tac-Toe game loop and prints the board in the console with custom text styles and background colors. It is designed for command-line use and relies on Windows APIs such as `Sleep` and `system("cls")`.

## How to Run

Compile with a C compiler such as GCC/MinGW:

```bash
gcc main.c -o tic_tac_toe
```

Then run:

```bash
tic_tac_toe.exe
```

## Game Controls

- Enter `1` to `9` to place your move
- Enter `10` to reset the board
- Enter a different value to exit the game
- Choose a board style during startup

## Game Flow

1. Start screen appears
2. Select a board theme
3. Enter player names
4. Play turns until there is a win or draw
5. Choose to reset, start a new game, or exit

## ANSI Escape Codes Used in This Project

This game uses ANSI escape sequences to color text and add effects in the console. The general format is:

```text
\033[<style>;<color>m
```

Where:

- `\033[` starts the escape sequence
- `m` ends it
- values such as `1`, `31`, `44`, etc. control style and color
- `\033[0m` resets the terminal formatting

### Common Style Codes

| Sequence | Effect |
|---|---|
| `\033[0m` | Reset to default terminal style |
| `\033[1m` | Bold text |
| `\033[4m` | Underline text |

### Text Color Codes

| Sequence | Color |
|---|---|
| `\033[1;30m` | Dark/black |
| `\033[1;31m` | Red |
| `\033[1;32m` | Green |
| `\033[1;33m` | Yellow |
| `\033[1;34m` | Blue |
| `\033[1;35m` | Magenta |
| `\033[1;36m` | Cyan |
| `\033[1;37m` | White |

### Background Color Codes

| Sequence | Background Color |
|---|---|
| `\033[41m` | Red background |
| `\033[42m` | Green background |
| `\033[43m` | Yellow background |
| `\033[44m` | Blue background |
| `\033[45m` | Magenta background |
| `\033[46m` | Cyan background |
| `\033[47m` | White background |

### Color and Effect Examples from This Project

These are the exact patterns used in the source code:

```text
\033[1;35m\033[1;31m %s '\033[0mX\033[1;35m` Enter a Box Number\033[0m
\033[1;32m %s '\033[0m%c\033[1;32m' WON THE MATCH !!!\033[0m
\033[1;31menter \033[1;32m`\033[1;33m1\033[1;32m'\033[1;31m to start the game\033[0m
\033[43m----------------------------------\033[0mDRAW\033[43m---------------------------------------\033[0m
\033[1;34m         ||         ||       \033[0m
\033[1;31m%c    \033[1;34m||    \033[1;31m%c    \033[1;34m||    \033[1;31m%c    \033[0m
\033[44m           \033[47m||\033[44m           \033[47m||\033[44m           
\033[47m===========||===========||===========\033[0m
\033[1;36mNo names entered for 'X' using default name player 1\033[0m
\033[4m \033[1m \033[1;33m    TIC TAC TOE\033[0m
```

## Notes

- These are ANSI escape sequences, which are supported by most modern terminal emulators.
- This project was written for Windows-style console behavior, so it may not look the same in Linux/macOS terminals without ANSI support.
- The sequence `\033[0m` is especially important because it resets all previous formatting.

## License

This project is provided as a small educational CLI game and can be modified or extended freely for personal learning and development.
