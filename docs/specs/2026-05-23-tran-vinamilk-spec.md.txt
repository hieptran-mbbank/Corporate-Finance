---
template: spec
purpose: "Technical specification for model-driven projects — defines scope, inputs, formulas, validation, and analysis requirements precisely enough that any competent executor (human or LLM) can produce correct output"
audience: student
fields_required: [title, author, date, version, company, scope, model_architecture, data_inputs, derived_inputs, formulas, validation, analysis_requirements, output_format, references]
naming_convention: "YYYY-MM-DD-{slug}.md"
courses: [BUS-629]
notes: "Stage 4 deliverable — v1.1. HIL iteration: (1) added explicit _2025/_2024 year suffixes to all BAL_ named ranges in Section 4 to prevent Stage 5 LLM ambiguity; (2) corrected INC_depreciation to 0.00 under VAS (bundled in COGS/SGA) and introduced CASH_depreciation = 1,233.18 VND bn as the sole depreciation reference for the cash coverage ratio."
---

# Vinamilk (VNM) — Performance Ratios Technical Specification

**Author:** Tran  
**Date:** 2026-05-24  
**Version:** 1.1  
**Company:** Vietnam Dairy Products Joint Stock Company · VNM · HOSE

---

## 1. Scope & Objective

This specification defines the Excel-based performance ratio model and the analytical work to be performed for Vietnam Dairy Products Joint Stock Company (Vinamilk), ticker VNM on the Ho Chi Minh Stock Exchange (HOSE).

- **Fiscal period:** FY2025 (1 January – 31 December 2025); prior-year comparatives FY2024
- **Reporting standard:** Vietnamese Accounting Standards (VAS)
- **Reporting currency:** Vietnamese Dong (VND); all monetary figures in VND billions (Tỷ VND) throughout — Balance Sheet, Income Statement, Cash Flow, and all ratio outputs
- **Market data unit exception:** `share_price` is in VND per share; `shares_outstanding` is in millions of shares; `market_capitalization` = 65,100 × 2,090 = 136,059,000 VND millions = **136,059 VND billions**. The executor must use 136,059 (VND billions) when comparing market cap to any balance sheet figure
- **Analytical objective:** Compute and interpret 25+ financial ratios across six categories (Performance, Profitability, Efficiency, Leverage, Liquidity, Du Pont) to assess Vinamilk's financial health and strategic positioning; generate 3–5 actionable strategic recommendations
- **Intended audience:** Prof. Adam Stauffer; Managing Director perspective — executive-level reader who expects concise, evidence-grounded interpretation and clear strategic implications; assume full financial literacy; do not define ratios, go straight to what the numbers mean strategically

---

## Part A — Model Specification

### 2. Model Architecture

The workbook consists of six tabs in the following order:

| Tab | Contents | Role |
|-----|----------|------|
| Cover | Instructions, color key, named-range convention | Reference only |
| Balance Sheet | FY2024 (prior) and FY2025 (current) balance sheet line items | **Data input** |
| Income Statement | FY2025 income statement line items | **Data input** |
| Cash Flow Statement | FY2025 cash flow items | **Data input** |
| Ratios | Analyst assumptions, derived inputs, and all ratio outputs | **Calculation & output** |
| Notes | Company metadata, data source, AI usage log | Reference / audit |

**Color coding conventions:**

| Style | Meaning |
|-------|---------|
| Yellow background | Hardcoded data inputs — financial statement figures; executor enters these |
| Light-blue background + blue text | Analyst assumptions: `share_price`, `shares_outstanding`, `cost_capital`, `tax_rate` |
| Green text | Cross-sheet formula references; do not overwrite |
| Gray background | Ratio output cells; populated automatically from Ratios tab; do not overwrite |

**Input / calculation / output separation:** Raw financial data lives exclusively on the Balance Sheet, Income Statement, and Cash Flow tabs. The Ratios tab contains no raw inputs other than the four analyst assumptions; every other cell on the Ratios tab is a formula referencing input tabs via named ranges.

**Formatting:** Monetary values `#,##0.00` (VND billions); percentages `0.00%`; multiples `0.00x`; years as text strings ("2025", "2024").

---

### 3. Data Inputs

