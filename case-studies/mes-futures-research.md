# MES Futures Research Case Study

This case study summarizes a high-level research cycle for a private MES futures strategy. It does not disclose source code, exact signal logic, executable rules, or private datasets.

## Objective

Improve the quality of a futures trend-pullback strategy by reducing low-quality entries, identifying drawdown sources, and validating whether exit behavior remains stable across recent and older data.

## Market

- Instrument: Micro E-mini S&P 500 futures (`MES`)
- Timeframe reviewed: 15-minute futures data
- Validation sources: private Python backtests and TradingView Deep Backtesting exports

## Research Problem

Early versions of the research showed a common issue:

- Some entries were occurring too far from the intended pullback area.
- Some short-entry windows created repeated drawdown clusters.
- Full positions and scaled runner positions needed different exit behavior.
- Daily max-loss exits were protecting the account, but repeated occurrences indicated preventable trade-quality issues.

## Analysis Process

The private research workflow reviewed trades by:

- Long versus short contribution
- Entry time window
- Exit reason
- Runner versus non-runner behavior
- Daily max-loss frequency
- Profit factor
- Drawdown
- Trade duration
- Recent-data and older-data behavior
- Daily trade/no-trade decision explanations
- Journal-style post-trade review fields

The TradingView exports were also grouped into real positions to avoid overcounting partial exits as separate strategy decisions.

## High-Level Improvements Tested

The research tested several non-code-level ideas:

- Keeping entries closer to the EMA pullback zone
- Filtering weak short-entry time windows
- Differentiating full-position exits from scaled-runner exits
- Letting reduced-size runners continue when trend conditions remained favorable
- Avoiding uncontrolled full-position exposure late in the session
- Reviewing whether daily max-loss exits were caused by specific repeatable patterns

## Representative TradingView Research Snapshot

One extended TradingView deep-test snapshot from January 2020 through July 2026 showed:

| Metric | Snapshot |
|---|---:|
| Net profit | +$22,682.50 |
| Return on initial capital | 22.68% |
| Profit factor | 1.53 |
| Max drawdown, intrabar | 7.10% |
| Long contribution | +$12,922.50 |
| Short contribution | +$9,760.00 |
| Grouped positions reviewed | 155 |

## Private Python Backtest Diagnostics Snapshot

A private Python backtest snapshot from September 2024 through July 2026 was used to study diagnostics and exit quality in more detail.

| Metric | Snapshot |
|---|---:|
| Final capital | $121,307.52 |
| Total return | 21.31% |
| Win rate | 84.06% |
| Profit factor | 5.27 |
| Max drawdown | -2.25% |
| Long contribution | +$12,565.37 |
| Short contribution | +$8,782.14 |
| Closed trade rows reviewed | 69 |

### Diagnostic Takeaways

- 14 of 18 reported months were profitable in this private Python snapshot.
- Best month reviewed: April 2026, approximately +$5,927.
- Weakest month reviewed: January 2026, approximately -$1,127.
- Partial exits and runner exits were both meaningful contributors.
- Daily max-loss exits remained a risk warning category, even when total performance was positive.
- Entry timing, weekday behavior, and worst-trade review were used as diagnostics rather than standalone trading rules.
- No-trade days are now reviewed through a daily decision matrix to determine which filters blocked activity.

## Exit-Quality Summary

The private Python diagnostic export showed the value of separating exits by purpose:

| Exit Category | Closed Rows | Aggregate PnL |
|---|---:|---:|
| Partial profit exits | 29 | +$8,190.20 |
| Runner exits | 11 | +$8,626.50 |
| Stop / trailing exits | 16 | +$4,007.57 |
| Daily max-loss exits | 3 | -$2,473.00 |

This helped confirm that the research should continue focusing on preventing full-position losses while preserving partial-profit and runner behavior.

## Key Findings

- Entry quality improved when the actual entry candle remained close to the pullback area.
- The short side improved after filtering weaker entry windows.
- Runner exits contributed positively in multiple review cycles.
- Allowing all positions to continue indefinitely increased risk; allowing only reduced-size runners to continue was cleaner.
- Daily max-loss events remained the largest warning category and require continued research.
- Explainable daily diagnostics improved the review process by making no-trade days auditable.
- Paper-trading preparation has begun in signal-monitoring mode before any automated execution.

## Current Interpretation

The strategy appears more stable when treated as a selective research system with strict entry quality and controlled risk behavior. It is not intended to replace broad market exposure or buy-and-hold investing.

## Next Research Questions

- Can daily max-loss events be prevented earlier through better entry filters?
- Are long and short systems better managed with fully separate parameters?
- Which results remain stable after walk-forward and out-of-sample validation?
- Does similar behavior appear in MNQ or other futures markets?
- Which no-trade days were correctly filtered, and which were missed opportunities?
- Do paper-trading signals remain aligned with private Python and TradingView review outputs?

## Confidentiality Note

The implementation, code, Pine script, data processing, and exact rules remain private.
