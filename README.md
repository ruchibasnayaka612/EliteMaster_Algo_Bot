# 🤖 EliteMaster: Automated Institutional Algo-Trading Engine (Python & MT5)

Ruchiranga's EliteMaster is an automated algorithmic trading engine designed for professional-grade execution within the MetaTrader 5 (MT5) platform. The system leverages advanced concepts like Smart Money Concepts (SMC), ICT Fair Value Gaps (FVG), and Volume Profile Analysis to automate high-probability trade execution in the Forex market.

## 🎥 Project Showcase
I have documented the system architecture and live execution of this engine. Watch the project in action:
**[Watch the EliteMaster System Showcase on YouTube](https://youtu.be/ypDcLLp-pZk)**

## 🛡️ Intellectual Property Note
This repository serves as an open-source portfolio showcase. To protect proprietary signal generation logic, threshold values, and specific trigger conditions, those components have been abstracted. This repository demonstrates my capability in:
*   **System Architecture:** Developing robust, multi-threaded trading software.
*   **Risk Management Algorithms:** Implementing strict, emotionless trade execution logic.
*   **Data Integration:** Real-time data processing between Python and MT5 terminals.

## 📈 Trading Strategies
The engine monitors 20 high-volatility Forex pairs, identifying opportunities via:
*   **The Trap Hunter (Strategy 2):** Identifies fake breakouts and institutional liquidity traps using custom Volume Profile Point of Control.
*   **The Trend Sniper (Strategy 3):** Executes on 50% pullbacks from momentum candles, utilizing cross-timeframe correlation (4H & 1H).
*   **The FVG Filler (Strategy 4):** Detects institutional re-balancing of Fair Value Gaps using Fibonacci retracement and volume metrics.

## ⚖️ Strict Risk Management
The system is built on a "rules-first" philosophy to eliminate emotional bias:
*   **Trade Cap:** Maximum 3 concurrent active trades.
*   **Risk Profile:** Fixed 6% account risk per trade.
*   **Performance:** Targets a 1:3 Risk/Reward ratio.
*   **Safety Logic:** Stop-loss moves to breakeven at 1:1; 50% volume closure at 1:2 to secure profits.

## 🚀 How to Explore
1. Clone this repository: `git clone https://github.com/ruchibasnayaka612/EliteMaster`
2. Install requirements: `pip install -r requirements.txt`
3. View core architecture in `EliteMaster_Public.py`.

---
*Developed by Ruchiranga Basnayaka | [LinkedIn Profile](https://www.linkedin.com/in/ruchiranga-basnayaka/)*