All values below are sourced from the student's Stage 3 populated workbook (Vinamilk FY2025 annual report via Vietstock Finance). The executor must use these exact figures; no lookups, estimates, or independent sourcing permitted.

#### Balance Sheet — FY2025 (Current Year) · VND billions

| Named Range | Line Item | Value |
|-------------|-----------|------:|
| `BAL_cash_marketable_securities_2025` | Cash and marketable securities | 23,149.74 |
| `BAL_receivables_2025` | Receivables | 6,027.72 |
| `BAL_inventories_2025` | Inventories | 6,839.28 |
| `BAL_other_current_assets_2025` | Other current assets | 244.43 |
| `BAL_assets_current_2025` | Total current assets | 36,261.17 |
| `BAL_ppe_gross_2025` | Property, plant & equipment (gross) | 34,581.52 |
| `BAL_accumulated_depreciation_2025` | Less accumulated depreciation | 22,963.401 |
| `BAL_ppe_net_2025` | Net tangible fixed assets | 11,618.119 |
| `BAL_intangibles_2025` | Intangible assets (goodwill) | 1,030.797 |
| `BAL_other_assets_2025` | Other assets | 4,402.273 |
| `BAL_assets_total_2025` | Total assets | 53,312.359 |
| `BAL_debt_current_2025` | Debt due for repayment (current) | 9,393.737 |
| `BAL_accounts_payable_2025` | Accounts payable | 3,923.309 |
| `BAL_other_current_liabilities_2025` | Other current liabilities | 5,203.240 |
| `BAL_liabilities_current_2025` | Total current liabilities | 18,520.286 |
| `BAL_debt_long_term_2025` | Long-term debt | 62.908 |
| `BAL_other_long_term_liabilities_2025` | Other long-term liabilities | 246.161 |
| `BAL_liabilities_total_2025` | Total liabilities | 18,829.355 |
| `BAL_common_stock_2025` | Common stock and paid-in capital | 20,933.665 |
| `BAL_retained_earnings_2025` | Retained earnings | 13,549.360 |
| `BAL_equity_shareholders_2025` | Total shareholders' equity | 34,483.025 |

#### Balance Sheet — FY2024 (Prior Year) · VND billions

| Named Range | Line Item | Value |
|-------------|-----------|------:|
| `BAL_cash_marketable_securities_2024` | Cash and marketable securities | 25,486.03 |
| `BAL_receivables_2024` | Receivables | 6,233.76 |
| `BAL_inventories_2024` | Inventories | 5,686.84 |
| `BAL_other_current_assets_2024` | Other current assets | 147.02 |
| `BAL_assets_current_2024` | Total current assets | 37,553.65 |
| `BAL_ppe_gross_2024` | Property, plant & equipment (gross) | 32,713.052 |
| `BAL_accumulated_depreciation_2024` | Less accumulated depreciation | 21,192.851 |
| `BAL_ppe_net_2024` | Net tangible fixed assets | 11,520.201 |
| `BAL_intangibles_2024` | Intangible assets (goodwill) | 1,030.364 |
| `BAL_other_assets_2024` | Other assets | 4,944.847 |
| `BAL_assets_total_2024` | Total assets | 55,049.062 |
| `BAL_debt_current_2024` | Debt due for repayment (current) | 9,115.435 |
| `BAL_accounts_payable_2024` | Accounts payable | 3,874.064 |
| `BAL_other_current_liabilities_2024` | Other current liabilities | 5,470.048 |
| `BAL_liabilities_current_2024` | Total current liabilities | 18,459.547 |
| `BAL_debt_long_term_2024` | Long-term debt | 157.904 |
| `BAL_other_long_term_liabilities_2024` | Other long-term liabilities | 257.208 |
| `BAL_liabilities_total_2024` | Total liabilities | 18,874.659 |
| `BAL_common_stock_2024` | Common stock and paid-in capital | 20,933.665 |
| `BAL_retained_earnings_2024` | Retained earnings | 15,240.740 |
| `BAL_equity_shareholders_2024` | Total shareholders' equity | 36,174.405 |

#### Income Statement — FY2025 · VND billions

