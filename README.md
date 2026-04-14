# Best Loser Wins: Momentum Risk Scaler

A high-performance, mobile-optimized Progressive Web App (PWA) designed for professional day traders. This tool automates the mathematics of **pyramiding (scaling)** into winning short positions while keeping a fixed, immutable risk profile.

## 🚀 Core Philosophy
The app is built on the **"Best Loser"** principle: 
- **Fixed Risk:** No matter how large the position grows, the total risk remains capped (default ₹47).
- **Mathematical Pyramiding:** Winning trades "fund" additional size. As the price moves in your favor, the app calculates the exact quantity to add and the new global stop-loss level.
- **NSE Precision:** All stop-loss outputs are automatically rounded down to the nearest 0.05 tick to satisfy Indian exchange requirements.

## ✨ Features
- **Dual-Mode Dashboard:** Instantly see 1.5x and 2.0x ATR risk distances and initial position sizes before entering a trade.
- **7-Level Flight Plan:** Generates a step-by-step execution map once a fill price is entered.
- **OLED Dark Mode:** High-contrast UI designed for the Pixel 9 and live market environments.
- **PWA Ready:** Installable on Android/iOS via "Add to Home Screen" for a native, distraction-free experience.
- **Safety Indicators:** Visual warnings (Red/Yellow) if the stop-loss distance becomes too tight (< 0.65 points) for high-volatility environments.

## 🛠️ Technical Implementation
- **Architecture:** Single-file HTML5/CSS3/JavaScript for zero-latency execution.
- **Input Optimization:** Utilizes `inputmode="decimal"` for immediate numeric keyboard access on mobile devices.
- **Rounding Logic:**
  ```javascript
  function nseRound(num) {
      return (Math.floor(num * 20) / 20).toFixed(2);
  }