# Aggressive Order Pressure + MTF Volatility — STALGO

**TradingView Pine Script® v6 indicator by STALGO — Sandaru Tharushka.**

A compact TradingView dashboard for estimated buy/sell pressure and multi-timeframe volatility.

![STALGO dashboard](assets/stalgo-dashboard.jpg)

## Features

- Estimated **BUY %** and **SELL %**
- Signed **Pressure** score
- Pressure states: **STRONG BUY / BUY / NEUTRAL / SELL / STRONG SELL**
- **1m / 5m / 10m** volatility monitoring
- Volatility regimes: **LOW / MID / HIGH**
- Compact on-chart dashboard
- Optional candle coloring during strong pressure
- Alerts for strong BUY/SELL pressure
- Alerts for high volatility

## How the pressure estimate works

The indicator estimates buying and selling activity from each candle's closing position inside its high-low range, weighted by the volume data available on the selected TradingView symbol. The estimated buy/sell values are smoothed before the pressure score is calculated.

- Positive pressure = stronger estimated buying pressure
- Negative pressure = stronger estimated selling pressure
- Near zero = relatively balanced pressure

> **Important:** This indicator does **not** use true exchange Level 3 / MBO order-book aggressor data. Pressure is an estimate based on OHLC and the volume/tick-volume supplied by the selected TradingView data feed.

## Volatility model

Volatility is based on **ATR as a percentage of price**, normalized against its own recent historical distribution with a z-score.

| Setting | Default |
|---|---:|
| Pressure smoothing | 10 |
| Strong pressure level | 35 |
| Normal pressure level | 10 |
| ATR length | 14 |
| Volatility lookback | 100 |
| HIGH threshold | 0.50 |
| LOW threshold | -0.50 |

## Installation

1. Open **TradingView**.
2. Open **Pine Editor**.
3. Open `STALGO_Aggressive_Order_Pressure_MTF_Volatility.pine` from this repository.
4. Copy the full code into Pine Editor.
5. Click **Save**.
6. Click **Add to chart**.
7. Adjust the settings for your instrument and timeframe if required.

## Dashboard values

| Metric | Meaning |
|---|---|
| BUY | Estimated buy-side percentage |
| SELL | Estimated sell-side percentage |
| PRESSURE | Signed pressure score and state |
| 1M VOL | 1-minute ATR-based volatility regime |
| 5M VOL | 5-minute ATR-based volatility regime |
| 10M VOL | 10-minute ATR-based volatility regime |

## Usage

This project is intended for **market research and analytical use**. It should not be treated as a standalone buy/sell signal or a guarantee of future market movement.

## Author

### STALGO
**Sandaru Tharushka**

GitHub: [@SandaruTharushka](https://github.com/SandaruTharushka)

## License

The Pine Script source contains a **Mozilla Public License 2.0** notice. Refer to the source-file header for licensing details.
