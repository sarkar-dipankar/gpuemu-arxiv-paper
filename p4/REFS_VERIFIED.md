# P4 reference verification log

Verified 2026-06-17. Consolidated log: `papers/REFERENCES_VERIFIED.md`.

| # | Status | Notes |
|---|---|---|
| 1 | VERIFIED | Low Overhead Instruction Latency Characterization for NVIDIA GPGPUs / Arafa et al., 2019. https://arxiv.org/abs/1905.08778 |
| 2 | VERIFIED | rNdN / Krolik, Verbrugge, Hendren, TACO 2023. https://dl.acm.org/doi/10.1145/3603503 |
| 3 | VERIFIED | NVIDIA Developer Forums, Understanding PTXAS output. |
| 4 | VERIFIED | RegDem / Sakdhnagool, Sabne, Eigenmann, 2019. https://arxiv.org/abs/1907.02894 |
| 5 | FIXED | Triton (Tillet, Kung, Cox), MAPL 2019. Added DOI 10.1145/3315508.3329973. Was URL-less. |
| 6 (was 7) | PLACEHOLDER | Companion paper P1. Replace with arxiv ID on Tuesday. |

## Dropped

- Old ref 6 (CUTLASS) was a blog post (https://maknee.github.io/blog/2025/Maybe-Consider-Putting-Cutlass-In-Your-CUDA-Kernels/) whose content is a ptxas naming-trick triggered by the substring "cutlass" in kernel names. It is not a CUTLASS-library tutorial, contrary to the citation. **Dropped**, and the sentence in §2 that mentioned it ("Library-level wrappers (e.g. CUTLASS [6]) further trade off register pressure against tiling.") was edited to remove the parenthetical. Old ref 7 (Companion P1) renumbers to ref 6.

## Summary

- 4 verified as-is.
- 1 fixed (Triton DOI added).
- 1 dropped + sentence trimmed (CUTLASS blog content mismatch).
- 1 placeholder for companion P1.
- Net: 6 references in P4 (was 7).
