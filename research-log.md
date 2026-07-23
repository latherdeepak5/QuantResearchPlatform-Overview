# Research Log

This log records high-level research milestones. It intentionally avoids exact implementation rules, private code, and proprietary parameter details.

## 2026-07-23

### Unified Paper-Execution Review Layer

The private platform now records the same structured strategy lifecycle across
IBKR paper routing, Telegram, and a password-protected local dashboard. The
dashboard tracks open positions, entries, partial exits, final exits, realized
P&L, and monitor health without publishing private strategy rules or account
details.

### Broker-Held Emergency Protection

Every routed paper entry must now include an initial protective level. The
private router submits attached broker-held emergency protection, resizes the
remaining quantity after partial exits, and cancels the protection after final
closure. An entry is blocked when a valid protective level is unavailable.

This reduces disconnect risk for an existing broker position. It does not make
the full strategy independent of the monitoring computer: new signals, dynamic
management, Telegram, and dashboard updates still require a running process and
broker session.

### MNQ Management Research

The MNQ structure workflow was extended with partial-plus-runner management and
compared across several reward thresholds, retracement depths, hard-stop
assumptions, and step-trailing increments. The finer step-trailing alternative
was retained. A larger step and deeper entry variants were not promoted when the
comparison did not improve the accepted balance of return and drawdown.

### MGC Structure And Continuation Research

The MGC transfer study retained smaller position sizing and added:

- Directional moving-average confirmation.
- Same-direction continuation opportunities.
- Partial profit-taking with reduced-size runners.
- A confirmation-aware opposite-structure exit intended to avoid reacting to a
  single premature reversal marker.

The moving-average condition was also tested on MNQ but remained MGC-specific.
More aggressive retracement and trend-factor variants were restored to the
earlier baseline after comparison.

### Verification

- The private code compiled successfully.
- The private automated suite passed 67 tests.
- Generated ledgers, credentials, account identifiers, and executable strategy
  logic remain excluded from this public repository.

## 2026-07-17

### Guarded Paper-Execution Milestone

Advanced the private workflow from monitor-only broker alerts to guarded automatic execution in an IBKR paper account. Real-time broker data was verified independently before paper routing was enabled.

Public-safe controls now include:

- Paper-account-only validation; live-account routing remains blocked.
- Real-time market-data validation before orders are permitted.
- Contract-size caps and position-aware exit sizing.
- Persistent event identifiers and broker order references for duplicate protection.
- Separate strategy ownership so two MNQ systems cannot manage one position.
- A single-instance process lock after duplicate monitor processes were detected during operations.
- Quiet routine polling with visible fills, failures, Telegram alerts, and durable audit records.

### MNQ Market-Structure Research

Expanded the research platform beyond MES into MNQ opening-range, Supertrend/EMA, and market-structure studies. The accepted structure model requires directional agreement between independent conditions before a retracement entry is eligible, and it exits when the structure reverses.

A delayed-confirmation variant initially appeared reasonable but failed the full private-history comparison. It generated 50 additional trades with a 28% win rate, negative simulated net PnL, and profit factor below 1.0. The branch was removed from both private Python and chart-validation code. Recording this rejection prevents an attractive but weaker rule from being reintroduced later.

### Broader Research Library

Organized normalized local research inputs for MES, MNQ, MGC, MYM, BTC, and ETH by asset, symbol, and timeframe. Raw datasets remain excluded from public repositories. Added MGC structure/liquidity experiments and a larger automated regression suite while preserving accepted MES behavior.

An optional MGC broker-monitoring path was also evaluated with reduced sizing and partial-runner handling. It remains explicitly gated in the private workflow because the early transfer results are positive but not yet robust enough to become a default paper-execution stream.

### Verification

- Real-time MES broker quotes and current 15-minute history were confirmed.
- The complete private automated suite passed 37 tests before the milestone push.
- Raw data, credentials, account identifiers, generated reports, and executable private logic remain outside this overview repository.

## 2026-07-12

### Combined Strategy Monitoring Milestone

Extended the private research workflow from standalone backtesting into a combined monitor-only structure. The private project now evaluates both the existing pullback research path and an opening-range research path, then applies a one-position-at-a-time account view so overlapping ideas can be reviewed without double-counting exposure.

The latest private Python combined snapshot, after filtering weaker opening-range timing, was exceptional for the reviewed sample: 227 accepted positions, approximately 64.76% win rate, approximately +$124k simulated net PnL, 2.98 profit factor, and approximately -2.48% max drawdown. This result is being treated as a high-value research milestone, not as live-trading proof.

High-level purpose:

- Preserve the selective pullback system as the core research setup.
- Track an additional opening-range behavior separately enough to review its contribution.
- Avoid holding multiple overlapping research positions at the same time in the combined view.
- Compare private Python results with chart-platform historical testing where fill assumptions may differ.
- Track asset/system contribution so the pullback and opening-range components can be reviewed separately.
- Validate entry timing by year before promoting an opening-range timing rule into the primary research path.

### Broker-Fed Alert Readiness

Added the first broker-fed monitoring path in the private implementation.

Current public-safe scope:

- Connect to a broker desktop application or gateway once login is available.
- Fetch broker-sourced 15-minute futures bars.
- Run private Python diagnostics and signal evaluation.
- Produce entry, partial-exit, and final-exit alerts.
- Keep order routing disabled by default while signal parity is reviewed.

This remains a research and paper-monitoring milestone. It is not live trading.

### Phone Notification Test

Telegram phone alerts were configured and tested successfully through a standalone sample alert. This allows notification plumbing to be verified before broker connectivity or trade automation is enabled.

### Roadblocks And Fixes

Main blockers encountered:

- Broker Gateway login was not yet stable.
- Chart-platform strategy results differed materially from private Python research results.
- Telegram chat-id discovery required a specific API endpoint format.
- Terminal environment syntax differed between PowerShell and Git Bash.
- Secrets needed to be kept out of repository documentation.

How they were handled:

- Continued development in alert-only mode while delaying broker login troubleshooting.
- Treated private Python monitoring as the execution reference for the next paper-testing phase.
- Added safer setup notes for Telegram test alerts.
- Added placeholder environment examples instead of real secrets.
- Documented the full end-to-end flow and today's blockers in the private implementation repository.

## 2026-07-10

### Explainable Trade Review Layer

Added a public-safe research milestone around explainable diagnostics. The private project now produces a daily decision matrix that records, at a high level, why each reviewed day produced a trade or did not produce a trade.

High-level review fields include:

- Long-side checklist status
- Short-side checklist status
- Failed-filter categories
- Daily action summary
- Exit reason summary
- Realized PnL by reviewed day

This improves the research process because a no-trade day can now be reviewed as a decision, not as an empty result.

### Trade Journal Workflow

Built a journal-style review layer inspired by professional trading journals. The goal is to make every trade easier to audit after the fact without exposing private implementation logic.

High-level journal concepts:

- Entry context
- Direction and size
- Entry checklist status
- Exit timing
- Exit reason
- Realized result
- Review notes and mistake tags

### Paper-Trading Readiness

Started preparing a paper-trading workflow using a broker API connection in monitor-only mode.

Important research controls:

- Order routing remains disabled by default.
- The first live-data phase is signal monitoring, not automated trading.
- Paper-trading results will be compared against TradingView and private Python diagnostics before considering any live deployment.

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
- Which no-trade days were correctly filtered versus overly restricted?
- How closely will paper-trading signals match backtest and TradingView timing?
