# MNQ Structure Research Case Study

This public-safe case study summarizes a private Micro E-mini Nasdaq-100 futures research cycle. It intentionally excludes executable logic, source code, private datasets, and complete parameter definitions.

## Objective

Develop a selective market-structure strategy for a nearly continuous futures session while keeping it operationally separate from the established MES research stack.

## Research Process

The private workflow evaluated several independent families of ideas:

- Opening-range behavior.
- Supertrend and moving-average alignment.
- Market-structure changes and continuation events.
- Retracement-based entries after confirmation.
- Structure, volatility, and opposite-signal exits.
- Long and short performance separately.

Ideas were first tested in Python, then represented visually on a chart platform, and finally integrated into broker-paper monitoring only after the entry and exit lifecycle was explainable.

## Accepted Direction

The retained structure model requires directional agreement on the same completed bar before a pullback entry becomes eligible. This stricter requirement intentionally sacrifices trade frequency to avoid acting on stale structure information.

The model is isolated from the MNQ opening-range monitor. Only one MNQ strategy may own paper-order routing at a time, preventing two systems from closing or reversing the same broker position.

## Rejected Variant

The research tested retaining an earlier structure event while waiting for a later trend confirmation, then entering on a deeper retracement. The hypothesis was that it could recover valid trends missed by strict same-bar confirmation.

The evidence rejected that idea:

| Research view | Trades | Win rate | Net simulated PnL | Profit factor |
|---|---:|---:|---:|---:|
| Original confirmation baseline | 520 | 36.54% | +$109,217 | 1.39 |
| Delayed-confirmation branch | 50 | 28.00% | -$6,095 | 0.73 |

The delayed branch was removed because it lowered combined profit factor and increased drawdown. This is an example of the platform's core research standard: more signals are not useful when their expected quality is negative.

## Paper-Execution Controls

The selected MNQ model can run through the private IBKR paper workflow with:

- Real-time broker-data validation.
- Paper-account-only enforcement.
- Fixed maximum quantity.
- Position-aware entry and exit checks.
- Persistent event and order-reference deduplication.
- Telegram lifecycle notifications.
- A single-instance monitor lock.

This remains paper execution. Live-account routing is blocked.

## Next Questions

- Does broker-paper fill behavior remain consistent with the private event model?
- How much performance is concentrated in a small number of extended moves?
- Are separate overnight and regular-session controls justified?
- Can execution quality improve without weakening the same-bar confirmation standard?

## Risk Notice

All figures are historical simulations and exclude some real-world effects such as slippage. They do not guarantee future results and are not trading advice.