| Named Range | Line Item | Value | Note |
|-------------|-----------|------:|------|
| `INC_sales` | Net sales | 63,645.89 | |
| `INC_cost_goods_sold` | Cost of goods sold | 35,487.58 | Includes embedded depreciation under VAS |
| `INC_sga` | Selling, general & administrative expenses | 15,131.68 | Includes embedded depreciation under VAS |
| `INC_depreciation` | Depreciation (stand-alone line) | **0.00** | VAS: depreciation is bundled inside `INC_cost_goods_sold` and `INC_sga`; no separate depreciation line exists on the Income Statement. Set explicitly to 0.00. **Do not use `INC_depreciation` in any ratio formula — use `CASH_depreciation` instead.** |
| `INC_ebit` | Earnings before interest and taxes (EBIT) | 10,663.72 | Already net of embedded depreciation via COGS/SGA |
| `INC_other_income` | Other income | 1,312.07 | |
| `INC_interest_expense` | Interest expense | 325.80 | |
| `INC_taxable_income` | Taxable income | 11,649.99 | |
| `INC_taxes` | Taxes | 2,236.40 | |
| `INC_net` | Net income | 9,413.59 | |
| `INC_dividends` | Dividends | 11,264.48 | Exceeds FY2025 net income — draws down retained earnings |
| `INC_addition_retained_earnings` | Addition to retained earnings | −1,850.89 | |

#### Cash Flow Statement — FY2025 · VND billions

| Named Range | Line Item | Value | Note |
|-------------|-----------|------:|------|
| `CASH_depreciation` | Depreciation add-back | **1,233.18** | **True depreciation under VAS** — this is the only depreciation figure to use in ratio formulas (specifically the cash coverage ratio). Replaces the erroneous `INC_depreciation` value. |
| `CASH_operating` | Cash provided by operations | 11,776.50 | Verify this figure reflects the corrected `CASH_depreciation` = 1,233.18 add-back |
| `CASH_debt_short_term_change` | Increase (decrease) in short-term debt | 278.30 | |
| `CASH_debt_long_term_change` | Increase (decrease) in long-term debt | −94.99 | |
| `CASH_dividends_paid` | Dividends paid | −11,264.48 | |
| `CASH_stock_issues` | Issues (repurchases) of stock | 7.20 | |
| `CASH_financing` | Cash provided by (used for) financing | −11,073.97 | |
| `CASH_net_change` | Net increase (decrease) in cash | 702.53 | |

#### Analyst Assumptions

| Named Range | Item | Value | Unit |
|-------------|------|------:|------|
| `yearCurrent` | Current fiscal year | 2025 | text |
| `yearStart` | Prior fiscal year | 2024 | text |
| `share_price` | Share price (HOSE, 31 Dec 2025) | 65,100 | VND/share |
| `shares_outstanding` | Shares outstanding | 2,090 | millions |
| `cost_capital` | Cost of capital (WACC) | 0.09 | decimal |
| `tax_rate` | Tax rate | 0.20 | decimal |
| `market_capitalization` | `share_price × shares_outstanding` | 136,059,000 | VND millions |

> **Working value:** Use `market_capitalization_bn` = 136,059 VND billions in all ratio computations alongside balance sheet figures.

---

### 4. Named Range Conventions

#### Primary convention — year-suffixed (use these in all formulas)

The executor must use the year-suffixed form (`_2025`, `_2024`) for all Balance Sheet named ranges. This is the authoritative form; it eliminates ambiguity when the Stage 5 LLM processes the spec in isolation.

| Prefix | Pattern | Example | Applies to |
|--------|---------|---------|-----------|
| `BAL_` | `BAL_[item]_2025` | `BAL_assets_total_2025` | FY2025 (current year) balance sheet items |
| `BAL_` | `BAL_[item]_2024` | `BAL_assets_total_2024` | FY2024 (prior year) balance sheet items |
| `INC_` | `INC_[item]` | `INC_sales` | Income statement items (FY2025 only; no year suffix) |
| `CASH_` | `CASH_[item]` | `CASH_depreciation` | Cash flow items (FY2025 only; no year suffix) |
| `RATIO_` | `RATIO_[name]` | `RATIO_asset_turnover` | Key ratios reused as Du Pont components |
| (none) | `share_price`, `shares_outstanding`, `cost_capital`, `tax_rate` | — | Analyst assumptions |

