HFM SMART TRADER ANDROID — MANUAL EDITION
===========================================

WHAT THIS IS
A phone-first, offline-first Progressive Web App (PWA) rebuild of the feature areas in the supplied HFM_Trading_Software.zip.

FEATURES INCLUDED
- Overview / manual trade workflow
- ICT scanner using pasted completed OHLC candles
- Simplified mobile port of core concepts: swing points, liquidity sweeps, three-candle FVGs, premium/discount, AMD range sweep candidates, entry/SL/TP candidate display
- Risk and lot-size calculator
- Local trading journal with CSV export
- Market news search shortcuts
- Local settings and data export
- PWA manifest and service worker for install/offline caching

IMPORTANT DIFFERENCES FROM THE WINDOWS ORIGINAL
This Android-only edition does NOT connect to MetaTrader 5 or HFM directly. It cannot:
- read live quotes, account balance/equity, margin, open positions or trade history;
- download MT5 candles automatically;
- calculate broker-specific profit/volume using MT5 order_calc_profit;
- send, modify or close broker orders;
- run background MT5 scans or reliable background alerts.
Use HFM's official MT5 Android app separately to verify current market data and manually execute trades.
Never enter your HFM password into this companion.
The mobile ICT implementation is a simplified port, not identical to every detail of the original Python engine. It uses only candle rows pasted by the user. No data means no signal.

FREE HOSTING / INSTALL ON ANDROID
A PWA must be served from HTTPS (or localhost) to install and use its service worker. Opening index.html directly from the phone's file manager may show the page, but installation/offline service worker features will not work reliably.

Free publishing route using GitHub Pages:
1. Create/sign in to a GitHub account.
2. Create a new public repository, e.g. hfm-smart-trader.
3. Upload all files and folders in this package (index.html, manifest.webmanifest, sw.js, icons/).
4. In repository Settings > Pages, set deployment source to Deploy from a branch; select main and /(root); Save.
5. Wait for GitHub Pages to publish. The HTTPS address will be shown in Settings > Pages.
6. Open that HTTPS address in Chrome on Android.
7. Chrome menu ⋮ > Install app (or Add to Home screen) > Install.
8. Open HFM Smart Trader from your app list.

LOCAL DATA
Journal entries are stored in the browser localStorage on that phone/browser. Export CSV/JSON regularly. Clearing browser data may erase records. This package does not upload journal data anywhere.

RISK SAFETY
The lot calculator's value-per-price-unit input must be set correctly for the specific symbol and account contract. The default is illustrative only and must not be assumed correct. The result excludes costs and execution effects. Verify contract size, tick value, lot minimum/step/maximum and margin in HFM MT5. Start on DEMO. This tool is educational, not financial advice, and does not promise profitable results.

FILES
index.html                 Main mobile app
manifest.webmanifest       PWA metadata
sw.js                      Offline cache service worker
icons/                     App icons
