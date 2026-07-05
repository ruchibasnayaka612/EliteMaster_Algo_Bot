# Ruchiranga's EliteMaster - Auto-Trading Bot for MT5

Ruchiranga's EliteMaster is an automated algorithmic trading engine designed for use within the MetaTrader 5 (MT5) trading platform. The system utilizes advanced institutional trading techniques such as Smart Money Concepts (SMC), ICT Fair Value Gaps (FVG), and Volume Profile Analysis to provide a fully automated means of executing high-probability trades within the Foreign Exchange market.

## Intellectual Property Note
This repository acts as an open-source portfolio showcase. In order to protect the proprietary components of the trading signals, the specific math used to generate the trade signals, the threshold values, and the specific trigger conditions have been removed from this repository. The main software architecture of the risk management algorithm and the overall structure are included here as an example of my ability to develop trading software with high levels of logic and design.

## Trading Systems and Signals
The trading robot monitors 20 different Forex currency pairs that have high volatility. When it identifies a trading opportunity, it executes a trade according to one of the following three distinct institutional strategies:

* **The Trap Hunter strategy (Strategy 2):** Detects fake breakouts and institutional liquidity at important Support/Resistance locations using a custom volume profile Point of Control to confirm the price movement.
* **The Trend Sniper strategy (Strategy 3):** Executes on 50% pullbacks from an institutional momentum candle only when prices on the longer-duration chart (4 Hours) and the shorter-duration chart (1 Hour) are trending in the same direction with high correlation.
* **The FVG Filler strategy (Strategy 4):** Detects the re-balancing of Fair Value Gaps after a period of expansion using Fibonacci retracement levels in conjunction with volume metrics to create optimal entries.

## Strict Risk Management
The execution of trades is completely automated based solely on pre-defined rules, eliminating any emotion associated with executing trades.

* Limits maximum active trades to 3.
* Risks exactly 6% of the account balance per trade.
* Targets a 1:3 Risk/Reward ratio.
* Moves stop loss to breakeven at 1:1 and closes 50% of the volume at 1:2 to protect profits.

## How to View/Run
1. Clone this repository.
2. Install dependencies via `pip install -r requirements.txt`.
3. Check `EliteMaster_Public.py` for the core structural logic.
