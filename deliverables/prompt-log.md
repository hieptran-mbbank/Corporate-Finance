### Stage 4: Technical Specification Prompt Session
* **Date:** 2026-05-23
* **Tool Used:** Claude 3.5 Sonnet
* **Objective:** Drafting the self-contained Technical Specification for Vinamilk ratio analysis.
* **Human-in-the-Loop (HIL) Iteration Note:** In the first draft, the LLM failed to specify the year-end suffixes (`_2025`/`_2024`) for the `BAL_*` named ranges in Part A.4, and it misallocated the VAS depreciation treatment, which would result in formula errors during Stage 5 execution. I intervened in Round 2, instructing the LLM to apply proper year suffixes and isolate the `INC_depreciation = 0` rule due to COGS/SG&A bundling in Vinamilk's audited VAS financials. The spec was successfully tightened to ensure it stands completely alone.