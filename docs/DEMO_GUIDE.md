# AlphaDesk Demo Guide

This repository is a public portfolio/demo companion for AlphaDesk. It does not contain the private trading engine.

## Demo walkthrough
1. Overview — introduce AlphaDesk as a local-first platform for US stocks and ETFs.
2. Operating modes — explain demo mode (deterministic synthetic data), paper mode (real market data without live orders), and live brokerage execution. Demonstrate only modes enabled and verified in the current build.
3. Signal pipeline — show symbol discovery, strategy signal generation, ML-assisted evaluation, market-regime context, risk checks, and order eligibility.
4. Strategies — describe ORB, VWAP Reversion, EMA Momentum, and RSI(2) Dip-Buy at a high level. Do not publish proprietary parameters or source code.
5. Risk controls — demonstrate position sizing, bracket exits, daily loss and drawdown limits, loss-streak cooldowns, liquidity filters, PDT safeguards, and end-of-day liquidation where implemented.
6. Backtesting — explain event-driven replay and metrics. Clearly label simulated/historical results; do not imply future performance.
7. Terminal — show sanitized screenshots of charts, watchlists, positions, orders, equity curves, and monitoring.

## Recommended demo assets
- Sanitized terminal screenshots with account identifiers and sensitive values removed.
- A short screen recording using demo or paper mode.
- A high-level architecture diagram.
- A sample configuration containing placeholders only.
- A note stating which features are implemented, experimental, or planned.

## Security checklist
Before publishing any asset, confirm it contains no API keys, tokens, passwords, environment files, private keys, broker account identifiers, personal/customer data, proprietary strategy source, private thresholds, or sensitive trade records.

## Important
Do not use this public repository to host or mirror the private AlphaDesk/Betadesk source tree. Add only deliberately sanitized demo materials.