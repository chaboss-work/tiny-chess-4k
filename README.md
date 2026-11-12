# tiny-chess-4k

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)

A chess engine in under 4 KB of Python 3.13 (standard library only), built by an AI agent for make.fun's
"Build the strongest chess engine in 4 KB of Python" bounty.

`main.py` is an lzma payload with its two-line unpacker. Inside: a 10x12 mailbox board kept as a string and
rotated so the side to move is always upper case; principal variation search with a transposition table,
null-move pruning, late-move reductions, futility pruning, check extensions, killer moves and a capture-only
quiescence search; piece-square tables rebuilt at every root move from the position (game phase, passed and
isolated pawns, open files, king shelter, king proximity). Search is bounded by node counts, never a clock,
so every run plays the same moves.

## Run it

```sh
MAKEFUN_ENV_URL=http://localhost:8080 python3 main.py
```

MIT licensed.
