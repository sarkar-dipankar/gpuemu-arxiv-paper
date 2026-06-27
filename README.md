# gpuemu arXiv preprints

Sources for four short empirical papers on GPU kernel correctness. Each
subdirectory is a self-contained arXiv submission package: LaTeX source,
BibTeX bibliography, figures, and a `Makefile` that builds the PDF and
the upload tarball.

| Folder | Title | Pages | arXiv |
|---|---|---:|---|
| [`p1/`](p1/) | The Correctness Illusion in LLM-Generated GPU Kernels | 10 | [arXiv:2606.20128](https://arxiv.org/abs/2606.20128) |
| [`p2/`](p2/) | Operator-Aware Mixed-Precision Tolerance Calibration for Tensor Kernels | 7 | pending |
| [`p3/`](p3/) | Test-Input Generation for Tensor Programs: What Actually Finds Kernel Bugs | 8 | pending |
| [`p4/`](p4/) | Static PTX Metrics Track Structural Kernel Regressions but Miss Semantic Ones | 9 | pending |

All four are released under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## Author

Dipankar Sarkar, Arizona State University. ORCID
[`0000-0001-5431-6367`](https://orcid.org/0000-0001-5431-6367).
Email: [dsarkar3@asu.edu](mailto:dsarkar3@asu.edu).

## Reproducibility

The corpus, the experiment drivers, the analysis scripts that produce
every table and figure, and the replay tool that fetches each cited run
record from object storage are all in the public
[`sarkar-dipankar/gpuemu-corpus`](https://github.com/sarkar-dipankar/gpuemu-corpus)
package. The validator daemon is at
[`Skelf-Research/gpuemu`](https://github.com/Skelf-Research/gpuemu).

## Build any paper

```bash
cd p1   # or p2, p3, p4
make pdf      # builds paper.pdf
make tarball  # produces arxiv-pN.tar.gz for upload to arXiv
```

Each folder has its own `README.md` with a submission checklist, a
`metadata.txt` listing the exact arXiv form fields (title, abstract,
categories, ACM class, comments), and a `REFS_VERIFIED.md` recording
per-reference verification.

## How the four papers relate

P1 is the foundational study. It establishes that the field-standard
fixed-shape `allclose`-style oracle systematically misses LLM-style
transcription bugs. The other three depend on it.

P2 addresses the tolerance question: given the oracle, what value of
`atol` does the kernel itself justify? Calibrated atol lifts overall pass
rate on the 26-entry corpus from 73.2% to 82.4% (+9.3pp), with control
false-positive count rising from 0 to 20 out of 1,882 (+1.1pp).

P3 addresses the input-generation question: it ablates seven strategies
and reports each on two axes (bug recall, control false-positive rate).
Boundary shape sampling is the operationally safe winner at 78% recall
and 0% control FP. Adversarial value sampling reaches 99% recall but
inflates control FP to 94% under the current validator.

P4 addresses the cheap-static-gate question: it pairs PTX metrics with
CUDA-event timing across five GPU classes. Static PTX deltas separate
structural from semantic kernel changes and transfer identically across
the tested GPUs. Measured runtime deltas at sub-millisecond scale do
not.

P1 went live on arXiv on 2026-06-18 as
[arXiv:2606.20128](https://arxiv.org/abs/2606.20128). P2, P3, P4 are
the next batch. Each of those cites P1 by its arXiv ID. After all four
land, P1 will receive a v2 replace update with the three companion IDs.
