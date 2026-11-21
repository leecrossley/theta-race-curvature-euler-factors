# Six values of an extremal prime-race function recover an Euler factor

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24412641.svg)](https://doi.org/10.5281/zenodo.24412641)

This result is now maintained in [theta-host-split-inert-race](https://github.com/leecrossley/theta-host-split-inert-race/tree/main/results/theta-race-curvature-euler-factors). This repository is archived and keeps its releases and DOI.

Fix a rational prime $`p`$. **Six values of a single function of the 547/727 prime race determine the Euler factor at $`p`$ of the primitive product $`\zeta_E/\zeta_F`$.** This includes the conductor primes 2, 547 and 727. The six-value formula uses the known local degree at odd primes. Nine values recover it as well when the degree is left unspecified. [Theorem and reconstruction](PROOF.md)

The measured function at log dilation $`h`$ is the largest limiting symmetric second difference in the width-two race,

```math
C(h)=\limsup_{y\to\infty}\{2S(y)-S(e^h y)-S(e^{-h}y)\}.
```

For an odd prime, take three values near $`\log p`$ and three near $`2\log p`$. A weighted three-point difference isolates each prime power. The recovered integers give the multiplicities in the local denominator. For example, at 31 the denominator is $`(1+T)^8`$ and at 47 it is $`(1-T)^8`$. At 2 it is $`1-T^2`$. [Sampling formula](recover.py) · [Reference values](evidence/curvatures.tsv)

These are values of a limiting extremum. To demonstrate the inversion, the release evaluates them from the explicit prime-power formula. It includes certified enclosures for 81 samples, direct checks against the primitive characters and a precision guarantee for recovering the integers. [Verification output](evidence/check.txt) · [Prior work](PRIOR-WORK.md)

## Replay

In a Python 3.10+ virtual environment run

```sh
python -m pip install -r requirements.txt
python sample_values.py
python recover.py
python independent.py
python check_source.py
```

On x86-64 Linux with Git, curl, tar and zstd, `bash verify-release.sh` also checks the file hashes, upstream records and five local Lean deductions. With Lean 4.33.1 on PATH and a built Mathlib at commit `0df444a360eaa60ab8c11dca51a86af692955474`, run `bash verify-release.sh /path/to/mathlib4`. An optional second argument supplies the directory of the five upstream records. The explicit formula and limiting extremum have written proofs. [Lean deductions](CurvatureEuler.lean) · [File hashes](SHA256SUMS)
