# Validation Methodology

The project uses a multi-step validation workflow to avoid trusting a single backtest result.

## Primary Validation Layers

### Python Backtesting

Private Python backtests are used for fast iteration, diagnostics, and structured analysis. These tests help identify broad weaknesses such as poor entry windows, exit-reason clustering, and drawdown patterns.

### TradingView Deep Backtesting

TradingView deep-test exports are used as an independent validation layer. The goal is to compare behavior against a separate execution engine and longer historical samples where available.

### Export Analysis

TradingView exports are reviewed by grouping split trade rows into real positions. This avoids overcounting partial exits and gives a clearer view of actual position-level behavior.

## What Gets Reviewed

- Net profit
- Profit factor
- Max drawdown
- Long/short contribution
- Win rate
- Average win versus average loss
- Exit reason breakdown
- Entry-time breakdown
- Monthly and yearly consistency
- Daily max-loss frequency
- Runner contribution

## Interpretation Principles

- A profitable backtest is not enough by itself.
- Lower drawdown with cleaner trade selection is preferred over noisy high gross profit.
- Daily max-loss exits are treated as a sign that entries or stops need improvement.
- Long and short performance are reviewed separately.
- Recent-market performance is compared against older data to reduce recency bias.

## Limitations

Backtests and deep tests do not perfectly model live execution, fills, spread, latency, data revisions, psychological pressure, or broker-specific behavior. Results are research artifacts, not guarantees.