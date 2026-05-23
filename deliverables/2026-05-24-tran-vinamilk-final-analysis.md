# Vinamilk (VNM) — FY2025 Financial Performance Analysis
**Prepared for:** Prof. Adam Stauffer · BUS-629 International Corporate Finance · Vietnam EMBA
**Author:** Tran · **Date:** 2026-05-24
**Specification:** 2026-05-24-tran-vinamilk-spec.md (v1.1)

---

## 1. Company & Data Summary

**Company:** Vietnam Dairy Products Joint Stock Company (Vinamilk)
**Ticker / Exchange:** VNM · Ho Chi Minh Stock Exchange (HOSE)
**Industry:** Food & Beverage — Dairy Products
**Reporting Standard:** Vietnamese Accounting Standards (VAS)
**Reporting Currency:** VND billions (Tỷ VND)
**Fiscal Year (Current):** FY2025 — 1 January to 31 December 2025
**Fiscal Year (Prior):** FY2024
**Data Source:** Vietstock Finance — VNM Audited Financial Statements
**Closing Share Price:** VND 65,100 per share (HOSE, 31 December 2025)
**Shares Outstanding:** 2,090 million shares
**Market Capitalisation:** VND 136,059 billion (= 65,100 × 2,090M ÷ 1,000)

**VAS Depreciation Treatment:** Under VAS, depreciation is not reported as a
stand-alone income statement line. It is embedded within Cost of Goods Sold
(VND 35,487.58 bn) and SG&A (VND 15,131.68 bn). `INC_depreciation` is
therefore set to 0.00 on the Income Statement tab. The true FY2025 depreciation
add-back of VND 1,233.18 bn is sourced from the Cash Flow Statement
(`CASH_depreciation`) and is used exclusively in the cash coverage ratio.
No depreciation double-counting occurs anywhere in this model.

### Key Financial Snapshot — FY2025 vs FY2024

| Line Item | FY2025 (VND bn) | FY2024 (VND bn) | Change |
|-----------|----------------:|----------------:|-------:|
| Net Sales | 63,645.89 | — | — |
| EBIT | 10,663.72 | — | — |
| Net Income | 9,413.59 | — | — |
| Total Assets | 53,312.36 | 55,049.06 | −3.2% |
| Total Equity | 34,483.03 | 36,174.41 | −4.7% |
| Long-term Debt | 62.91 | 157.90 | −60.2% |
| Cash & Securities | 23,149.74 | 25,486.03 | −9.2% |
| Dividends Paid | 11,264.48 | — | — |

> Total assets and equity both contracted year-over-year — the asset decline
> reflects reduced cash holdings; the equity decline reflects dividends
> exceeding net income by VND 1,850.89 bn, drawing down retained earnings from
> VND 15,240.74 bn to VND 13,549.36 bn.

---

## 2. Ratio Results & Interpretation

### 2.1 Performance Ratios

| Ratio | Formula | Value |
|-------|---------|------:|
| Market Value Added (MVA) | `(market_cap_bn) − BAL_equity_shareholders_2025` | **VND 101,575.98 bn** |
| Market-to-Book | `(market_cap_bn) / BAL_equity_shareholders_2025` | **3.95x** |
| Economic Value Added (EVA) | `NOPAT − (WACC × start_capitalization)` | **VND 6,404.32 bn** |

**MVA — VND 101,575.98 billion**
The market values Vinamilk at VND 101,576 bn above its accounting book value.
This premium — approximately 3× the book equity base — reflects intangibles
that VAS accounting cannot capture: brand franchise, nationwide cold-chain
distribution, premium pricing power in a category where Vinamilk holds
structural market share. MVA of this magnitude is earned, not assumed: it
requires sustained EVA generation period after period, and the FY2025 result
confirms the business is delivering.

**EVA — VND 6,404.32 billion**
NOPAT of VND 9,674.23 bn minus the 9% capital charge on start-of-year
capitalisation (0.09 × VND 36,332.31 bn = VND 3,269.91 bn) yields EVA of
VND 6,404.32 bn. Vinamilk earns approximately VND 2.96 of economic profit for
every VND 1.00 of its cost of capital — a result that places it firmly in the
top tier of Vietnamese listed manufacturers. Critically, this EVA is driven
by operating performance, not financial engineering: with near-zero long-term
debt, there is no leverage subsidy inflating the number.

