# ⚡ AlphaDesk
### AI-Powered Day Trading Platform for US Stocks & ETFs

AlphaDesk is a production-oriented, local-first automated day-trading platform for US stocks and ETFs. It combines an asynchronous trading engine, algorithmic strategies, machine-learning-assisted signal evaluation, market-regime detection, risk management, event-driven backtesting, and a real-time trading terminal.

> **Portfolio repository:** This public repository documents the project for demonstration and recruiter review. The core application source remains in a separate private repository. This repository is documentation-only and is not a runnable copy of the application.

## Highlights

- **Three operating modes:** Demo mode uses deterministic synthetic market data; paper mode uses real market data with simulated fills; live mode can route real orders through a supported broker when explicitly configured and enabled.
- **AI-assisted strategy pipeline:** Opening Range Breakout (ORB), VWAP Reversion, EMA Momentum, and RSI(2) Dip-Buy strategies feed a pipeline that combines a locally trained gradient-boosting model, market-regime detection (trend, range, volatile), dynamic strategy weighting, and signal-conflict resolution.
- **Risk management first:** ATR-based position sizing, bracket exits, daily-loss halts, drawdown protection, loss-streak cooldowns, end-of-day liquidation, Pattern Day Trader (PDT) safeguards, and price/liquidity filters.
- **Event-driven backtesting:** Historical replay through the trading stack, next-bar-open fills, adverse stop-loss slippage, conservative stop/target tie-breaking, causal indicators, and metrics such as Sharpe ratio, Sortino ratio, maximum drawdown, profit factor, expectancy, and R-multiples.
- **Real-time terminal:** React and TypeScript interface with candlestick charts, EMA/VWAP overlays, trade markers, watchlists, positions, orders, trades, logs, AI insights, equity curve, strategy controls, and WebSocket updates.
- **Extensible architecture:** Registries for broker adapters, market-data providers, strategies, indicators, and AI models.

Feature availability depends on configuration and build version. This description is based on the private project's README and does not mean that live trading is enabled or that any strategy is profitable.

## High-level architecture

```text
React + TypeScript Trading Terminal
     │ REST API / WebSocket
     ▼
FastAPI + Event Hub
     ▼
Async Trading Engine
     ├── Data Manager ── Provider Registry
     ├── Technical Indicators
     ├── Market-Regime Detector
     ├── Strategy Registry
     ├── ML Signal Gate + Strategy Weights
     ├── Risk Manager
     ├── Broker Registry ── Paper Simulator / Broker Adapter
     ├── Portfolio Tracker
     └── Event-Driven Backtester
              │
              ▼
     Persistent Orders, Trades,
     Equity, Settings & Backtests
```

The diagram is a high-level summary. Proprietary source code, model artifacts, private thresholds, and implementation details are intentionally excluded from this public repository.

## Technology stack

- **Backend:** Python, FastAPI, asynchronous engine
- **Frontend:** React, TypeScript, lightweight-charts, Zustand
- **Persistence:** SQLite and SQLAlchemy
- **Real-time communication:** REST APIs and WebSockets
- **Quantitative trading:** technical indicators, intraday strategies, event-driven backtesting, performance analytics
- **AI/ML:** local gradient-boosting model, signal scoring, regime detection, strategy weighting, AI insights
- **Quality engineering:** automated backend tests for indicators, fills, risk rules, portfolio accounting, strategies, backtesting, and API behavior

## Risk and testing philosophy

The project emphasizes controlled execution and conservative simulation: stop-loss slippage, stop/target tie-breaking, protection against look-ahead bias, position-sizing limits, daily loss halts, drawdown protection, cooldowns, and end-of-day controls. The private project README reports a backend test suite covering indicators, paper fills, risk rules, portfolio accounting, strategy scenarios, backtesting, and API behavior. Test counts and results may change as development continues.

## Demo materials

- [Demo walkthrough and publication checklist](docs/DEMO_GUIDE.md)
- [Sanitized example configuration](demo/config.example.yaml)

Screenshots and video demonstrations may be added as sanitized assets become available. Do not publish API keys, tokens, broker account identifiers, personal data, real account records, private strategy parameters, or proprietary source code.

## Project scope and security

This public repository is a portfolio overview, not the application source. It does not include the private trading engine, broker credentials, environment files, private model artifacts, or proprietary strategy implementation. The demo configuration is illustrative and is not a production configuration.

## Disclaimer

AlphaDesk is a software engineering project for education and research, not financial advice or a guarantee of trading performance. Day trading involves substantial risk, and automation can amplify losses. Backtested, simulated, and synthetic results do not guarantee future performance. Use demo and paper modes for evaluation; live trading carries the risk of losing capital.

---

**Built by Sai Kiran** · [GitHub profile](https://github.com/saikiranpeddineni)