# arxiv submission package: P1

This folder is the unit uploaded to arxiv. Nothing outside the folder is part of the submission.

## Build

```
make pdf       builds paper.pdf locally
make tarball   produces arxiv-p1.tar.gz (the file you upload)
```

## Submission steps (today, 2026-06-17)

1. Confirm `dsarkar3@asu.edu` is registered on arxiv and (if first time) has
   endorsement for `cs.SE`. If endorsement is blocked, change `Primary cat`
   in `metadata.txt` to `cs.LG` and cross-list `cs.SE`.
2. Run `make tarball` to produce `arxiv-p1.tar.gz`.
3. Go to `https://arxiv.org/submit`. Choose "TeX" as the format. Upload the
   tarball.
4. Fill the form using `metadata.txt`. Paste the abstract verbatim.
5. Submit. arxiv assigns an ID within 24 hours.

## After P1's arxiv ID lands

P1 currently cites "Companion paper P2" and "Companion paper P3" as
placeholders (P2 and P3 are not yet on arxiv). After P2 and P3 are
submitted on Tuesday 2026-06-23 and arxiv assigns their IDs, edit P1's
`paper.tex` references section to replace those two placeholders with the
real arxiv IDs, then upload a v2 via arxiv's "replace" flow.

## Files

- `paper.tex` self-contained, all preamble inline.
- `figures/p1_verdicts.pdf` per-kernel verdict bar chart, embedded in §4.
- `figures/p1_cross_gpu.pdf` cross-GPU heatmap, embedded in §4.
- `metadata.txt` arxiv form fields and the abstract text.
- `REFS_VERIFIED.md` the reference verification log for this paper.
- `Makefile` `pdf`, `tarball`, `clean`.

## License

CC-BY 4.0. The notice is rendered under `\maketitle` in `paper.tex`.
