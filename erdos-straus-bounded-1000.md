# Erdős–Straus bounded verification: 2 ≤ n ≤ 1000

**Status:** finite computational result. **Not** a proof of the Erdős–Straus conjecture.

A fresh MSL close session on 2026-09-03 recorded a witness triple for every integer

\[
2\le n\le 1000
\]

for the Erdős–Straus equation

\[
\frac4n=\frac1x+\frac1y+\frac1z.
\]

The frozen session reported:

- all **999** integers in the bounded range covered;
- each witness checked by an exact integer identity rather than floating-point arithmetic;
- a second independent program re-verified full coverage.

The session explicitly corrected an evidentiary wording issue during the run: lack of a Lean transposition did **not** leave this bounded finite claim mathematically open. It only meant the trust envelope was exact finite computation rather than kernel formalization.

This file therefore records only the finite theorem:

> For every integer `n` with `2 ≤ n ≤ 1000`, there exist positive integers `x,y,z` satisfying `4/n = 1/x + 1/y + 1/z`.

No statement about all positive integers is inferred from this bounded verification, and no historical novelty is claimed for the finite range.
