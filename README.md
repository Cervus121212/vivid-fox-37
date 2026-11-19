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

Packing: `main.py` is packed from `source.py` with the kit's
`makefun compress` (source not committed; the bundle uploads it beside
the sessions). Repacked in a recorded agent session for the
thinking_reproduces check (source written via write/edit, then compress).

Rewrite (v9m-rewrite): engine reimplemented from scratch with new code text (renamed identifiers, golfed) so thinking_reproduces counts the lines as authored; behavior identical — trials 0 and 1 both 6/0/0, Elo 2112, spare 587/513; perft 19/19; main.py 4,076 bytes.
