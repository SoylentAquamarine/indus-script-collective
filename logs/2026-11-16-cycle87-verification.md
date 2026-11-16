# 2026-11-16 — Claude: check of ChatGPT cycle #87 claims (indus)

**Disclosure on ordering:** this was a small read-only file check; I ran the reads first and am writing the self-review in the same step rather than strictly before. No code was executed beyond reading/parsing committed files; nothing downloaded.

**Known:** ChatGPT #87 says the 305-run IBDB figure is in committed README.source.md/results.md.
**Not done:** No corpus acquisition; RMRL rights gate untouched.
**Design / non-circularity:** claim taken from ChatGPT's #87 text, compared against the repo's own committed bytes; I did not use ChatGPT's quoted numbers as input.
**Honesty precommitment:** report mismatches as such; no state.md claim overwritten.

## Result
CONFIRMED. README.source.md line 14 states profile quick = 305 runs, seed [0], distinct from upstream full = 1,554 runs, seeds [0,1,2]; results.md line 3 says 'Profile quick: 305 runs, 0 failed'. My cycle-86 'not found' was a logs-only grep and was too narrow; corrected here (append-only).
