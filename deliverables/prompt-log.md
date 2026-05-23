---
template: "prompt-log-template"
stage: "Stage 5"
author: "Hiep Tran"
date: "2026-05-24"
company: "Vietnam Dairy Products Joint Stock Company (Vinamilk)"
ticker: "VNM"
exchange: "HOSE"
---

# BUS-629 AI PROMPT LOG & HUMAN-IN-THE-LOOP (HIL) ITERATIONS

This log serves as an authoritative record of all artificial intelligence prompt sessions utilized during the financial analysis of Vinamilk (VNM). It details system prompts, iterative refinements, and manual verification interventions (HIL) to satisfy academic transparency and core course rubrics.

---

## Session 1: Stage 2 — Company Selection Memo
* **Date:** 2026-05-17
* **AI Tool:** Claude 3.5 Sonnet
* **Objective:** Drafting the initial corporate selection rationale and financial hypotheses for Vinamilk.
* **Prompt Structure:** Provided the AI with the raw URL of the instructor's memo template and integrated personal context regarding my role in MBBank's Planning Department and the VEMBA program curriculum.
* **Human-in-the-Loop (HIL) Iteration Note:** The initial AI draft generated open-ended, generic corporate descriptions ("we will see what the ratios show"). I intervened by re-prompting the LLM to strictly format all preliminary observations into directional, falsifiable hypotheses in the strict **"I expect X because Y"** format (e.g., predicting gross margin compression due to global raw milk powder price shifts).

---

## Session 2: Stage 4 — Technical Specification Draft
* **Date:** 2026-05-23
* **AI Tool:** Claude 3.5 Sonnet
* **Objective:** Building a self-contained technical specification linking the Stage 1 model architecture to Stage 3 data points.
* **Inputs Uploaded:** * Master Spec Template URL
  * Stage 1 Empty Template (`performance-ratios-template.xlsx`)
  * Stage 3 Populated Financials (`2026-05-17-tran-vinamilk-financials.xlsx`)
* **Human-in-the-Loop (HIL) Iteration Note:** In the first round, the LLM hallucinated metadata boundaries, failed to append the crucial `_2025` and `_2024` year suffixes to the Balance Sheet named ranges (`BAL_*`), and misallocated the VAS depreciation treatment. I executed a **Round 2 HIL Pass**, forcing the AI to fix the year-end suffixes to protect the Stage 5 execution run, and explicitly instructed it to guide `INC_depreciation = 0` due to the structural bundling of depreciation inside COGS and SG&A under Vietnamese Accounting Standards (VAS).

---

## Session 3: Stage 5 — Analysis Execution & Final Report
* **Date:** 2026-05-24
* **AI Tool:** Claude 3.5 Sonnet
* **Objective:** Running the final ratio report, executing DuPont decomposition, and structural portfolio cleanup.
* **Primary Prompt:** ```text
  Stop the metadata and timeline discussion. This is Stage 5: LLM Analysis Execution. You have already read my Stage 4 Technical Specification and the populated Stage 3 financials for Vietnam Dairy Products Joint Stock Company (Vinamilk - VNM, HOSE). As the Execution LLM, your task right now is to generate the complete, unedited financial analysis report strictly based on that specification. Output the full report inside a single Markdown code block covering all required sections from Part B.