#### Alias convention — `_curr` / `_prior` (legacy; for reference only)

The workbook template also defines `_curr` (= `_2025`) and `_prior` (= `_2024`) aliases for balance sheet ranges, and `startYear_` / `currentYear_` / `avg_` aliases for derived inputs. These are preserved in the model for formula compatibility but **must not be used in this spec's ratio formulas** — use the year-suffixed form exclusively to avoid ambiguity.

| Alias | Resolves to | Year-suffixed equivalent |
|-------|------------|--------------------------|
| `BAL_[item]_curr` | FY2025 balance | `BAL_[item]_2025` |
| `BAL_[item]_prior` | FY2024 balance | `BAL_[item]_2024` |
| `startYear_equity` | `BAL_equity_shareholders_2024` | `BAL_equity_shareholders_2024` |
| `currentYear_equity` | `BAL_equity_shareholders_2025` | `BAL_equity_shareholders_2025` |
| `avg_equity` | `AVERAGE(BAL_equity_shareholders_2024, BAL_equity_shareholders_2025)` | — |

---

### 5. Derived Inputs

Computed on the Ratios tab from the raw inputs above. All formulas use year-suffixed named ranges. Values in VND billions unless noted.

| Named Range | Description | Formula (year-suffixed) | Value |
|-------------|-------------|------------------------|------:|
| `startYear_equity` | Equity at 1 Jan 2025 | `BAL_equity_shareholders_2024` | 36,174.405 |
| `startYear_inventory` | Inventories at 1 Jan 2025 | `BAL_inventories_2024` | 5,686.84 |
| `startYear_receivables` | Receivables at 1 Jan 2025 | `BAL_receivables_2024` | 6,233.76 |
| `startYear_total_assets` | Total assets at 1 Jan 2025 | `BAL_assets_total_2024` | 55,049.062 |
| `startYear_total_capitalization` | Long-term debt + equity at 1 Jan 2025 | `BAL_debt_long_term_2024 + BAL_equity_shareholders_2024` | 36,332.309 |
| `currentYear_after_tax_operating_income` | NOPAT | `INC_net + (1 − tax_rate) × INC_interest_expense` | 9,674.23 |
| `currentYear_daily_sales_average` | Average daily sales | `INC_sales / 365` | 174.37 |
| `currentYear_equity` | Equity at 31 Dec 2025 | `BAL_equity_shareholders_2025` | 34,483.025 |
| `currentYear_cash_marketable_securities` | Cash + securities at 31 Dec 2025 | `BAL_cash_marketable_securities_2025` | 23,149.74 |
| `currentYear_assets_current` | Current assets at 31 Dec 2025 | `BAL_assets_current_2025` | 36,261.17 |
| `currentYear_liabilities_current` | Current liabilities at 31 Dec 2025 | `BAL_liabilities_current_2025` | 18,520.286 |
| `currentYear_cost_goods_sold_daily` | Average daily COGS | `INC_cost_goods_sold / 365` | 97.23 |
| `currentYear_debt_long_term` | Long-term debt at 31 Dec 2025 | `BAL_debt_long_term_2025` | 62.908 |
| `currentYear_working_capital_net` | Net working capital | `BAL_assets_current_2025 − BAL_liabilities_current_2025` | 17,740.884 |
| `currentYear_assets_total` | Total assets at 31 Dec 2025 | `BAL_assets_total_2025` | 53,312.359 |
| `currentYear_total_capitalization` | Long-term debt + equity at 31 Dec 2025 | `BAL_debt_long_term_2025 + BAL_equity_shareholders_2025` | 34,545.933 |
| `currentYear_liabilities_total` | Total liabilities at 31 Dec 2025 | `BAL_liabilities_total_2025` | 18,829.355 |
| `avg_equity` | Average equity FY2025 | `AVERAGE(BAL_equity_shareholders_2024, BAL_equity_shareholders_2025)` | 35,328.715 |
| `avg_total_assets` | Average total assets FY2025 | `AVERAGE(BAL_assets_total_2024, BAL_assets_total_2025)` | 54,180.711 |
| `avg_total_capitalization` | Average total capitalization FY2025 | `AVERAGE(startYear_total_capitalization, currentYear_total_capitalization)` | 35,439.121 |