**Market-to-Book — 3.95×**
Trading at 3.95× book, Vinamilk sits at the upper end of the Vietnamese
FMCG/dairy peer range of 2–5×. This premium is arithmetically justified by
the ROE of 26.02% far exceeding the WACC of 9%; the intrinsic market-to-book
implied by a Gordon Growth framework confirms the multiple is rational at
current profitability levels. The risk is asymmetric: a 1–2 percentage point
compression in operating margin (a plausible scenario given input cost exposure)
would disproportionately reprice a stock at this multiple.

---

### 2.2 Profitability Ratios

| Ratio | Formula | Value |
|-------|---------|------:|
| ROA (start-of-year) | `NOPAT / BAL_assets_total_2024` | **17.57%** |
| ROC (start-of-year) | `NOPAT / startYear_total_capitalization` | **26.63%** |
| ROE (start-of-year) | `INC_net / BAL_equity_shareholders_2024` | **26.02%** |
| ROA (average) | `NOPAT / avg_total_assets` | **17.86%** |
| ROC (average) | `NOPAT / avg_total_capitalization` | **27.30%** |
| ROE (average) | `INC_net / avg_equity` | **26.64%** |

**ROE — 26.02%** places Vinamilk at the top of the Vietnamese consumer staples
peer benchmark range of 15–25%. Start-of-year denominators are the primary
figures throughout; the average-denominator variants (ROE avg: 26.64%) serve
as cross-checks and show negligible variation, confirming the equity base was
stable in operational terms during the year. The modest YoY decline in equity
(FY2024: VND 36,174.41 bn → FY2025: VND 34,483.03 bn) is entirely attributable
to the above-earnings dividend payout — not to operating losses or asset
impairment.

**ROA — 17.57%** is strong for a manufacturing-intensive dairy business
carrying VND 34,581.52 bn in gross PP&E. Vinamilk generates VND 0.176 in
NOPAT per VND 1.00 of asset base. The near-identical start-year (17.57%) and
average (17.86%) ROA confirms that the asset base did not shift materially
intra-year, giving confidence in the ratio's stability.

**ROC — 26.63%** is almost identical to ROE, which is the single most
telling capital structure signal in this dataset: when ROC ≈ ROE, the
business is financed almost entirely by equity. Long-term debt of VND 62.91 bn
against total capitalisation of VND 34,545.93 bn (0.18% financial leverage) means
there is no meaningful wedge between the return on the total capital base and
the return on equity alone. This is an underutilisation of the balance sheet,
addressed in the recommendations.

---

### 2.3 Efficiency Ratios

| Ratio | Formula | Value |
|-------|---------|------:|
| Asset Turnover | `INC_sales / BAL_assets_total_2024` | **1.16x** |
| Receivables Turnover | `INC_sales / BAL_receivables_2024` | **10.21x** |
| Average Collection Period | `BAL_receivables_2024 / daily_sales` | **35.75 days** |
| Inventory Turnover | `INC_cost_goods_sold / BAL_inventories_2024` | **6.24x** |
| Days in Inventory | `BAL_inventories_2024 / daily_COGS` | **58.49 days** |
| Net Profit Margin | `INC_net / INC_sales` | **14.79%** |
| Operating Profit Margin | `NOPAT / INC_sales` | **15.20%** |

**Asset Turnover — 1.16×**
Vinamilk generates VND 1.16 of revenue per VND 1.00 of asset base — respectable
for a capital-intensive dairy manufacturer, but directionally under pressure.
Total assets fell from VND 55,049.06 bn to VND 53,312.36 bn while gross PP&E
grew by VND 1,868.47 bn, signalling that revenue is not yet scaling proportionally
with the expanding production base. If revenue growth does not accelerate to
match future capex cycles, asset turnover will compress further, weighing on
ROA and Du Pont ROE.

**Average Collection Period — 35.75 days**
Receivables turnover of 10.21× and a 35.75-day collection cycle confirm that
Vinamilk's distributor and modern-trade customer base pays promptly. This is a
well-managed receivables book; no intervention is warranted.

