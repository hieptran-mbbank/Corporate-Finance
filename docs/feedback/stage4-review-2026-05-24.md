# Stage 4 review — 2026-05-24

Reviewing the Stage 4 spec at `docs/specs/2026-05-23-tran-vinamilk-spec.md.txt`

## Observations

- **Part A (Model Specification):** All five sections present and fully developed. Data Inputs (Section 3) include every named range with explicit numeric values for both FY2024 and FY2025. Year-suffixed named ranges (`_2025`/`_2024`) used consistently throughout — this eliminates the ambiguity that trips up Stage 5 LLMs.
- **Part A.6–7 (Ratios & Validation):** 29 ratios across all six categories (Performance, Profitability, Efficiency, Leverage, Liquidity, Du Pont) — each with named-range formula. 9 validation rules (V1–V9) including BS balance checks for both years, Du Pont identity, NOPAT reconciliation, and two VAS-specific depreciation checks (V7–V8).
- **Part B (Analysis Specification):** All four sections present. Per-category interpretation guidance with benchmarks tied to Vietnamese dairy/FMCG peer range. Du Pont decomposition specified as a 5-step process with deliberate time-mismatch caveat.
- **Spec craft + prompt log + HIL:** YAML frontmatter documents v1.0 to v1.1 iteration (year-suffix fix + VAS depreciation correction). Prompt log Session 2 details Round-2 re-prompt fixing `BAL_*` year suffixes and `INC_depreciation = 0.00` under VAS.

## Kindly-worded suggestions for improvement

**Stage 4 rubric notes**

- Strong submission — the most thorough spec in the cohort. Nine validation rules (including the VAS `INC_depreciation = 0` check at V7–V8), explicit year-suffixed named ranges throughout, and a detailed v1.0 to v1.1 HIL iteration trail addressing both naming ambiguity and accounting-standard nuance. The four-factor Du Pont decomposition with the deliberate time-mismatch caveat (V4) pre-empts the most common Stage 5 false-positive.
- **Minor filename note:** The spec file on your repo is `2026-05-23-tran-vinamilk-spec.md.txt` — the `.txt` extension prevented the auto-scanner from detecting it. Rename to `.md` for consistency with Stage 5 tooling expectations: `git mv docs/specs/2026-05-23-tran-vinamilk-spec.md.txt docs/specs/2026-05-23-tran-vinamilk-spec.md`.

**Looking ahead to Stage 5**

- **Stage 5 — LLM analysis + manual verification.** Run your Stage 4 spec through the LLM of your choice, then verify at least five of its ratio outputs against the workbook by hand. The polish rubric grades how cleanly the prior four stages tie together as a single deliverable, so revisit your earlier files with fresh eyes.