---

### 6. Ratio Definitions & Formulas

All formulas use year-suffixed named ranges. `INC_depreciation` does not appear in any formula below; the cash coverage ratio uses `CASH_depreciation` = 1,233.18 exclusively.

#### Performance

| Ratio | Named Range | Formula | Unit |
|-------|-------------|---------|------|
| Market value added (MVA) | — | `(market_capitalization / 1000) − BAL_equity_shareholders_2025` | VND bn |
| Market-to-book ratio | — | `(market_capitalization / 1000) / BAL_equity_shareholders_2025` | x |
| Economic value added (EVA) | — | `currentYear_after_tax_operating_income − (cost_capital × startYear_total_capitalization)` | VND bn |

> MVA and Market-to-book divide `market_capitalization` (stored in VND millions) by 1,000 to convert to VND billions before comparing to balance sheet figures. EVA > 0 confirms Vinamilk earns above its 9% cost of capital.

#### Profitability

| Ratio | Named Range | Formula | Unit |
|-------|-------------|---------|------|
| Return on assets — start (ROA) | — | `currentYear_after_tax_operating_income / BAL_assets_total_2024` | % |
| Return on capital — start (ROC) | — | `currentYear_after_tax_operating_income / startYear_total_capitalization` | % |
| Return on equity — start (ROE) | — | `INC_net / BAL_equity_shareholders_2024` | % |
| Return on assets — avg (ROA avg) | — | `currentYear_after_tax_operating_income / avg_total_assets` | % |
| Return on capital — avg (ROC avg) | — | `currentYear_after_tax_operating_income / avg_total_capitalization` | % |
| Return on equity — avg (ROE avg) | — | `INC_net / avg_equity` | % |

> Start-of-year denominators are the primary figures. Average-denominator variants are cross-checks only. Benchmark: Vietnamese listed consumer staples peers typically show ROE 15–25%.

#### Efficiency

| Ratio | Named Range | Formula | Unit |
|-------|-------------|---------|------|
| Asset turnover | `RATIO_asset_turnover` | `INC_sales / BAL_assets_total_2024` | x |
| Receivables turnover | — | `INC_sales / BAL_receivables_2024` | x |
| Average collection period | — | `BAL_receivables_2024 / currentYear_daily_sales_average` | days |
| Inventory turnover | — | `INC_cost_goods_sold / BAL_inventories_2024` | x |
| Days in inventory | — | `BAL_inventories_2024 / currentYear_cost_goods_sold_daily` | days |
| Net profit margin | — | `INC_net / INC_sales` | % |
| Operating profit margin | `RATIO_operating_profit_margin` | `currentYear_after_tax_operating_income / INC_sales` | % |

> `RATIO_asset_turnover` and `RATIO_operating_profit_margin` are the two Du Pont ROA building blocks; they carry the `RATIO_` prefix because they are reused in Section 6 Du Pont formulas.

#### Leverage

| Ratio | Named Range | Formula | Unit |
|-------|-------------|---------|------|
| Long-term debt ratio | — | `BAL_debt_long_term_2025 / (BAL_debt_long_term_2025 + BAL_equity_shareholders_2025)` | % |
| Long-term debt-to-equity | — | `BAL_debt_long_term_2025 / BAL_equity_shareholders_2025` | x |
| Total debt ratio | — | `BAL_liabilities_total_2025 / BAL_assets_total_2025` | % |
| Times interest earned (TIE) | — | `INC_ebit / INC_interest_expense` | x |
| Cash coverage ratio | — | `(INC_ebit + CASH_depreciation) / INC_interest_expense` | x |
| Debt burden | `RATIO_debt_burden` | `INC_net / currentYear_after_tax_operating_income` | x |
| Leverage ratio | `RATIO_leverage` | `BAL_assets_total_2025 / BAL_equity_shareholders_2025` | x |

> **VAS depreciation note:** Cash coverage uses `CASH_depreciation` = 1,233.18 (the true depreciation add-back from the Cash Flow tab). `INC_depreciation` = 0.00 and must never appear in this formula. `RATIO_debt_burden` and `RATIO_leverage` carry the `RATIO_` prefix because they are Du Pont components.