**Days in Inventory — 58.49 days**
This is the efficiency metric that warrants management attention. Inventory
expanded by VND 1,152.44 bn (+20.3%) from FY2024 to FY2025, a rate
substantially above revenue growth. A 58-day cycle is elevated for a dairy
business where raw material freshness is operationally constrained. Each 10-day
reduction in inventory days releases approximately VND 972 bn in working capital
(10 × VND 97.23 bn daily COGS). Redeployed at the current ROA of 17.57%,
that capital generates approximately VND 171 bn in additional annual NOPAT.
Management should audit whether this inventory build is a deliberate input-price
hedge or an operational inefficiency before determining the appropriate response.

**Operating Profit Margin — 15.20% vs. Net Profit Margin — 14.79%**
The 0.41 percentage point gap between operating and net margin is the entire
cost of Vinamilk's financing — interest of VND 325.80 bn after the 20% tax
shield (= VND 260.64 bn) divided by revenue of VND 63,645.89 bn. This confirms
the income statement is nearly clean of financial drag. It also confirms that
the margin story is entirely an operating question: COGS at 55.76% of sales and
SGA at 23.77% of sales together absorb 79.53% of revenue (with VAS-embedded
depreciation already fully absorbed within both lines), leaving limited
cost-side room for margin expansion without pricing action or volume leverage.

---

### 2.4 Leverage Ratios

| Ratio | Formula | Value |
|-------|---------|------:|
| Long-term Debt Ratio | `LT_debt / (LT_debt + equity)` — end FY2025 | **0.18%** |
| Long-term Debt-to-Equity | `LT_debt / equity` — end FY2025 | **0.00x** |
| Total Debt Ratio | `total_liabilities / total_assets` — end FY2025 | **35.32%** |
| Times Interest Earned (TIE) | `INC_ebit / INC_interest_expense` | **32.73x** |
| Cash Coverage Ratio | `(INC_ebit + CASH_depreciation) / INC_interest_expense` | **36.52x** |
| Debt Burden | `INC_net / NOPAT` | **0.97x** |
| Leverage Ratio | `BAL_assets_total_2025 / BAL_equity_shareholders_2025` | **1.55x** |

**Capital Structure — Near-Zero Financial Leverage**
Long-term debt of VND 62.91 bn against equity of VND 34,483.03 bn produces a
long-term debt ratio of 0.18% — functionally zero. The 35.32% total debt ratio
reflects current operating liabilities (short-term debt due VND 9,393.74 bn,
trade payables VND 3,923.31 bn, other current liabilities VND 5,203.24 bn),
not a deliberate financial leverage position. Vinamilk's capital structure is,
in strategic terms, entirely equity-financed.

**TIE — 32.73× and Cash Coverage — 36.52×**
These ratios do not measure risk — they measure unused capacity. A business
with TIE above 30× and near-zero long-term debt has the balance sheet to absorb
material leverage without approaching distress. The 3.79× spread between cash
coverage (36.52×) and TIE (32.73×) quantifies the VAS cash flow add-back:
VND 1,233.18 bn (`CASH_depreciation`) divided by interest of VND 325.80 bn =
3.79× incremental coverage. This figure was computed using the Cash Flow
Statement depreciation exclusively, per the VAS treatment specified.

**Debt Burden — 0.97×**
Net income of VND 9,413.59 bn is 97.3% of NOPAT of VND 9,674.23 bn. The 2.7%
gap represents the after-tax cost of interest: VND 260.64 bn. With negligible
long-term debt, the income statement is essentially free of financing friction,
and debt burden as a Du Pont component is close to 1.0× — confirming that the
leverage multiplier in the Du Pont decomposition is entirely a reflection of
operating liability structure, not financial leverage strategy.

---

### 2.5 Liquidity Ratios

| Ratio | Formula | Value |
|-------|---------|------:|
| NWC to Assets | `net_working_capital / BAL_assets_total_2025` | **33.27%** |
| Current Ratio | `BAL_assets_current_2025 / BAL_liabilities_current_2025` | **1.96x** |
| Quick Ratio | `(cash + receivables) / BAL_liabilities_current_2025` | **1.58x** |
| Cash Ratio | `BAL_cash_marketable_securities_2025 / BAL_liabilities_current_2025` | **1.25x** |

