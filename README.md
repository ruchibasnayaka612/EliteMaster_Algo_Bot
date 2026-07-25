# 🤖 EliteMaster: Automated Institutional Algo-Trading Engine (Python & MT5)

**Version 2.2.2 (Ultimate Sniper Architecture + Time Guard + Crash Recovery)**

Ruchiranga's **EliteMaster** is an autonomous, quantitative algorithmic trading engine engineered for institutional-grade execution within the MetaTrader 5 (MT5) ecosystem. The system integrates Smart Money Concepts (SMC), Volume Profiling (FRVP), and ICT Fair Value Gaps (FVG) with dynamic multi-phase risk management and fault-tolerant state persistence to automate high-probability trade execution in the Forex market.

---

## 🎥 Project Showcase

I have documented the system architecture, quantitative logic, and live execution of this engine. Watch the project in action: 
👉 **[Watch the EliteMaster System Showcase on YouTube](#)** *https://www.youtube.com/watch?v=ypDcLLp-pZk*

---

## 🛡️ Intellectual Property & Portfolio Note

This repository serves as an open-source engineering portfolio showcase. To protect proprietary signal generation logic, threshold values, and specific institutional trigger conditions, those core components have been abstracted in `EliteMaster_Public.py`. 

This repository demonstrates my software engineering and quantitative finance capabilities in:
* **Fault-Tolerant System Architecture:** Developing resilient, multi-threaded trading software with automated crash recovery.
* **Quantitative Risk Management:** Implementing algorithmic risk guardrails, dynamic lot sizing, and multi-phase trailing logic.
* **Asynchronous Data Integration:** Real-time OHLCV data processing between Python and MT5 terminals with instant push notifications.

---

## ⚙️ Core Capabilities & System Architecture

* **Fault-Tolerant State Persistence (Crash Recovery):** Engineered with real-time local JSON storage (`bot_state.json`). If the system encounters a power outage, network disconnection, or system reboot, the engine autonomously restores exact position memories, partially closed ticket IDs, and trailing states—ensuring zero management lapse on active trades.
* **Time Guard Execution Filter:** Integrates an automated trading window (**07:30 to 23:00 Server Time**) to prevent algorithmic order execution during low-liquidity, high-spread midnight sessions.
* **Standalone Deployment:** Compiled into an executable (`.exe`) standalone software, eliminating dependency on IDEs or background Python environments during 24/7 live server execution.
* **Real-Time Push Notifications:** Connected asynchronously to a Telegram Bot API to deliver instant alerts for order placements, profit securing, zero-risk locks, and smart trailing events.
* **Execution Logging:** Persists all executed trade parameters into a structured local storage (`Trade_Execution_Log.csv`) for post-trade quantitative analysis.

---

## 📈 Algorithmic Trading Strategies

The engine continuously scans **20 high-volatility Forex & Commodity pairs** across multiple timeframes using a 200 EMA structural trend filter:

* **S2: The Trap Hunter (1H / 15M):** Identifies institutional liquidity sweeps and false breakouts. Utilizes rolling fractals for Break of Structure (BOS) mapping and verifies execution within the Fixed Range Volume Profile (FRVP) Point of Control (POC).
* **S3: The Trend Sniper (4H / 1H):** Executes on institutional momentum pullbacks aligned with cross-timeframe trend continuity (4H & 1H 200 EMA alignment). Validates high-volume engulfing candles within dynamic value areas.
* **S4: The FVG Filler (4H / 15M):** Detects institutional re-balancing of 4H Fair Value Gaps (FVG) aligned with the macroeconomic trend. Calculates precise mitigation levels using Fibonacci retracement confluence with volume POCs.

---

## ⚖️ Strict Quantitative Risk Management

The system operates on an emotionless, rules-first quantitative architecture designed for strict capital preservation:

* **Global Exposure Cap:** Maximum of **3 concurrent active global positions** (`MAX_GLOBAL_TRADES = 3`) to prevent over-leveraging and margin exhaustion.
* **Fixed Risk Profile:** Enforces a **strict 5.0% account equity risk** per executed trade. Position sizes are dynamically computed in real-time (`calculate_dynamic_lot`) using live symbol tick values and tick sizes.
* **Algorithmic RR Guardrails:** Automatically evaluates Fibonacci extension targets before order placement:
  * **RR < 1:1:** Instantly rejects the trade to prevent negative expectancy.
  * **1:1 ≤ RR ≤ 1:1.5:** Overrides the target to a safe **1:2 default Risk/Reward fallback**.
  * **RR > 1:1.5:** Targets the precise **Fibonacci -0.272 institutional extension target**.

### 🎯 Multi-Phase Sniper Trade Manager
Active positions are monitored 24/7 by an autonomous dynamic trade management loop:
1. **Phase 1 (Profit Securing & Zero-Risk Lock):** Upon reaching a **1:1.5 Risk/Reward ratio**, the engine automatically liquidates **25% of the position volume** to bank realized profits and immediately modifies the Stop-Loss to Entry (**Break-Even**).
2. **Phase 2 (Smart Trailing):** As price momentum breaches the **Fibonacci -0.136 extension level**, the Stop-Loss dynamically trails and locks at the **Fibonacci 0.05 safety buffer**, securing maximum trend extraction with zero downside exposure.

---

## 🚀 How to Explore

1. **Clone this repository:**
   ```bash
   git clone [https://github.com/ruchibasnayaka612/EliteMaster_Algo_Bot.git](https://github.com/ruchibasnayaka612/EliteMaster_Algo_Bot.git)
