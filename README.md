# Peg Solitaire

A browser-based implementation of the classic wooden peg solitaire puzzle game.

## How to play

1. Open `index.html` in any modern browser — no build step or server required.
2. **Setup:** Click any peg to remove it and create the first empty hole.
3. **Playing:** Select a peg (it turns gold), then click a glowing green hole to jump over an adjacent peg. The jumped peg is removed.
4. Keep jumping until no valid moves remain.
5. **Goal:** Finish with as few pegs as possible. One peg left = perfect score.

### Controls

| Action | How |
|---|---|
| Select a peg | Click it |
| Deselect | Click it again, or press `Esc` |
| Execute a jump | Click a highlighted (green) hole |
| Restart | Click **New Game** |

## Board layout

The board is a cross-shaped grid of **45 holes** arranged on a 9×9 coordinate system:

```
· · · ● ● ● · · ·
· · · ● ● ● · · ·
· · · ● ● ● · · ·
● ● ● ● ● ● ● ● ●
● ● ● ● ● ● ● ● ●
● ● ● ● ● ● ● ● ●
· · · ● ● ● · · ·
· · · ● ● ● · · ·
· · · ● ● ● · · ·
```

## Scoring

| Pegs remaining | Rating |
|---|---|
| 1 | Perfect |
| 2 – 3 | Excellent |
| 4 – 8 | Well Done |
| 9+ | Game Over |

## Technical notes

- Single file — `index.html` with embedded CSS and JavaScript, no dependencies.
- Game logic is fully separated from rendering; `applyMove()` never touches the DOM.
- Move validation runs on every click: a jump is legal only when the source has a peg, the middle cell has a peg to capture, and the landing cell is empty.
- Game-over is detected by checking `allMoves().length === 0` after each turn.