#### Liquidity

| Ratio | Named Range | Formula | Unit |
|-------|-------------|---------|------|
| Net working capital to assets | — | `currentYear_working_capital_net / BAL_assets_total_2025` | % |
| Current ratio | — | `BAL_assets_current_2025 / BAL_liabilities_current_2025` | x |
| Quick ratio | — | `(BAL_cash_marketable_securities_2025 + BAL_receivables_2025) / BAL_liabilities_current_2025` | x |
| Cash ratio | — | `BAL_cash_marketable_securities_2025 / BAL_liabilities_current_2025` | x |

> The cash ratio alone will exceed 1.0 — interpret alongside the dividend payout policy and capital allocation strategy, not as a standalone liquidity metric.

#### Du Pont System

| Ratio | Named Range | Formula | Unit |
|-------|-------------|---------|------|
| ROA — Du Pont | — | `RATIO_asset_turnover × RATIO_operating_profit_margin` | % |
| ROE — Du Pont | — | `RATIO_leverage × RATIO_asset_turnover × RATIO_operating_profit_margin × RATIO_debt_burden` | % |

> **Component map:**
> - `RATIO_asset_turnover` = `INC_sales / BAL_assets_total_2024`
> - `RATIO_operating_profit_margin` = `currentYear_after_tax_operating_income / INC_sales`
> - `RATIO_leverage` = `BAL_assets_total_2025 / BAL_equity_shareholders_2025`
> - `RATIO_debt_burden` = `INC_net / currentYear_after_tax_operating_income`

---

### 7. Validation Rules

The executor must verify all rules below before beginning the analysis. Any failure is a model error, not an analytical finding — fix before proceeding, except V3 (expected mismatch) and V6 (expected discrepancy).

**V1 — Balance Sheet balance, FY2025**  
`BAL_assets_total_2025` = `BAL_liabilities_total_2025 + BAL_equity_shareholders_2025`  
Expected: 53,312.359 ≈ 18,829.355 + 34,483.025 = 53,312.380 (rounding ≤ 0.05 VND bn acceptable)

**V2 — Balance Sheet balance, FY2024**  
`BAL_assets_total_2024` = `BAL_liabilities_total_2024 + BAL_equity_shareholders_2024`  
Expected: 55,049.062 ≈ 18,874.659 + 36,174.405 = 55,049.064 (rounding ≤ 0.05 VND bn acceptable)

**V3 — Du Pont ROA = direct ROA (must match exactly)**  
`RATIO_asset_turnover × RATIO_operating_profit_margin` = `currentYear_after_tax_operating_income / BAL_assets_total_2024`  
Both sides use `BAL_assets_total_2024` as denominator → algebraically identical. Any discrepancy = formula error.

**V4 — Du Pont ROE vs. direct ROE (expected mismatch — explain in analysis)**  
Du Pont ROE (`RATIO_leverage × RATIO_asset_turnover × RATIO_operating_profit_margin × RATIO_debt_burden`) will **not** equal direct ROE (`INC_net / BAL_equity_shareholders_2024`). Cause: `RATIO_leverage` uses end-of-year balances (`BAL_assets_total_2025`, `BAL_equity_shareholders_2025`) while `RATIO_asset_turnover` uses start-of-year `BAL_assets_total_2024`. This is a deliberate time-mismatch in the model design — quantify the gap and explain it in the Du Pont section.

**V5 — Net income reconciliation**  
`INC_net` = `INC_addition_retained_earnings + INC_dividends`  
Expected: 9,413.59 = (−1,850.89) + 11,264.48 = 9,413.59 ✓

**V6 — NOPAT formula**  
`currentYear_after_tax_operating_income` = `INC_net + (1 − tax_rate) × INC_interest_expense`  
= 9,413.59 + (0.80 × 325.80) = 9,413.59 + 260.64 = 9,674.23 ✓

**V7 — INC_depreciation is zero (VAS check)**  
`INC_depreciation` must equal 0.00. If any non-zero value appears on the Income Statement depreciation line, it indicates a double-counting error under VAS. The true depreciation figure is `CASH_depreciation` = 1,233.18 on the Cash Flow tab. Do not proceed if `INC_depreciation` ≠ 0.00.

