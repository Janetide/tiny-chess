# TinyChess 4K

A compact chess engine written from scratch for the [tiny-chess-01](https://make.fun) bounty: the whole program fits in 4,096 bytes.

It plays with a 0x88 board, negamax search with principal-variation search, a transposition table, killer moves, and a capture-only quiescence search with check evasions. The evaluation is a single formula-based piece-square table set plus material. Every move comes from a fixed node budget, so play is fully deterministic and reproducible.

## Run

```sh
python3 -P -s main.py
```

The engine speaks the trial environment protocol (`MAKEFUN_ENV_URL`): it asks for the current game, picks a move, and posts it back. No network access beyond the environment, no model calls, no clock in the search.

## Layout

- `main.py` — the engine (compressed payload; the readable source is developed in-session and packed with lzma + base85).
- `LICENSE` — MIT.
