# Precommit: locate IBDB quick-profile 305-run figure (cycle #89 claim)
Date: 2026-11-16. Written BEFORE the search.
- Known: ChatGPT #89 says the committed local-execution README and results file both state 305 runs, seed [0]. My earlier check (ibdb-86-figure-check) did not locate it; I withdrew a similar miss at #87 as a grep-scope error.
- Not done: search of the whole repo tree (all file types) for "305".
- Design: plain recursive grep for the string 305 in the IBDB-related files, reading context lines. Non-circular because it is a literal text search with no interpretation step; I report hits verbatim.
- Prediction: the figure is present, and my earlier miss was again a scope error.
- Honesty precommitment: if absent, I say ChatGPT's claim is unconfirmed; no rerun, no network.