**V8 — Cash coverage ratio uses CASH_depreciation only**  
Confirm that the cash coverage ratio formula references `CASH_depreciation` (= 1,233.18), not `INC_depreciation` (= 0.00). A formula referencing `INC_depreciation` will produce a result identical to TIE — that is a model error.

**V9 — No formula errors**  
All 25+ ratio output cells must be free of `#DIV/0!`, `#REF!`, `#VALUE!`, and `#N/A` before analysis proceeds.

---

## Part B — Analysis Specification

### 7. Analysis Requirements

The analysis must address all six ratio categories below. Interpretation questions and cross-category connections are required content.

#### Performance

- Compute MVA, EVA, and market-to-book using the VND-billions-aligned market cap (136,059 VND bn)
- Is EVA positive? Does Vinamilk earn above its 9% WACC?
- Benchmark market-to-book against Vietnamese dairy / FMCG sector range of 2–5×
- Cross-category: link MVA premium to ROE and Du Pont — is the market premium justified by profitability fundamentals?

#### Profitability

- Report ROA, ROC, and ROE using start-of-year denominators as primary; average-denominator variants as cross-checks
- Benchmark ROE against Vietnamese listed consumer staples peers (15–25%)
- Cross-category: connect ROE to Du Pont decomposition and leverage ratios — is the equity return driven by operating performance or by leverage?

#### Efficiency

- Interpret asset turnover in the context of Vinamilk's capital-intensive manufacturing base
- Assess days in inventory and average collection period for a dairy FMCG operator
- Compare operating profit margin to net profit margin — does the gap signal material financing or tax effects?
- Cross-category: `RATIO_asset_turnover` and `RATIO_operating_profit_margin` are the Du Pont ROA building blocks — connect them explicitly

#### Leverage

- Vinamilk carries near-zero long-term debt (62.908 VND bn vs. equity of 34,483.025 VND bn). Quantify long-term debt ratio and D/E; characterize the capital structure posture
- TIE and cash coverage will be very high; interpret as debt capacity, not just coverage
- Note: cash coverage uses `CASH_depreciation` = 1,233.18 (VAS add-back), not any income statement figure
- Cross-category: `RATIO_leverage` (assets/equity) flows into Du Pont ROE as the leverage multiplier — quantify its contribution

#### Liquidity

- Cash ratio will exceed 1.0; interpret alongside FY2025 dividend payout of 11,264.48 VND bn (exceeds net income of 9,413.59 VND bn — funded partly from prior retained earnings)
- Is the cash balance an operational buffer or evidence of inefficient capital deployment?
- Cross-category: link idle cash to EVA — cash earning below cost of capital directly depresses economic value added

#### Du Pont Decomposition

See Section 8 below.

---

### 8. Du Pont Decomposition

The executor must perform a complete four-factor Du Pont decomposition of ROE.

**Step 1 — Compute and state all four component values:**

| Component | Named Range | Formula |
|-----------|-------------|---------|
| Leverage | `RATIO_leverage` | `BAL_assets_total_2025 / BAL_equity_shareholders_2025` |
| Asset turnover | `RATIO_asset_turnover` | `INC_sales / BAL_assets_total_2024` |
| Operating profit margin | `RATIO_operating_profit_margin` | `currentYear_after_tax_operating_income / INC_sales` |
| Debt burden | `RATIO_debt_burden` | `INC_net / currentYear_after_tax_operating_income` |

**Step 2 — Compute Du Pont ROE:**  
`RATIO_leverage × RATIO_asset_turnover × RATIO_operating_profit_margin × RATIO_debt_burden`

**Step 3 — Identify the primary driver.** Which component is the largest contributor to ROE relative to a unit-leverage baseline? Which component is the binding constraint?

**Step 4 — Address the Du Pont vs. direct ROE mismatch (Validation Rule V4).** Quantify the gap, identify the source (time-mismatch: `RATIO_leverage` uses 2025 balances; `RATIO_asset_turnover` uses 2024 assets), and confirm it is expected — not a model error. This discussion must appear as a dedicated paragraph.

**Step 5 — Assess sustainability.** With leverage at approximately 1.55× (near-pure-equity financing), discuss whether a modest increase in long-term debt would materially amplify ROE, and whether that is consistent with Vinamilk's strategic posture and HOSE market conditions.

