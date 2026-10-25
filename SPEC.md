# Backgammon — Spec

A two-player backgammon game for one screen, in a single `index.html` file that runs by opening it in a web browser. Plain HTML, CSS, and JavaScript only: no frameworks, no installs, no internet needed.

## Acceptance criteria

1. The game starts with the standard backgammon setup, and clicking **Roll** shows two dice from 1–6.
2. Each die moves one checker exactly that many points. A double gives four moves. Landing on a point with 2+ opponent checkers is not allowed.
3. The turn passes to the other player once both dice (or all four on a double) are used, or when the player clicks **Pass** because no legal move remains.
4. Landing on a single opponent checker sends it to the **bar**. That player must re-enter it before moving any other checker.
5. Once all 15 of a player's checkers are in their home board, they can bear off. The first to bear off all 15 sees a "You win" message and a **New Game** button that resets the board.

## Out of scope (for today)

- Forced-move rules (must use both dice if possible): players police this themselves
- Doubling cube
- Computer opponent