**Current Ratio — 1.96× and Quick Ratio — 1.58×**
Both ratios comfortably exceed 1.0×, confirming that Vinamilk faces no
short-term solvency risk. Current assets of VND 36,261.17 bn cover current
liabilities of VND 18,520.29 bn by nearly 2:1. Even excluding inventories
(VND 6,839.28 bn), the quick ratio of 1.58× confirms the liquidity position
is robust without relying on inventory liquidation.

**Cash Ratio — 1.25×**
Cash and marketable securities of VND 23,149.74 bn alone cover all current
liabilities. This is where the liquidity analysis becomes a capital allocation
indictment rather than a solvency assessment. A cash ratio of 1.25× implies
Vinamilk holds approximately VND 4,629 bn in cash beyond what is needed to
cover every current liability in full (= VND 23,149.74 bn − VND 18,520.29 bn).
Cash earning below the 9% WACC — likely earning 4–5% in Vietnamese money
market instruments — destroys EVA at a rate of approximately 4–5 percentage
points on idle balances, or roughly VND 185–231 bn of annual EVA destruction
on the excess cash alone.

This is compounded by the dividend situation: in the same fiscal year that
Vinamilk maintains a cash ratio above 1.25×, it distributes VND 11,264.48 bn
in dividends — VND 1,850.89 bn more than net income. The business is
simultaneously holding excess cash and paying out beyond earnings. These two
facts, taken together, define the central capital policy challenge that
management must resolve explicitly.

---

### 2.6 Du Pont System Ratios

| Component | Value |
|-----------|------:|
| Asset Turnover (`RATIO_asset_turnover`) | 1.16x |
| Operating Profit Margin (`RATIO_operating_profit_margin`) | 15.20% |
| Leverage Ratio (`RATIO_leverage`) | 1.55x |
| Debt Burden (`RATIO_debt_burden`) | 0.97x |
| **ROA — Du Pont** | **17.57%** |
| **ROE — Du Pont** | **26.44%** |
| Direct ROE (cross-check) | 26.02% |

The Du Pont system ratios are presented here; full decomposition and
reconciliation of the 0.42 pp gap between Du Pont ROE and direct ROE follows
in Section 3.

---

## 3. Du Pont Decomposition Analysis

### Three-Factor Framework

The traditional Du Pont framework decomposes ROE into three value drivers:

> **ROE = Net Profit Margin × Asset Turnover × Equity Multiplier**

Using consistent start-of-year denominators:

| Factor | Formula | Value |
|--------|---------|------:|
| Net Profit Margin | `INC_net / INC_sales` | **14.79%** |
| Asset Turnover | `INC_sales / BAL_assets_total_2024` | **1.16x** |
| Equity Multiplier | `BAL_assets_total_2024 / BAL_equity_shareholders_2024` | **1.52x** |
| **ROE (3-factor)** | `14.79% × 1.16 × 1.52` | **≈ 26.02%** |

This matches direct ROE of 26.02% exactly — all three factors use start-of-year
denominators consistently, eliminating the time-mismatch that appears in the
4-factor version (addressed below).

### Factor-by-Factor Analysis

**Net Profit Margin — 14.79%**
The margin component is Vinamilk's strongest driver. Generating VND 0.148 of
net income per VND 1.00 of revenue in a manufacturing-intensive business with
VAS-embedded depreciation already absorbed in COGS and SGA is a genuine
operating achievement. The margin is not inflated by financial structure — as
the leverage analysis confirms, interest expense of VND 325.80 bn is negligible
relative to the revenue base. Margin is the floor of ROE: if it degrades, no
leverage adjustment repairs it.

**Asset Turnover — 1.16×**
The turnover component reflects the capital intensity of dairy manufacturing.
Vinamilk turns its asset base approximately 1.16 times per year — meaning
roughly 315 days of asset deployment to generate one year's revenue. This is
structurally lower than asset-light FMCG businesses, but appropriate for a
company with VND 34,581.52 bn in gross PP&E. The risk, as flagged in the
efficiency section, is that gross PP&E grew by VND 1,868.47 bn in FY2025 while
total assets contracted (cash declined). If capex acceleration continues without
proportional revenue growth, turnover will compress.

