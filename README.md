# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Minahichan/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Minahichan/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python: a 0x88 board, negamax
with alpha-beta, a transposition table, killer moves, capture quiescence
and a material + piece-square evaluation, searched to a fixed node
budget so every replay plays the same moves. It talks to the make.fun
env over HTTP (`POST /game`, `POST /move`) and plays the house gauntlet.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

## Tuning notes

- Search budget `BUD=100000` nodes/move (~2.7s per move, under the 10s limit),
  iterative deepening to depth 11.
- Perft is exact: perft(3)=8902, perft(4)=197281.
- Practice Elo 1099 (2W/0D/4L on practice trial-0), below the 1,154 floor.
  The tuning changed no game outcomes on the practice trial.

---

<sub>Entered on [make.fun](https://make.fun/?ref=60xrk087&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
