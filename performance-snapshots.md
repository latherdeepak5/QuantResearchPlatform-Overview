# Performance Snapshots

This page records high-level public research snapshots. These are not trading recommendations and do not include exact strategy logic.

## Snapshot: MNQ Structure Hypothesis Comparison

This private comparison tested whether retaining an earlier structure signal until a later confirmation would improve opportunity capture. It did not. The original stricter confirmation remained superior and the delayed branch was rejected.

| Research view | Trades | Win rate | Net simulated PnL | Profit factor | Max drawdown |
|---|---:|---:|---:|---:|---:|
| Original confirmation baseline | 520 | 36.54% | +$109,217 | 1.39 | -$24,787.50 |
| Delayed-confirmation branch | 50 | 28.00% | -$6,095 | 0.73 | -$10,245.00 |
| Combined experimental result | 570 | 35.79% | +$103,122 | 1.34 | -$26,785.75 |

The reviewed sample used local MNQ 15-minute data from September 2024 through July 2026, five micro contracts, and estimated commissions without slippage. These are historical simulations, not paper or live returns.

## Snapshot: Combined MES One-Position Python Research

This private Python simulation combined the selective MES pullback research path with an opening-range research path, then replayed both through a one-position-at-a-time account view. The result was an unusually strong historical research snapshot, but it remains a simulation and is not live performance.

| Field | Value |
|---|---:|
| Instrument | MES |
| Timeframe reviewed | 15-minute futures bars |
| Account view | Combined one-position-at-a-time |
| Accepted positions | 227 |
| Win rate | 64.76% |
| Net simulated PnL | +$124,261.64 |
| Average PnL per position | +$547.41 |
| Profit factor | 2.98 |
| Max drawdown | -2.48% |

### Asset And System Contribution Snapshot

| Asset / System View | Positions | Win Rate | Net Simulated PnL | Profit Factor |
|---|---:|---:|---:|---:|
| MES combined one-position view | 227 | 64.76% | +$124,261.64 | 2.98 |
| MES timing-filtered opening-range contribution | 187 | 62.03% | +$105,822.50 | 2.85 |
| MES pullback contribution inside combined view | 40 | 77.50% | +$18,439.14 | 4.38 |

### Yearly Combined Snapshot

| Year | Accepted Positions | Win Rate | Net Simulated PnL | Profit Factor |
|---|---:|---:|---:|---:|
| 2024 | 33 | 66.67% | +$13,622.64 | 2.92 |
| 2025 | 128 | 62.50% | +$61,977.85 | 2.72 |
| 2026 | 66 | 68.18% | +$48,661.15 | 3.49 |

![Combined Strategy Snapshot](assets/combined-strategy-snapshot.svg)

## Snapshot: MES Deep-Test Review, 2020-2026

| Field | Value |
|---|---:|
| Instrument | MES |
| Approximate range | Jan 2020 - Jul 2026 |
| Net profit | +$22,682.50 |
| Return on initial capital | 22.68% |
| Profit factor | 1.53 |
| Max drawdown, intrabar | 7.10% |
| Long contribution | +$12,922.50 |
| Short contribution | +$9,760.00 |
| Grouped positions reviewed | 155 |

## Snapshot: MES Recent Deep-Test Review, 2024-2026

| Field | Value |
|---|---:|
| Instrument | MES |
| Approximate range | Sep 2024 - Jul 2026 |
| Net profit | +$18,286.25 |
| Return on initial capital | 18.29% |
| Profit factor | 1.658 |
| Max drawdown, intrabar | 8.82% |
| Long contribution | +$10,820.00 |
| Short contribution | +$7,466.25 |
| Grouped positions reviewed | 78 |

## Snapshot: Private Python Diagnostics Review, 2024-2026

| Field | Value |
|---|---:|
| Instrument | MES |
| Approximate range | Sep 2024 - Jul 2026 |
| Final capital | $121,307.52 |
| Total return | 21.31% |
| Profit factor | 5.27 |
| Win rate | 84.06% |
| Max drawdown | -2.25% |
| Long contribution | +$12,565.37 |
| Short contribution | +$8,782.14 |
| Closed trade rows reviewed | 69 |

## Monthly Consistency Snapshot

| Metric | Value |
|---|---:|
| Profitable months reviewed | 14 of 18 |
| Best month | Apr 2026, +$5,927.06 |
| Weakest month | Jan 2026, -$1,127.00 |

## Exit-Quality Snapshot

| Exit Category | Closed Rows | Aggregate PnL |
|---|---:|---:|
| Partial profit exits | 29 | +$8,190.20 |
| Runner exits | 11 | +$8,626.50 |
| Stop / trailing exits | 16 | +$4,007.57 |
| Daily max-loss exits | 3 | -$2,473.00 |


## Visual Snapshot: Python Diagnostics

![Python Diagnostics Snapshot](assets/python-diagnostics-snapshot.svg)
## Interpretation Notes

- Results are historical simulations and may not match live execution.
- Gross profit is less important than clean trade selection, drawdown behavior, and stability across regimes.
- Daily max-loss exits are reviewed as a risk warning category.
- Runner contribution is tracked separately from initial partial profit-taking.
- Long and short systems are reviewed separately because they often behave differently.
- Python diagnostics are used to understand behavior; TradingView deep tests are used as a separate validation layer.
- Daily decision matrices are used to review both trade days and no-trade days.
- Guarded paper execution is treated as a validation step, not proof of live readiness.
- The combined one-position snapshot is considered exceptional historically, but it must still pass broker-fed alert monitoring before any order-routing decision.

## What These Snapshots Do Not Show

These snapshots do not include:

- Exact rules
- Source code
- Pine script
- Trade-by-trade exports
- Private optimization files
- Live trading performance

## Research Standard

A result is considered more useful when it improves risk-adjusted behavior, reduces avoidable drawdown, and remains interpretable across different market periods.