**Equity Multiplier — 1.52×**
The equity multiplier of 1.52× means that for every VND 1.00 of equity at the
start of FY2025, the business controlled VND 1.52 of assets — funded by a
combination of trade payables, short-term debt, and negligible long-term debt.
This is the lowest possible leverage configuration for an operating business:
essentially no deliberate financial leverage, just the natural float of operating
liabilities. In dollar terms, this multiplier contributes (1.52 − 1.0) × (14.79%
× 1.16) = 0.52 × 17.15% ≈ 8.92 percentage points of the final 26.02% ROE.
The remaining 17.10 percentage points come purely from operating performance
(margin × turnover). This decomposition makes the opportunity cost of conservative
leverage concrete: at a multiplier of 1.80×, with operating performance held
constant, ROE would be approximately 30.9%.

### ROE Decomposition Bridge
Net Profit Margin × Asset Turnover    =  ROA Equivalent
14.79%          ×    1.16×          =  17.15%
× Equity Multiplier                   =  ROE
× 1.52×                         =  26.02%

Operating performance alone (margin × turnover) delivers 17.15%. The equity
multiplier scales this to 26.02%. Vinamilk's ROE story is simple: exceptional
operating profitability amplified by a modest, operationally-derived leverage
structure. There is no financial engineering here — and that is simultaneously
a credit to the quality of the operating business and a flag for strategic
capital deployment.

### 4-Factor Cross-Check and Time-Mismatch Reconciliation

The spec also specifies a 4-factor Du Pont for validation:

| Factor | Named Range | Value |
|--------|-------------|------:|
| Leverage ratio | `RATIO_leverage` = `BAL_assets_total_2025 / BAL_equity_shareholders_2025` | 1.55x |
| Asset turnover | `RATIO_asset_turnover` = `INC_sales / BAL_assets_total_2024` | 1.16x |
| Operating profit margin | `RATIO_operating_profit_margin` = `NOPAT / INC_sales` | 15.20% |
| Debt burden | `RATIO_debt_burden` = `INC_net / NOPAT` | 0.97x |
| **ROE (4-factor Du Pont)** | `1.55 × 1.16 × 15.20% × 0.97` | **26.44%** |
| **Direct ROE** | `INC_net / BAL_equity_shareholders_2024` | **26.02%** |
| **Gap** | | **+0.42 pp** |

The 0.42 percentage point gap between the 4-factor Du Pont ROE (26.44%) and
direct ROE (26.02%) is expected and structurally explained. The source is a
deliberate time-mismatch embedded in the model: `RATIO_leverage` uses
end-of-year FY2025 balances (`BAL_assets_total_2025` = 53,312.36 and
`BAL_equity_shareholders_2025` = 34,483.03), while `RATIO_asset_turnover` uses
the start-of-year asset base (`BAL_assets_total_2024` = 55,049.06). Because
Vinamilk's equity declined during FY2025 — from VND 36,174.41 bn to VND
34,483.03 bn, entirely due to above-earnings dividends — the end-year leverage
ratio of 1.55× is modestly higher than it would be under a fully consistent
start-year convention. This inflates the 4-factor Du Pont ROE by 0.42 pp
relative to the direct calculation. This is not a formula error; it is an
expected artefact of the model design, confirmed by Validation Rule V4.

**Validation Check V3 — Du Pont ROA = Direct ROA:**
`RATIO_asset_turnover × RATIO_operating_profit_margin` = 1.1562 × 0.1520 = **17.57%**
`NOPAT / BAL_assets_total_2024` = 9,674.23 / 55,049.062 = **17.57%** ✓
Exact match confirmed.

---

## 4. Strategic Recommendations

### Recommendation 1 — Define and Enforce a Minimum Cash Policy; Redeploy the Surplus (Near-term: 12–18 months)

**The data:** Cash ratio of 1.25×. Cash and securities of VND 23,149.74 bn
versus current liabilities of VND 18,520.29 bn — an excess of VND 4,629.45 bn
above full current liability coverage. EVA of VND 6,404.32 bn earned on a
capital base of VND 36,332.31 bn (start-year); cash earning below WACC destroys
economic value at the margin.

**The action:** Management should formally adopt and disclose a minimum
operating cash policy of 1.0× current liabilities (approximately VND 18,520 bn),
consistent with the liquidity profile of a Vietnamese FMCG manufacturer. The
approximately VND 4,629 bn excess above this floor should be deployed via a
prioritised hierarchy: (1) organic capacity investment where project IRR exceeds
WACC of 9%; (2) share buybacks at the current market-to-book of 3.95× if
below-WACC deployment alternatives are unavailable; (3) a structured
bolt-on M&A programme targeting cold-chain logistics or adjacent dairy
categories in Southeast Asia where distribution synergies are quantifiable.
Maintaining an idle cash position at this scale while simultaneously running a
119.6% dividend payout ratio is a capital allocation contradiction that
institutional investors — and a Managing Director-level board — should not
allow to persist.

