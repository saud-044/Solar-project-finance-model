# Solar PV Project Finance Model — 50 MWp, France

A ground-up project finance model for a 50 MWp ground-mounted solar PV
asset in Nouvelle-Aquitaine, France. Built from a blank sheet to learn
the mechanics of how infrastructure debt is sized, sculpted, and repaid.

## Headline outputs (base case)

| Metric | Value |
|---|---|
| Project IRR (unlevered) | 7.2% |
| Equity IRR (levered) | 10.7% |
| Equity multiple (MOIC) | 3.37x |
| Minimum DSCR | 1.37x |
| Minimum LLCR | 1.61x |
| Gearing (on capex) | 75% |
| Binding constraint | Gearing |

## What it covers

- Flag-driven semi-annual timing engine (52 periods, construction + operations)
- Capex funding with interest-during-construction (IDC), circularity broken
  via a manual Goal Seek
- Revenue split across a 20-year CfD contract (€79/MWh) and a 5-year
  merchant tail (€55/MWh real)
- Debt sized on the binding constraint of gearing vs. DSCR capacity
- Sculpted amortisation to a target DSCR, with a DSRA and a distribution lock-up
- Full cash-flow waterfall, LLCR, and levered/unlevered returns
- Two-way sensitivity tables
- 15 integrity checks under a single master flag

## One thing I found interesting

The debt is **gearing-bound, not coverage-bound**. On a 20-year contracted
asset the cash flows are predictable enough that DSCR sits well above target,
so the 75% gearing cap limits the loan before coverage ever does. Flex the
interest rate by 200bps and the minimum DSCR barely moves. The "safety" of
a government-backed offtake shows up as policy-limited leverage rather than
cash-flow-limited leverage.

## Stated simplifications

No working capital or refinancing; straight-line tax depreciation; flat merchant tail
(no price cannibalisation). A learning build, not an investment committee paper.

## Files

- `Solar_Project_Finance_Model_v3.xlsx` - the full model
- `Solar_Model_Summary.pdf` — 1-pager + sensitivity summary

## Assumptions & sources

Yield from PVGIS (JRC); capex benchmarked to IRENA / Fraunhofer ISE European
utility-scale; contract price from recent CRE PPE2 ground-mount tender averages.
Full source list on the model's cover tab.

------

*Built by Saud Shaikh, MSc Finance candidate, emlyon business school.
Civil engineer by background, focused on infrastructure and real assets.
Feedback from infra practitioners genuinely welcome.*
Email: saudshaikh044@gmail.com
