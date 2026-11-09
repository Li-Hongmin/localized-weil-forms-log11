# Cutoff-free positivity of localized Weil forms through the (log 11)/2 threshold

[![verify](https://github.com/Li-Hongmin/localized-weil-forms-log11/actions/workflows/verify.yml/badge.svg)](https://github.com/Li-Hongmin/localized-weil-forms-log11/actions/workflows/verify.yml) [![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.24054983-blue)](https://doi.org/10.5281/zenodo.24054983)

**Hongmin Li** (Institute of Science Tokyo; The University of Tokyo) · ORCID [0000-0003-0228-0600](https://orcid.org/0000-0003-0228-0600)

Main result of the manuscript: a computer-assisted certificate of strict positivity of the complete geometric Weil form in both parity sectors for every support radius 0 < a ≤ (log 11)/2.

- Manuscript on rStation: <https://rstation.ai/problems/riemann_hypothesis/papers/45/v1> (version 1)
- Archived on Zenodo: concept DOI [10.5281/zenodo.24054983](https://doi.org/10.5281/zenodo.24054983) (all versions); this repository mirrors version 1, DOI [10.5281/zenodo.24054984](https://doi.org/10.5281/zenodo.24054984)

## Contents

- `paper/paper.md`, `paper/localized-weil-forms-log11.pdf` — the manuscript (version 1).
- `verification/` — the supplement of that version, unpacked unchanged (except as noted below); its own README describes each file.
- `.github/workflows/verify.yml` — reruns every check below on each push.

## What the programs check

| Check | Command (run inside `verification/`) |
|---|---|
| Frozen endpoint certificate: parameters, pivot counts, strict signs, bundle hashes | `python certificate/verify_frozen_results.py` |
| Interval elimination on the stored Schur matrices | `python verify_retained_core_matrices.py` |
| Prime four-step degree graph (200 cells) | `python certify_log11_prime_four_step_degree.py 256 11` |
| Green-response identities | `python verify_green_response_identities.py` |

The programs check the finite and exact computations used in the manuscript; the mathematical arguments are those written in the paper.

`certificate/verify_frozen_results.py` also hashes `certificate/README.md` of the archived supplement; the CI restores that file from the Zenodo record before running it. An English rendering is in `certificate/README.en.md`.

## Reproducing

```sh
cd verification
pip install numpy==2.5.4 python-flint==0.9.0 sympy==1.14.0
python certificate/verify_frozen_results.py
python verify_retained_core_matrices.py
python certify_log11_prime_four_step_degree.py 256 11
python verify_green_response_identities.py
```

Requirements: Python 3.9+. Run the commands from a copy if you want to keep the recorded outputs untouched.

## Cite

```bibtex
@misc{li2026localizedweilformslog11,
  author    = {Li, Hongmin},
  title     = {Cutoff-free positivity of localized Weil forms through the (log 11)/2 threshold},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.24054983},
  url       = {https://doi.org/10.5281/zenodo.24054983}
}
```

## License

Manuscript and data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Code: MIT (see `LICENSE`). For this repository these licences, granted by the author, replace the earlier notice in `verification/LICENSE.txt`.
