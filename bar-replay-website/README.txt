BAR REPLAY - WEBSITE (works on phone and computer)

All files sit in one folder with no subfolders, so they're easy to upload from a phone.

PUT IT ONLINE FREE WITH GITHUB PAGES (can be done from a phone browser)
1. Unzip this file (Android: Files by Google -> tap the zip -> Extract. iPhone: Files app -> tap the zip).
2. Go to github.com and create a free account.
3. Tap "+" -> New repository. Name: bar-replay. Public. Create repository.
4. Tap "uploading an existing file", select ALL files from the unzipped folder, then "Commit changes".
5. Repository Settings -> Pages -> Source: "Deploy from a branch" -> Branch: main, folder: / (root) -> Save.
6. After about a minute your site is live at:  https://YOUR-USERNAME.github.io/bar-replay/
It works right away with "Continue without sign-in" until Google sign-in is set up.

GOOGLE SIGN-IN (one time)
1. console.cloud.google.com -> APIs & Services -> OAuth consent screen -> External.
   Scopes: email, profile, openid. Add testers' Gmail addresses, or "Publish app" so anyone can sign in.
2. Credentials -> Create credentials -> OAuth client ID -> Web application.
   (You can reuse the one made for the Chrome extension.)
   Authorised JavaScript origins -> add:  https://YOUR-USERNAME.github.io
3. Copy the Client ID. On GitHub open config.js -> pencil (edit) icon -> paste it between the quotes -> Commit.
4. Wait a minute and reload the site.

INSTALL ON YOUR PHONE
Android Chrome: menu -> Add to Home screen.  iPhone Safari: Share -> Add to Home Screen.

INDICATORS (same as your TradingView script "UT Bot x2 + 1H Bias Dashboard")
Open Settings (the sliders icon). Everything starts with the same values as your Pine script:
- UT Bot #1: key 3.0, ATR period 10. Green Buy / red Sell arrows with a green stop line.
- UT Bot #2: key 3.0, ATR period 10. Lime / maroon dots with an orange stop line.
- 1H Bias Dashboard: key 3.0, ATR 10, timeframe 1H. A green BULLISH / red BEARISH box on the chart
  (position and background tint are options). Bullish = 1H price is above its own UT Bot trailing stop.
  "Include the forming candle" is on, so the box moves live like your TradingView chart; switch it off
  to change only when a 1H candle closes.
- Because both bots start with the same values, their signals land on the same candles until you change one.
- The button "Reset UT Bots and bias to my TradingView values" puts everything back.
- Signals appear only after a candle closes (no repainting). The bias needs about 10 candles of its timeframe to warm up.

DATA
- Default: Binance PAXG/USDT (gold-backed token), live, no key needed.
- Real XAU/USD: tap Data -> "XAU/USD, forex and stocks" and paste your free Twelve Data API key.
  Each user uses their own key; it stays in their own browser.
- CSV exports from TradingView or MT5 also work.

Chart engine: TradingView Lightweight Charts (Apache 2.0, see LICENSE-lightweight-charts.txt).

IF THE SITE DOES NOT OPEN
- Page not found (404): index.html must be in the MAIN folder of the repository, not inside a folder, and you must upload the
  files from inside the unzipped folder, not the .zip itself. Open the repository: you should see index.html in the first list.
- Settings -> Pages must say "Your site is live". The first time can take about 5 minutes. The repository must be Public.
- The page opens but says some files did not load: the message names the missing file. Upload it to the same place as index.html.
- Google error "origin_mismatch": the Authorised JavaScript origin must be exactly https://YOUR-USERNAME.github.io (no path, no slash at the end).
- Google sign-in will not load: tap "Continue without sign-in".
