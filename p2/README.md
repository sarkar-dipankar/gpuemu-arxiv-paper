# arxiv submission package: P2

This folder is the unit uploaded to arxiv. Do not upload anything outside it.

## Build

```
make pdf       builds paper.pdf locally
make tarball   produces arxiv-p2.tar.gz (the file you upload)
```

## Submission steps (Tuesday 2026-06-23, after P1 has its arxiv ID)

1. Edit `paper.tex` references section. Find the "Companion paper P1"
   placeholder and replace it with the real `arXiv:<P1-ID>`.
2. Edit `metadata.txt` `Comments:` line to point at P1's arxiv ID.
3. Run `make tarball`. Output: `arxiv-p2.tar.gz`.
4. Go to `https://arxiv.org/submit`. Format: TeX. Upload the tarball.
5. Fill the form using `metadata.txt`.
6. Submit.

## Files

- `paper.tex` self-contained, all preamble inline.
- `figures/p2_tightening.pdf` per-(op, dtype) tightening factor figure.
- `metadata.txt` arxiv form fields.
- `REFS_VERIFIED.md` reference verification log.
- `Makefile` build helper.

## License

CC-BY 4.0.
