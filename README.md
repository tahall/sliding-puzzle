# Sliding Puzzle

A fully client-side sliding puzzle game with five difficulty levels (3×3 through 10×10). No dependencies, no build step — just open `index.html` in a browser.

## Features

- **Five difficulty levels** — 3×3, 4×4, 6×6 (default), 8×8, and 10×10 grids
- **Image tile mode** — upload any photo and it is sliced across the tiles; solve the puzzle to reassemble the picture
- **Numbers toggle** — show or hide tile numbers independently of image mode
- **Smooth tile animations** — tiles physically slide into the blank using CSS transforms (140 ms)
- **Move counter** — tracks the number of tile slides
- **Timer** — starts on your first move, stops when you solve the puzzle
- **Highlighted movable tiles** — adjacent tiles that can slide are visually distinguished
- **Keyboard support** — use the arrow keys to slide tiles (the tile opposite to the arrow direction slides into the blank)
- **Shuffle** — generates a new, guaranteed-solvable random puzzle
- **Show Solution** — replays your moves in reverse, resetting the board to its original shuffled state

## How to Play

1. Open `index.html` in any modern browser.
2. Select a difficulty (default: 6×6), then click **Shuffle** (or it auto-shuffles on load).
3. Optionally click **Upload Image** to use your own photo as the puzzle.
4. Click a tile adjacent to the blank space to slide it, or use the **arrow keys**.
5. Arrange all tiles in order (blank in the bottom-right corner) to win.
6. Use **Show Solution** at any time to watch your moves play back in reverse — useful if you get stuck or want to analyse your path.

## Controls

| Action | Input |
|---|---|
| Slide a tile | Click the tile |
| Slide a tile | Arrow keys (←→↑↓) |
| Change difficulty | 3×3 / 4×4 / 6×6 / 8×8 / 10×10 buttons |
| New puzzle | Shuffle button |
| Undo all moves | Show Solution button |
| Load image | Upload Image button |
| Toggle numbers | Numbers: On/Off button (image mode) |
| Remove image | Clear Image button (image mode) |

## Technical Notes

- **Solvability guarantee** — every shuffled board is checked using the standard inversion-count algorithm before being presented. Odd-width grids require an even inversion count; even-width grids require that inversions plus the blank's row from the bottom is even. Boards that fail either check (or are already solved) are re-shuffled automatically.
- **Smooth animations** — tiles are absolutely positioned in the board container and move via `transform: translate()`. Only the two tiles involved in each move have their transform updated; CSS `transition` handles the rest. A short block on rapid input prevents visual glitches mid-animation.
- **Show Solution** works by recording each move the player makes and replaying them in reverse. It does not compute an optimal path from scratch (infeasible for large grids in-browser).
- **Difficulty** — the tile size scales automatically so all grid sizes fit within a consistent ~560 px board area.
- **Image mode** — the uploaded image is center-cropped to a square on an 800×800 px canvas, then sliced across tiles using CSS `background-image`, `background-size`, and `background-position`. Changing difficulty re-applies the image at the new tile size automatically. Numbers can be overlaid or hidden independently.
- Pure vanilla HTML/CSS/JS — no frameworks, no external assets.

## Browser Support

Works in any modern browser (Chrome, Firefox, Safari, Edge). No internet connection required.
