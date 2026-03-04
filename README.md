# Sliding Puzzle — 10×10

A fully client-side sliding puzzle game played on a **10×10 grid** (99 tiles + 1 blank). No dependencies, no build step — just open `index.html` in a browser.

## Features

- **10×10 grid** — 99 numbered tiles and one blank space
- **Move counter** — tracks the number of tile slides
- **Timer** — starts on your first move, stops when you solve the puzzle
- **Highlighted movable tiles** — adjacent tiles that can slide are visually distinguished
- **Keyboard support** — use the arrow keys to slide tiles (the tile opposite to the arrow direction slides into the blank)
- **Shuffle** — generates a new, guaranteed-solvable random puzzle
- **Show Solution** — replays your moves in reverse, resetting the board to its original shuffled state

## How to Play

1. Open `index.html` in any modern browser.
2. Click **Shuffle** (or it auto-shuffles on load).
3. Click a tile adjacent to the blank space to slide it, or use the **arrow keys**.
4. Arrange all tiles in order (1–99, blank in the bottom-right corner) to win.
5. Use **Show Solution** at any time to watch your moves play back in reverse — useful if you get stuck or want to analyse your path.

## Controls

| Action | Input |
|---|---|
| Slide a tile | Click the tile |
| Slide a tile | Arrow keys (←→↑↓) |
| New puzzle | Shuffle button |
| Undo all moves | Show Solution button |

## Technical Notes

- **Solvability guarantee** — every shuffled board is checked using the standard inversion-count algorithm before being presented. Boards that would be unsolvable (or already solved) are re-shuffled automatically.
- **Show Solution** works by recording each move the player makes. Replaying them in reverse restores the original shuffle. It does not compute an optimal solution from scratch (which would be computationally infeasible for a 10×10 grid in-browser).
- Pure vanilla HTML/CSS/JS — no frameworks, no external assets.

## Browser Support

Works in any modern browser (Chrome, Firefox, Safari, Edge). No internet connection required.
