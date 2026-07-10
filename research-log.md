# Research Log

This log records high-level research milestones. It intentionally avoids exact implementation rules, private code, and proprietary parameter details.

## 2026-07-09

### TradingView Deep-Test Review

Reviewed extended TradingView deep-test exports for MES futures across recent and older market regimes.

High-level observations:

- Strategy quality improved when entries were kept closer to the EMA pullback zone.
- Broad compatibility-mode entries created too many chase trades.
- Weak short-entry windows created outsized drawdown and were filtered.
- Allowing every open position to continue beyond the regular session increased risk.
- Allowing only scaled runners to continue after partial profit was more stable than holding full positions indefinitely.

### Exit Research

Tested multiple exit behaviors conceptually:

- Full-position session exit
- Partial profit-taking
- Runner continuation
- EMA-based runner exit
- ATR/trailing-stop based runner exit
- Daily max-loss guard behavior

High-level conclusion:

A cleaner structure is to close full positions when risk is not yet reduced, but allow reduced-size runner positions to continue when the trend persists.

### Entry Quality Research

Reviewed entries that occurred far away from the EMA pullback zone.

High-level conclusion:

The entry candle should still be near the pullback area. A prior pullback alone is not enough if price has already moved too far away before entry.

## Ongoing Questions

- Which entry windows remain robust across multiple market regimes?
- How much of performance depends on a small number of large runner trades?
- Can daily max-loss events be prevented earlier rather than handled as emergency exits?
- Should long and short strategies be treated as separate systems with separate risk rules?
- How does MES behavior compare with MNQ over the same testing periods?