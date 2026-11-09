# log 11 two-parity cutoff-free application certificate (English rendering)

This is an English rendering of `certificate/README.md` of the archived supplement.

Fixed parameters: `a = log(11)/2, K = 400, N = 500, R = 280, F = [500, 850), q_f = 8000, Arb 256-bit`.
Starting from an empty `scratch/`, each parity generates the safe base, the verified graph, the clean contracted base and the complete Yukawa/Parseval family, and then runs the sharp checker. The large parent matrices live only in the unversioned `scratch/`; their hashes are in `PARENT-SHA256.txt`. This bundle keeps the actual sources, the per-stage logs and the final small interval results.

The checker constructs
`G = P0 + RP/t400 + BF*BF.T - G1 - (Rtot - R1)/t8000`, where
`Rtot = RP + XF*BF.T + BF*XF.T + BF*GQ*BF.T`, and builds `U_q = c_q + BF*v_q` term by term.
The generator keeps the odd negative polar term; the family exporter stores all `cross` and `gram_q`.
The trigamma series makes `t_q` strictly increasing, and both fresh values `t400` are strictly positive; `Rtot - R1` is the Parseval Gram of the remaining `U_q U_q^*`, so the tail weight has the correct direction.

even: smallest pivot lower bound of the 393-dimensional complement block about `0.04079956`; final core pivot lower bound about `3.6824e-50`.
odd: smallest pivot lower bound of the 394-dimensional complement block about `0.00733669`; final core pivot lower bound about `3.6435e-45`.
All are strictly positive. This bundle certifies only the log 11 two-parity application to the infinite-dimensional form; it does not prove RH.

The checker's success condition requires exactly 7 (even) / 6 (odd) core pivots, each with strictly positive interval lower bound; a negative pivot or a pivot interval containing zero exits with nonzero status. The lightweight frozen results can be checked with `python verify_frozen_results.py` (parameters, pivot counts, strict signs and bundle hashes).

The manifest check compares the fixed list of 21 expected relative paths before hashing: the list must have exactly 21 entries, no duplicates, and equal the expected set. An empty manifest, a 20-entry manifest, or one padded with duplicates therefore fails; only then is SHA-256 computed file by file.
