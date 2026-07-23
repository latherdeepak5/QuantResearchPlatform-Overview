# Roadmap

This roadmap lists high-level future research tasks. It does not disclose private implementation details.

## Near-Term Research

- Continue validating MES over longer historical TradingView deep-test samples
- Refine long-entry windows after reviewing older data
- Review daily max-loss clusters and identify preventable entry patterns
- Compare results using different EMA-distance tolerances
- Separate long-side and short-side parameter reviews
- Review daily decision matrices to separate valid no-trade days from overly restrictive filters
- Compare broker-fed paper alerts with TradingView and private Python diagnostics
- Validate combined one-position behavior during live market monitoring
- Track alert timing, missed signals, duplicate signals, and broker-data differences
- Track whether the exceptional combined Python snapshot remains stable in broker-fed paper monitoring
- Reconcile every broker-paper fill against the expected private strategy event
- Track paper slippage, rejected orders, missed exits, and reconnect behavior
- Validate that single-strategy MNQ ownership remains reliable across long-running sessions
- Reconcile dashboard lifecycle records against every broker-paper fill
- Verify broker-held stop quantities after partial fills and reconnects
- Test recovery across IB Gateway daily auto-restarts and the weekly manual login

## Medium-Term Research

- Continue comparing MNQ behavior against MES without sharing one parameter set
- Review volatility-regime sensitivity
- Study monthly and yearly consistency
- Track runner contribution versus partial-exit contribution
- Build clearer reporting around position-level drawdown
- Maintain a journal-style review process for entry quality, exit quality, and mistake tags
- Accumulate several months of paper-execution evidence before changing any account scope
- Continue validating broker-held protective orders during paper execution

## Longer-Term Research

- Add walk-forward style validation
- Study out-of-sample behavior by market regime
- Improve robustness checks across symbols and timeframes
- Build a cleaner public reporting layer that shows results without exposing private logic
- Document research decisions as versioned public notes
- Evaluate whether broker-paper results remain aligned before considering limited live testing
- Compare the same research framework across other futures and timeframes

## Public Repository Goals

This overview repository should remain focused on:

- Research direction
- High-level findings
- Methodology
- Risk philosophy
- Non-sensitive summaries

The private implementation repository remains separate.