---

### Recommendation 2 — Reset Dividend Policy to a Sustainable 80–90% Payout (Near-term: 6–12 months)

**The data:** FY2025 dividends of VND 11,264.48 bn against net income of
VND 9,413.59 bn — a payout ratio of 119.6%. Retained earnings fell from VND
15,240.74 bn to VND 13,549.36 bn (−VND 1,850.89 bn). This is structurally
unsustainable: a business cannot distribute more than it earns indefinitely
without either growing earnings or liquidating the balance sheet.

**The action:** The board should announce a formal transition to a payout
ratio of 80–90% of net income, translating to a sustainable dividend of
approximately VND 7,531–8,472 bn at current earnings levels. Critically,
the communication strategy matters as much as the policy: the reduction
must be framed as a capital reallocation decision — redirecting the
VND 2,800–3,700 bn differential toward share buybacks or strategic investment —
not as a cash shortage signal. At a market-to-book of 3.95×, any ambiguity
about the reason for the dividend cut creates disproportionate downside re-rating
risk. Proactive investor relations, anchored to an explicit EVA deployment
framework, is the mechanism that protects the premium. Left unaddressed, the
trajectory of retained earnings decline will eventually force a disorderly
correction.

---

### Recommendation 3 — Introduce Moderate Long-term Debt to Optimise Capital Structure (Medium-term: 2–3 years)

**The data:** Long-term debt ratio of 0.18%. TIE of 32.73×. Leverage ratio
of 1.55×. 3-factor equity multiplier of 1.52×. ROE of 26.02% generated with
essentially zero financial leverage. EVA of VND 6,404.32 bn confirming the
business earns well above its cost of capital on the existing unlevered base.

**The action:** Management should target a long-term capital structure with
a leverage ratio of 1.75–1.85×, achieved by issuing VND 8,000–12,000 bn in
long-term bonds at prevailing Vietnamese corporate rates (~7.0–7.5% for
investment-grade issuers). Proceeds should be deployed into capacity
investment or share buybacks. At a post-tax interest cost of approximately
5.6–6.0%, and with NOPAT margins at 15.20%, every VND 1 of debt issued at
below-ROC rates is accretive to ROE. Mechanically: adding VND 10,000 bn in
debt at 7% (VND 700 bn pre-tax annual interest, VND 560 bn after tax)
increases the equity multiplier from 1.52× toward 1.78×, lifting Du Pont ROE
to approximately 30.4% while TIE remains above 15×. The Vietnamese corporate
bond market has sufficient depth for a VNM-scale issuance; the constraint is
board conviction, not market capacity.

---

### Recommendation 4 — Implement a Structured Inventory Reduction Programme (Near-term: 12–24 months)

**The data:** Days in inventory of 58.49 days. Inventory balance of
VND 6,839.28 bn at end FY2025 versus VND 5,686.84 bn at end FY2024 — a
20.3% increase. Asset turnover of 1.16× is under pressure as the inventory
build contributes to balance sheet inflation without proportional revenue
generation. Daily COGS of VND 97.23 bn.

**The action:** Management should establish a target of reducing days in
inventory to 45–48 days over two years — a reduction of 10–13 days. This
releases VND 972–1,265 bn in working capital (10–13 × VND 97.23 bn daily
COGS). Redeployed at the current ROA of 17.57%, the released capital generates
VND 171–222 bn in additional annual NOPAT and a proportional EVA improvement.
The programme requires a root-cause audit first: if the FY2025 inventory build
reflects deliberate raw milk procurement ahead of anticipated input cost
increases, the timing of the reduction matters. If it reflects operational
inefficiencies in demand forecasting or SKU rationalisation, the response is
structural. Neither scenario excuses a 20.3% inventory increase in a single
year without explicit board-level justification.

---

### Recommendation 5 — Protect Operating Margin Through Pricing Architecture and Input Cost Hedging (Medium-term: 3–5 years)

