# arxiv submission package: P4

## Build

```
make pdf       builds paper.pdf locally
make tarball   produces arxiv-p4.tar.gz (the file you upload)
```

## Submission steps (Tuesday 2026-06-23, after P1 has its arxiv ID)

1. Edit `paper.tex` references section. Find "Companion paper P1"
   placeholder and replace with the real `arXiv:<P1-ID>`.
2. Edit `metadata.txt` `Comments:` line to point at P1's arxiv ID.
3. Run `make tarball`. Output: `arxiv-p4.tar.gz`.
4. arxiv submit form: TeX format, upload tarball, fill from `metadata.txt`.

## Files

- `paper.tex` self-contained.
- `figures/p4_cross_gpu.pdf` cross-architecture Delta-perf% heatmap.
- `figures/p4_structural_vs_perf.pdf` single-GPU structural-vs-perf scatter.
- `metadata.txt` arxiv form fields.
- `REFS_VERIFIED.md` reference verification log.

## License

CC-BY 4.0.
