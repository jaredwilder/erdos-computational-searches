# Erdős computational searches

Two exact finite research programs: a large search for radical coincidences in Erdős #850 and a parity reduction with SAT/search data for Erdős #273.

The subject-level repositories are:

- [`erdos850-radical-coincidences`](https://github.com/jaredwilder/erdos850-radical-coincidences)
- [`erdos273-covering-systems`](https://github.com/jaredwilder/erdos273-covering-systems)

This repository retains the combined source code, receipts, and historical computation record.

## Erdős #850 — radical coincidences

The question is whether distinct `x,y` can satisfy

\[
\operatorname{rad}(x+i)=\operatorname{rad}(y+i),
\qquad i=0,1,2.
\]

The recorded exhaustive search finds no such pair with

\[
\boxed{\max(x,y)\le464{,}637{,}500{,}000}.
\]

The computation scanned 539,687,500,000 candidates.

The main prune is the divisor identity

\[
\operatorname{rad}(x(x+1)\cdots(x+k-1))\mid y-x
\]

for any matching length-`k` pair. Since `0<y-x<N`, this sharply restricts the possible radical products before collision testing.

The C implementation is under `erdos850/scripts/`. Independent small-range controls reproduce the expected collision data before the large run is trusted.

A conditional `abc` finiteness route was found to be prior art (Langevin, 1993), so the distinct result here is the finite search frontier and the structural pruning used to reach it.

## Erdős #273 — covering systems

Every permitted modulus has the form `p-1` and is even. Splitting the integers by parity and dividing by two reduces the problem to two disjoint coverings whose half-moduli lie in

\[
H=\{(p-1)/2:p\text{ prime},\ p\ge5\}.
\]

This equivalence underlies the finite SAT ladder.

For a finite rung `N`, an UNSAT certificate means that no solution exists whose original moduli all divide `2N`. Density calculations eliminate fifteen rungs before SAT is needed; the joint two-half instances form the remaining finite search problem in this lane.

The exact reduction, density curve, and corrected search history are now presented in [`erdos273-covering-systems`](https://github.com/jaredwilder/erdos273-covering-systems).

## Scope

The #850 result is an exhaustive finite exclusion through the displayed boundary. The #273 result is an exact reduction plus finite exclusions. Neither computation is extrapolated beyond its proven range.

Author: Jared Wilder. License: Apache-2.0.