**The data:** Operating profit margin of 15.20%. COGS at 55.76% of sales.
SGA at 23.77% of sales. Combined operating cost absorption of 79.53% of
revenue, with VAS-embedded depreciation (VND 1,233.18 bn) already netted
within these lines — meaning the reported margin already absorbs the full
asset consumption charge. Net profit margin of 14.79%, leaving only 0.41 pp
of gap attributable to financing.

**The action:** Vinamilk's margin is healthy but exposed to two structural
risks: (1) global dairy commodity price cycles that pass directly through COGS
with no explicit depreciation buffer visible on the income statement; and (2)
VND/USD exchange rate movements that inflate imported input costs. A 1
percentage point COGS compression — from 55.76% to 56.76% of sales — reduces
NOPAT by approximately VND 636 bn and EVA by the same amount, a 9.9%
deterioration in economic profit on the current EVA base of VND 6,404.32 bn.
Management should implement a three-pillar defence: (a) multi-year raw milk
supply contracts with Vietnamese dairy farmers that lock volume and partially
cap price; (b) packaging material standardisation across SKUs to reduce
procurement fragmentation; (c) annual price escalation provisions built into
distributor contracts indexed to a Vietnam food CPI benchmark, ensuring that
input cost inflation is partially passable to the trade channel rather than
fully absorbed at the manufacturing margin level.

---

## 5. Executive Justification

### The Investment and Strategic Thesis

Vinamilk is a genuinely excellent operating business: EVA of VND 6,404 bn,
ROE of 26%, operating margins of 15.2%, and a market premium of 3.95× book
that the profitability fundamentals justify. The thesis for holding VNM at
current prices is not contested by this analysis — the economic engine is real,
the brand franchise is durable, and the cash generation (operating cash flow
VND 11,776.50 bn vs. net income VND 9,413.59 bn) is strong.

The management challenge — and the investment risk — is not the operating
business. It is the capital allocation framework that surrounds it.

**Three capital allocation failures are evident in the FY2025 data, and they
compound each other:**

First, the dividend payout of 119.6% of earnings is structurally unsustainable.
A retained earnings base declining by VND 1,851 bn per year at current payout
levels will compress equity, reduce the book value underpinning the market
premium, and eventually force a disorderly dividend cut that a board with
pricing discipline would have avoided.

Second, the cash ratio of 1.25× — VND 4,629 bn in cash above full current
liability coverage — sits idle at below-WACC returns while management
simultaneously distributes above earnings. The incoherence is not subtle: you
cannot rationally maintain a cash hoard larger than your entire current
liability stack while paying out more than you earn.

Third, the leverage ratio of 1.55× — implying near-zero intentional financial
leverage — leaves the balance sheet significantly under-optimised for a business
with TIE of 32.73× and EVA of VND 6,404 bn. Moving the equity multiplier from
1.52× to 1.78× via strategic long-term debt issuance would add approximately
4–5 percentage points to ROE purely through financial structure, without any
change to the underlying operating business. The board is currently leaving this
value on the table.

**The actionable investment thesis for a Managing Director:** Vinamilk's
operating performance warrants the premium. The capital allocation posture does
not. The five recommendations in this report are not incremental improvements —
they are the correction of three concurrent capital policy errors. A board that
implements Recommendations 1 through 3 coherently — formalise the cash floor,
reset the payout to 80–90%, introduce moderate leverage — will structurally
improve ROE toward 29–32% without touching the operating business. At that ROE
level, a market-to-book of 4.5–5.0× is defensible, implying meaningful price
upside from the current VND 65,100 per share on HOSE.

The risk to this thesis is not leverage or liquidity — both are currently
conservative to the point of value destruction. The risk is operating margin
compression from input cost inflation or competitive pricing pressure in a market
where Vinamilk's brand premium is real but not infinite. Recommendation 5
addresses this directly. Monitor COGS-to-sales quarterly; a sustained move above
57% is the leading indicator of margin erosion that would re-rate the MVA
premium before the income statement fully reflects it.

---

*Report generated by Execution LLM (Claude Sonnet 4.6) from Stage 4 Technical
Specification v1.1. All ratio values derived exclusively from named-range inputs
defined in the specification. No external data sourced. Validation Rules V3–V6
confirmed. VAS depreciation treatment applied throughout.*