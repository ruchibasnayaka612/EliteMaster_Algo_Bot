# EliteMaster Algo Trading Engine (v2.6.1)

A fully autonomous, quantitative trading engine built for MetaTrader 5 using Python. I designed this system to execute trades strictly based on Smart Money Concepts (SMC), Volume Profiling (FRVP), and precise Fibonacci levels, eliminating human emotion from the trading process.

🎥 **Project Showcase:** [Watch the EliteMaster System Showcase on YouTube](https://www.youtube.com/watch?v=ypDcLLp-pZk)

---

### 🛡️ Intellectual Property Note
This repository serves as my open-source engineering portfolio. To protect my proprietary edge, the exact mathematical formulas, volume thresholds, and signal generation logic have been abstracted out of the public code (`EliteMaster_Public.py`). What you see here is the structural architecture and risk management framework.

---

### ⚙️ Core Architecture & Features

* **Crash Recovery (Fault-Tolerant Memory):** The bot continuously saves active trade data to a local `bot_state.json` file. If the VPS restarts, MT5 crashes, or the internet drops, the engine simply wakes up, reads the JSON file, and resumes trailing stops without missing a beat.
* **Time Guard Filter:** Operates strictly between **07:00 and 23:30 (Server Time)**. I programmed this to intentionally avoid the low-liquidity and high-spread chop during the Asian midnight sessions.
* **Live Telegram Alerts:** Connected to a custom Telegram Bot API. It sends instant push notifications to my phone whenever a trade opens, hits breakeven, or closes in profit.

---

### 🧠 The 4 Independent Strategies
Instead of relying on one pattern, the engine runs 4 distinct strategies to adapt to different market conditions:

1. **S1: The Reversal Sniper (1H & 15M):** *(New in v2.6)* Scans dual timeframes independently to catch trend exhaustion. It looks for strong momentum shifts (0.8 ATR impulse candles) combined with RSI divergence and Volume Point of Control (POC) to enter at the exact turning point.
2. **S2: The Trap Hunter (15M):** Identifies where retail traders are getting trapped. It waits for support/resistance fakeouts (liquidity grabs) and enters only when the 200 EMA and volume data confirm the real institutional direction.
3. **S3: The Trend Sniper (4H / 1H / 15M):** A pure momentum follower. When all three timeframes align, it jumps into strong trends and safely exits exactly 2 pips before the previous swing high/low (Zero-Fib Target).
4. **S4: The FVG Filler (4H / 15M):** Looks for deep pullbacks. It detects 4H Fair Value Gaps (imbalances) and enters on the 15M chart when price hits the Golden Fibonacci zone (0.382 - 0.618) alongside high volume.

---

### ⚖️ Strict Risk & Trade Management
Active trades are managed 24/7 by a dynamic loop to ensure zero unnecessary losses:

* **Fixed 3.5% Risk:** The system dynamically calculates lot sizes based on the account balance and the exact pip distance to the Stop Loss. Risk never exceeds 3.5% per trade.
* **Phase 1 (Zero-Risk Lock):** As soon as a trade reaches a 1:1.5 Risk/Reward ratio, the bot automatically closes 25% of the position to secure profit and instantly moves the Stop Loss to Entry (Break-Even).
* **Phase 2 (Smart Fib Trailing):** If the trend continues past the -0.136 Fibonacci extension, the bot trails the Stop Loss safely behind the 0.05 level, locking in maximum gains while giving the trade room to breathe.
