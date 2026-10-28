# PumpDeck

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by-nc-sa/4.0/)
[![Support on Ko-fi](https://img.shields.io/badge/Ko--fi-Donate-ff5e5b.svg?logo=kofi&logoColor=white)](https://ko-fi.com/captainchris88)
[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-Donate-yellow.svg?logo=buy-me-a-coffee)](https://buymeacoffee.com/captainchris)

An alternative app for the **Rayofi Go Tone** / **TT BOT** smart cable-pull fitness pumps. It talks to the pumps directly over Bluetooth. There's no account, no cloud and nothing to install.

## 👉 Open the app: **https://chrgri.github.io/Pumpdeck/**

Open the link on your phone and you're ready. Nothing to download or set up.

**Requirements**
- **Android:** Chrome
- **iPhone:** the free **Bluefy** browser (Safari doesn't support Web Bluetooth)
- Bluetooth on. Chrome needs the "Nearby devices" permission (location on older Android versions).

---

## Why PumpDeck instead of the TT BOT app?

- **No login.** No account, no e-mail verification code, no privacy policy to accept. Open the page and connect.
- **Runs locally on your phone.** PumpDeck is a web app: the code runs entirely in your browser and talks to the pumps directly over Bluetooth. Nothing is sent to a server, and your workout history stays on your device. After the first visit it also opens offline.
- **Nothing to install.** One link, nothing from an app store. Optionally add it to your home screen. Updates arrive automatically.
- **More training insight.** Live graphs, per-rep speed bars for left and right, signed speed (pull vs. return) and temperature monitoring.
- **Better two-pump handling.** Left/right readouts side by side, and sync of resistance, unit, mode *and* mode settings. The official app only syncs resistance and unit.
- **Open and transparent.** The source and the decoded Bluetooth protocol are public. There's a built-in protocol log for tinkerers.

| | TT BOT app | PumpDeck |
|---|---|---|
| Account / login required | yes | **no** |
| Data sent to a cloud server | yes (workout records) | **no**, stays on the phone |
| Install from app store | yes | **no**, open a link (optional home-screen install) |
| Resistance, all 6 modes, kg/lb | ✓ | ✓ |
| Two pumps at once | ✓ | ✓ |
| Sync of both pumps | resistance + unit | **resistance, unit, mode and mode settings** |
| Auto-reconnect to known pumps | ✓ | ✓ (Chrome on Android) |
| Live graphs (speed, rope, temperature), 10/30/60 s | – | **✓** |
| Signed speed (pull + / return −) | – | **✓** |
| Per-rep peak-speed chart, left/right | – | **✓** |
| Rope-length calibration | – | **✓** |
| Workout history | in the cloud | on the phone, JSON export |
| Protocol log / raw commands | – | **✓** |
| Video courses and training plans | ✓ | – |
| Firmware updates | ✓ | – (use the official app) |

---

## Quick tutorial

### 1. Connect your pumps (once)
1. Switch both pumps on.
2. Tap **Connect pump** and pick the **left** pump in the dialog (named e.g. `Realtek-F8E4`).
3. Tap **Add second pump** and pick the **right** pump.

The cards now show **Left** (orange) and **Right** (green) with battery, temperature and firmware. The app remembers both pumps. Next time, they connect automatically as soon as they're switched on.

> If the app says your browser can't reconnect by itself: open `chrome://flags` in Chrome, set **Web Bluetooth new permissions backend** to *Enabled*, and restart Chrome.

### 2. Add it to your home screen (recommended)
Chrome menu **⋮** → **Install app** / **Add to Home screen**. PumpDeck then opens full screen with its own icon. Updates arrive automatically.

### 3. Set resistance and mode
- **Resistance:** use **−/+** or the slider. With **Sync both pumps** on (the default), both pumps always have the same load. That includes changes made with a pump's own buttons.
- **Mode:**

  | Mode | What it does |
  |---|---|
  | Standard | constant resistance |
  | Eccentric | extra load while the rope goes back in (0–50 %) |
  | Concentric | extra load while you pull (0–50 %) |
  | Rowing | speed-based, level 1–10 |
  | Chain | load rises as you pull further, like lifting chains (0–50 %) |
  | Power saving | eco mode |

### 4. Train
1. Under **Workout**, tap **Start**. The screen stays on while you train.
2. The top cards show **Reps**, **Speed** and **Rope out** (cm) live for left and right. Speed is + while pulling and − while the rope goes back in.
3. The **Live** graphs plot speed, rope length and temperature. Pick a 10, 30 or 60 s window at the top right.
4. The bar chart shows each rep's peak speed, left and right side by side. That makes it easy to spot when you're slowing down.
5. Use **Pause** / **Resume** as needed, then **Finish & save**. The workout goes to **History** and can be exported as JSON.

### 5. Calibrate rope length (optional)
If **Rope out** is off, go to **Pump settings** → **Rope calibration**:
1. Pull the rope out to a length you've measured, e.g. an A4 sheet's long side (29.7 cm) or 1 m with a tape measure.
2. Hold it there and enter the real length.
3. Tap **Calibrate**.

### Try it without a pump
**Demo (2 pumps)** starts two simulated pumps that move differently.

---

## More features

Under **Pump settings**:
- Switch kg/lb
- Reset the rep counter
- Set the rope start point
- Read pump info
- Switch the pumps off

Under **Protocol log**: every Bluetooth packet, plus a field for sending your own commands.

## Notes
- The app only works while the page is open. In the background or with the screen locked, Android drops the connection.
- Workout history is stored only on your phone.
- This is an unofficial project, not affiliated with the manufacturer. Use at your own risk.

## For developers
The whole app is one file: [`index.html`](index.html). The decoded Bluetooth protocol is in [PROTOCOL.md](PROTOCOL.md).

---

## ☕ Support

If PumpDeck makes your training better, consider supporting further open-source development:

[![Support on Ko-fi](https://img.shields.io/badge/Ko--fi-Donate-ff5e5b.svg?logo=kofi&logoColor=white&style=for-the-badge)](https://ko-fi.com/captainchris88)
[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-Donate-yellow.svg?logo=buy-me-a-coffee&style=for-the-badge)](https://buymeacoffee.com/captainchris)

---

## 📄 License

This work is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0)][cc-by-nc-sa].

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
