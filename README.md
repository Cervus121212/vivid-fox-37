# tiny-chess v9m — book-first engine

A tiny chess engine for make.fun tiny-chess-01: 0x88 board, alpha-beta +
quiescence search, PeSTO tapered evaluation, transposition table, killer
moves, and an 8-entry opening book built from Stockfish-oracle probes of our
own trial losses (Catalan + Semi-Slav lines) — 6 entries from the fresh
probe, plus 2 from the real trial transcripts (Catalan O-O, Semi-Slav bxc3).

- `main.py` — the whole engine, LZMA-packed, 3,888 bytes (limit 4,096).
- Book: positions are keyed by the low 12 bits of the engine's Zobrist
  hash; a book move plays instantly, before any search.
- No search change vs the no-book base: the only difference is the book.

Built and trialled locally with the make.fun kit (level 27).
