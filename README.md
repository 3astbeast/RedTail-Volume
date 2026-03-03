<p align="center">
  <img src="https://avatars.githubusercontent.com/u/209633456?v=4" width="160" alt="RedTail Indicators Logo"/>
</p>

<h1 align="center">RedTail Volume</h1>

<p align="center">
  <b>A buy/sell volume separation indicator for NinjaTrader 8 with volume statistics and daily range tracking.</b><br>
  See who's winning each bar at a glance — buyers or sellers — with on-chart stats panels.
</p>

<p align="center">
  <a href="https://buymeacoffee.com/dmwyzlxstj">
    <img src="https://img.shields.io/badge/☕_Buy_Me_a_Coffee-FFDD00?style=flat-square&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me a Coffee"/>
  </a>
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/3astbeast/RedTail-Volume/refs/heads/main/Screenshot%202026-03-03%20124510.png" width="800" alt="RedTail Market Structure Screenshot"/>
</p>
---

## Overview

RedTail Volume separates each bar's volume into buy and sell components using an OHLC proxy ratio, then stacks the winning side on top for a clear visual indication of who controlled the bar and by how much. It also includes Ripster-style volume statistics panels and a daily range tracking panel — giving you a real-time dashboard of volume and range context without needing a separate indicator.

---

## Buy/Sell Volume Separation

Volume is split using the candle's OHLC relationship as a proxy:

- **Buy Volume** = Total Volume × (Close − Low) / Range
- **Sell Volume** = Total Volume × (High − Close) / Range

The larger volume (the winner) is always plotted on top, and each side is color-coded (green for buyers, red for sellers by default). This means you can instantly see both the total volume and the directional bias of each bar.

When the candle has no range (High = Low), volume is split 50/50.

---

## Volume Statistics Panel

An on-chart statistics panel rendered in the top-right corner showing real-time volume context. Each metric can be independently toggled on or off.

**30-Day Average Volume** — The average daily volume over the past 30 trading days, calculated from a secondary daily data series. Provides a baseline for gauging whether today's activity is above or below normal.

**Today's Cumulative Volume** — Running total of all volume traded in the current session.

**% of 30-Day Average** — Today's cumulative volume as a percentage of the 30-day average. Quickly tells you if the day is tracking above or below normal pace.

**30-Bar Average** — Average volume over the past 30 bars on the current chart timeframe. Useful for comparing individual bars to recent activity.

**Current Bar Volume** — Volume of the current (developing) bar.

**% of 30-Bar Average** — Current bar volume as a percentage of the 30-bar average on the current timeframe.

**Buy/Sell Percentage** — The buy and sell percentage for the current bar. The panel text color changes to green when buyers dominate (>51%) or red when sellers dominate (>51%).

**Unusual Volume Highlighting** — When the % of 30-Day Average or % of 30-Bar Average exceeds the configurable threshold (default: 200%), the panel background changes color to flag unusual volume. A medium state (≥100%) also gets its own color treatment.

---

## Daily Range Panel

A separate on-chart panel rendered in the top-left corner tracking the day's price range relative to historical norms.

**30-Day Average Range** — The average daily high-to-low range over the past 30 trading days.

**Today's Range** — The current session's high-to-low range, updated in real time.

**% of Average Range** — Today's range as a percentage of the 30-day average. Color-coded: green background at ≥150% of average (extended range day), orange at ≥100%.

---

## SMA Overlay

An optional Simple Moving Average line plotted over the volume bars. Configurable period (default: 10). Useful for quickly seeing whether individual bars are above or below their recent average.

---

## Panel Color Customization

Both the Volume Statistics panel and the Daily Range panel have fully customizable color schemes with three states each:

**Volume Panel Colors**
- Normal text and background
- Medium volume text and background (≥100% of average)
- High/unusual volume text and background (≥ unusual volume threshold)
- Buy winning text color and sell winning text color

**Range Panel Colors**
- Normal text and background
- Medium range text and background (≥100% of average)
- High range text and background (≥150% of average)

---

## Plot Outputs

Three exposed plot series usable by strategies or other indicators:

- **Buy Volume** — The buy-side volume for each bar
- **Sell Volume** — The sell-side volume for each bar
- **Volume Average** — The SMA of total volume (when enabled)

---

## Installation

1. Download the `.cs` file from this repository
2. Open NinjaTrader 8
3. Go to **Tools → Import → NinjaScript Add-On**
4. Select the downloaded file and click **OK**
5. The indicator will appear in your **Indicators** list — add it to any chart

> **Note:** This indicator adds a secondary daily data series for the 30-day average calculations. NinjaTrader will automatically load the required daily bars when the indicator is applied.

---

## Part of the RedTail Indicators Suite

This indicator is part of the [RedTail Indicators](https://github.com/3astbeast/RedTailIndicators) collection — free NinjaTrader 8 tools built for futures traders who demand precision.

---

<p align="center">
  <a href="https://buymeacoffee.com/dmwyzlxstj">
    <img src="https://img.shields.io/badge/☕_Buy_Me_a_Coffee-Support_My_Work-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me a Coffee"/>
  </a>
</p>
