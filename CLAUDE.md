# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the project

Open `tictactoe.html` directly in a browser — no build step, server, or dependencies required.

## Architecture

The entire project lives in a single file: `tictactoe.html`.

- **State**: `board` (9-element array), `current` (active player `'X'`/`'O'`), `gameOver` (boolean), `score` (object tracking X wins, O wins, draws). All state is in-memory; refreshing resets everything except score is also reset.
- **Win detection**: `WINS` is a hardcoded array of the 8 winning index combinations. `checkWin()` iterates it and returns the winning triple or `null`.
- **Rendering**: Cells are plain `<div>` elements selected once at load. DOM is mutated directly — no virtual DOM or framework. CSS classes (`x`, `o`, `taken`, `win`) drive all visual state.
- **Game flow**: click handler on each cell → update `board[]` → call `checkWin()` → update DOM and score.

## Git workflow

Commit and push to GitHub after every meaningful change. Remote: `https://github.com/mahbodshahshahani/claudecodetest` (branch: `master`).
