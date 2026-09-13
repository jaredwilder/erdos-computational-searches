# erdos-computational-searches

**An exhaustion frontier at 464,637,500,000 for Erdős 850 and an exact parity-split reduction for
Erdős 273**, with full receipts, source code, controls, and prior-art reconciliation.

Author: Jared Wilder. First public timestamp: 2026-09-10.

## Focused problem repositories

The two research programs now have their own reading surfaces, with exact
source copies, mathematical summaries, controls and correction history:

- [Erdős #850: radical coincidences](https://github.com/jaredwilder/erdos850-radical-coincidences)
- [Erdős #273: covering systems](https://github.com/jaredwilder/erdos273-covering-systems)

Use those repositories to follow either problem. This combined repository
retains the original public research record.


## Erdős 850 — radical coincidences

Question: do there exist `x != y` with `rad(x+i) = rad(y+i)` for `i = 0,1,2`?

**Computed result: no witness pair with `max(x,y) <= 464,637,500,000`.** The run scanned
**539,687,500,000 candidates** and records verdict `NO_WITNESS_TO_FRONTIER`.

The search uses a difference-lemma prune. For a witness,

`L_k(n) = rad(n ... n+k-1)`

must divide `y-x`, and `L_k(x)=L_k(y)`; with `x<y<=N`, this forces `L_k(n)` into a small range.
Collisions are detected globally across all segments in one sorted structure. Source is the C sieve
under `erdos850/scripts/`. Controls reproduce an earlier independent brute force to 30,000,000.

### Scope of the computation

The quantified statement established here is exactly the finite frontier above. The receipt carries
that boundary explicitly; values beyond it are not inferred from the exhaustion.

### Prior-art reconciliation

`erdos850/abc/PRIOR-ART-VERDICT-2026-09-02.md` records that the conditional theorem the campaign was
about to formalize — that `abc` implies only finitely many such pairs — was already published by
Langevin (1993), with later restatements. The campaign therefore records that route as a correct
rediscovery and did not spend a Lean formalization on it.

That prior-art result is separate from the much larger finite search frontier above.

## Erdős 273 — covering systems

The repository records an **exact parity-split reduction** to two disjoint distinct-moduli coverings
drawn from

`H = {(p-1)/2}`.

`erdos273/DENSITY-CURVE.md` carries the density curve, ladder table, and CNF encodings.

The finite semantics are explicit: UNSAT at `N` means no covering exists with all moduli dividing
`2N`. Fifteen ladder rungs die by density; the joint two-half CNFs remain the unresolved finite
subproblem in this lane.

A correction is also preserved for an earlier claimed 600-second failure whose instance had never
actually been built.

## Evidence package

Both lanes publish the search code, receipts, exact finite boundary, controls, and route history.
The mathematical claims are therefore the frontier and reduction stated above, not stronger
unquantified conclusions.

## License

Apache-2.0.
