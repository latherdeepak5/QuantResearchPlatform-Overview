# Risk Principles

This project treats risk management as a core part of strategy design, not an afterthought.

## Current Risk Philosophy

### Reduce Risk Before Letting Trades Run

The research currently favors taking partial profits before allowing runner contracts to continue. A reduced-size runner can participate in extended moves while limiting full-position exposure.

### Avoid Late Full-Position Drift

Full positions that have not reduced risk should not be allowed to drift without control late in the session. This behavior has shown a tendency to increase drawdown.

### Treat Daily Max-Loss Exits As Warnings

A daily max-loss exit is useful as a guardrail, but repeated daily max-loss exits are a warning. The preferred goal is to prevent low-quality entries before they reach emergency-loss territory.

### Separate Long And Short Behavior

Long and short trades often behave differently. They should be analyzed separately instead of assuming one shared rule set is optimal for both sides.

### Keep Runner Logic Controlled

Runner continuation is useful only when risk has already been reduced. Runners should still have clearly defined exit logic such as trend deterioration, EMA behavior, ATR/trailing stop, or other risk controls.

### Treat Execution Safety As Strategy Risk

Broker automation introduces risks that do not appear in a backtest. Paper execution therefore requires account validation, real-time data checks, size limits, position-aware exits, duplicate-event protection, and a single running monitor. Live-account routing remains outside the current project scope.

### Keep Protection At The Broker

An accepted paper entry should not depend entirely on the local Python process
remaining connected. Routed entries therefore include broker-held emergency
protection, which is adjusted as the position is reduced and removed after final
closure. Dynamic management still depends on the monitor, so this protection is
a safety floor rather than a replacement for operational monitoring.

### Reject Plausible Ideas When The Evidence Weakens

A change is not accepted merely because it creates more trades or looks sensible on a chart. A recent MNQ delayed-confirmation variant reduced profit factor and increased drawdown, so it was removed even though it expanded opportunity count.

## Practical Review Questions

Before accepting a strategy change, the research asks:

- Did drawdown improve or worsen?
- Did daily max-loss exits increase?
- Did the change help both long and short trades, or only one side?
- Did the change remove mostly bad trades or also remove too many high-quality winners?
- Does the improvement hold over older data, not just the most recent period?

## Risk Notice

Futures trading involves substantial risk. This overview is for research documentation only and is not trading advice.