---

### 9. Strategic Recommendations

The analysis must conclude with exactly **3–5 strategic recommendations** meeting all of the following standards:

- **Evidence-grounded:** Each recommendation cites at least one specific ratio value computed in this model (e.g., "With a cash ratio of X.Xx…")
- **Actionable:** State a concrete management action — not an observation
- **Cross-referenced:** Each recommendation connects at least two ratio categories
- **Contextually calibrated:** Appropriate for a Vietnamese dairy company on HOSE; generic advice must be adjusted for VAS reporting norms and Vietnam macroeconomic context
- **Horizon-specified:** State near-term (1–2 years) or medium-term (3–5 years)

Candidate themes:

1. **Capital deployment** — FY2025 dividend payout (11,264.48 VND bn) exceeded net income (9,413.59 VND bn); cash ratio > 1.0; what alternative uses of cash — buybacks, M&A, capacity investment — would generate more EVA?
2. **Leverage optimization** — long-term debt of 62.908 VND bn against equity of 34,483.025 VND bn is near-zero leverage; could strategic debt increase ROE without material distress risk given TIE >> 10×?
3. **Working capital efficiency** — reduce days in inventory and average collection period to improve asset turnover and EVA
4. **Margin vs. volume** — with COGS at 55.8% of sales and SGA at 23.8%, which cost line offers the highest operating leverage for margin expansion?
5. **Revenue growth trajectory** — is the ROE constraint binding on the asset turnover side or the margin side, and what investment mix resolves it?

---

### 10. Output Format

The Stage 5 analysis deliverable must be structured as follows.

**Filename:** `YYYY-MM-DD-tran-vinamilk-analysis.md`

**Section order and length targets:**

| # | Section | Target length |
|---|---------|--------------|
| 1 | Executive Summary | 150–200 words; state the 3 most important findings upfront |
| 2 | Company & Data Overview | 100–150 words; company description, fiscal period, data source, VAS note |
| 3 | Performance | 250–350 words; MVA, EVA, market-to-book with strategic interpretation |
| 4 | Profitability | 200–300 words; ROA, ROC, ROE vs. benchmarks |
| 5 | Efficiency | 200–300 words; turnover ratios, margin analysis, Du Pont link |
| 6 | Leverage | 150–250 words; debt ratios, coverage (noting VAS depreciation), debt capacity |
| 7 | Liquidity | 150–200 words; current, quick, cash ratios vs. dividend policy |
| 8 | Du Pont Decomposition | 300–400 words; four-factor breakdown + time-mismatch explanation |
| 9 | Strategic Recommendations | 3–5 recommendations at 100–150 words each |
| 10 | Appendix: Ratio Table | All 25+ ratios with computed values, units, one-sentence interpretation |

**Tone and style:**

- Audience: Prof. Adam Stauffer; Managing Director perspective — executive reader; full financial literacy assumed; do not define ratios; go straight to strategic implication
- Voice: third-person analytical ("Vinamilk's current ratio of X.Xx suggests…"); no hedging ("it could be argued"); state findings directly
- Precision: ratio values to two decimal places; monetary figures in VND billions with comma formatting; always label units
- No padding: every paragraph must deliver an insight or strategic implication

**Appendix ratio table format:**

| Category | Ratio | Value | Unit | Strategic interpretation (one sentence) |
|----------|-------|------:|------|-----------------------------------------|

---

## References

1. Vietnam Dairy Products Joint Stock Company (Vinamilk). *FY2025 Audited Financial Statements (VAS).* Vietstock Finance: https://finance.vietstock.vn/VNM/tai-chinh.htm
2. Stage 3 populated workbook: `2026-05-17-tran-vinamilk-financials.xlsx`
3. Stage 1 ratio model template: `performance-ratios-template.xlsx` (BUS-629, UH Mānoa Shidler College of Business)
4. Stage 4 brief: `courses/BUS-629-VEMBA-International-Corporate-Finance/stage4-technical-specification.md` (github.com/adamwstauffer/shidler)
5. Spec template: `docs/templates/spec-template.md` (github.com/adamwstauffer/shidler)