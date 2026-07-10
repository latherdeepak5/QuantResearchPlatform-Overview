# Quant Research Platform - Public Overview

This repository is a public, read-only overview of an active quantitative research project focused on futures strategy research, backtesting, and TradingView deep-test validation.

The implementation code, Pine scripts, datasets, private research notebooks, and executable strategy logic are intentionally not included here.

## Purpose

The project tracks high-level research progress for a futures trading research platform, including:

- Strategy research notes
- Backtest summaries
- Risk-management findings
- TradingView deep-test observations
- Future improvement ideas

This repository is meant for visibility and communication only. It is not the working source-code repository.

## Current Research Focus

The current research is focused on Micro E-mini S&P 500 futures (`MES`) trend-pullback behavior, with special attention to:

- Avoiding entries that chase price too far from the EMA pullback zone
- Improving partial profit-taking behavior
- Keeping scaled runners alive when trend conditions continue
- Reducing large daily-loss events
- Comparing Python backtests with TradingView deep-test exports
- Separating strong entry windows from weak entry windows

## Current High-Level Findings

Recent research suggests the strategy behaves better when:

- Entries remain close to the EMA 21 / EMA 50 pullback area
- Weak early short-entry windows are filtered out
- Full positions are not allowed to drift uncontrolled late in the session
- Scaled runner contracts are allowed to continue after partial profits
- Daily max-loss exits are treated as a warning sign, not a preferred exit style

These findings are still under active validation and may change as more data is tested.

## What Is Not Included

This repository does not include:

- Source code
- Backtester implementation
- TradingView Pine Script
- Raw data
- Private optimization files
- Exact entry or exit logic
- Production trading instructions

## Risk Notice

This project is for research and educational purposes only.

Nothing in this repository is financial advice, investment advice, or a recommendation to trade futures, securities, options, crypto, or any other instrument. Futures trading is risky and can result in losses greater than the initial capital committed.

Backtest and deep-test results are historical simulations. They do not guarantee future performance.

## Ownership And Usage

Copyright (c) 2026 latherdeepak5. All rights reserved.

No permission is granted to copy, redistribute, sell, sublicense, reverse-engineer, or use private implementation details from the underlying project. Public text in this overview is provided only so collaborators and reviewers can understand the high-level research direction.

## Status

Active research. This overview will be updated as the project evolves.