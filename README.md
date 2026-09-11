# erdos-computational-searches

Two computational attacks on open Erdos problems that produced **bounds and a reduction, not
closures**, published with their full receipts, their source code, and their own negative results.

Author: Jared Wilder. First public timestamp: 2026-09-10.

## Erdos 850 - radical coincidences

Question: do there exist x != y with rad(x+i) = rad(y+i) for i = 0, 1, 2?

**Result: no witness pair with max(x, y) <= 464,637,500,000.** 539,687,500,000 candidates
scanned. Verdict in the master receipt is `NO_WITNESS_TO_FRONTIER`.

The receipt states its own limit and this README repeats it verbatim:

> Exhaustion to N is COMPUTATION evidence of a bound, NEVER closure of the negative branch.
> Only a verified witness closes anything.

Method: a difference-lemma prune. For a witness, L_k(n) = rad(n..n+k-1) divides y - x and
L_k(x) = L_k(y), which with x < y <= N forces L_k(n) to be small. Collisions are detected
globally across all segments in one sorted structure, not per segment. Source is the C sieve in
`erdos850/scripts/`. Controls reproduced a prior independent brute force to 30,000,000.

**A negative result is included and it is the honest headline of this lane.**
`erdos850/abc/PRIOR-ART-VERDICT-2026-09-02.md` records that the conditional theorem this campaign
was about to formalize - that abc implies only finitely many such pairs - is **already published**:
Langevin 1993, restated 1996 and 2016, and stated on the Erdos 850 problem page itself. The
verdict is `RECORDED`, the Lean work was **not** run, and the file says in its own words: *"Our
sketch is a correct rediscovery, not a discovery."*

## Erdos 273 - covering systems

An exact parity-split reduction: two disjoint distinct-moduli coverings drawn from
H = {(p-1)/2}. `erdos273/DENSITY-CURVE.md` carries the density curve, the ladder table, and the
CNF encodings.

**Semantics, fixed and repeated in every receipt:** UNSAT at N means no covering exists with all
moduli dividing 2N. That is a bound. **It is never a refutation of the problem.**

Recorded honestly in this lane: fifteen ladder rungs died by density, the joint two-half CNFs did
not settle, and a correction is on the record that an earlier claim about a 600 second failure had
no receipt because the instance had never been built.

## What neither of these is

Neither closes its problem. Both are open. What is published here is the search, the code, the
receipts, the exact frontier reached, and the places the approach failed.

## License

Apache-2.0.
