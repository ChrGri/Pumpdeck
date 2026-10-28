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
- **Velocity-based training.** Peak speed, mean speed, estimated power and velocity loss for every rep. Optionally end the set at a chosen velocity loss.
- **Sets and rest timer.** Plan sets × reps, with an automatic rest countdown and beeps before the next set.
- **Auto drop set.** When your reps get slower or shorter, the next rep is automatically lighter.
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
| Velocity-based training: peak/mean speed, power, velocity loss per rep | – | **✓** |
| Sets × reps with rest timer, stop at velocity loss | – | **✓** |
| Auto drop set (lighter when reps slow down or get shorter) | – | **✓** |
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
1. Under **Sets & rest**, set your plan:
   - **Sets** and **Reps** per set. Reps 0 = open set, which you end yourself.
   - **Rest** in seconds.
   - Optionally **Stop at loss**: the set ends when a rep's mean speed drops that many percent below your best rep in the set. 20–30 % is common for velocity-based training.
2. Tap **Start**. A full-screen **3-2-1** countdown (with beeps) comes before every set. The screen stays on. Each set ends automatically when the reps are done (or at the velocity loss). The rest countdown is pinned to the bottom of the screen, so you see it wherever you've scrolled. Its last 3 seconds become the full-screen 3-2-1, then the next set starts. Use **−15 s / +15 s** to adjust the rest, or **Start next set** to skip it. Tap the 3-2-1 to start right away.
   - Tick **Rest timer as notification** (Chrome asks for permission once). When you switch to another app or lock the screen during a rest, the countdown shows as a notification with **+15 s** and **Start now** buttons, and a loud **Go!** notification announces the next set. Keep PumpDeck open in the background; the app can't run once Android closes it.
3. After every rep, the tiles show for left and right:
   - **Peak** and **Mean** speed while pulling (m/s)
   - estimated **Power** (W)
   - **Loss**: velocity loss versus the best rep of the set
4. The top cards show **Reps** (in the current set), live **Speed** and **Rope out**. Speed is + while pulling, − while the rope goes back in.
5. The bar chart shows the current set rep by rep, left and right side by side. Switch between **Peak speed**, **Mean speed** and **Power**. With "Stop at loss" on, the mean-speed view shows the stop threshold as a dashed line.
6. The **Live** graphs plot speed, rope length and temperature over 10, 30 or 60 s.
7. After the last set the workout is saved automatically. **Finish & save** ends it early. **History** lists your workouts, and you can export it as JSON.

### 5. Auto drop set (optional)
Tick **Auto drop set** before you start.
1. In each set, the first rep at a weight is a settling rep. The next 2 reps set your **reference** peak speed and rope range, per side.
2. When a later rep is slower than **Speed <** (default 75 %) or shorter than **Range <** (default 80 %) of that reference, the load on both pumps drops by **Drop by** (default 20 %). The phone vibrates.
3. A new reference is measured at the lighter weight. This repeats up to **Max drops** times per set (default 3).
4. The next set starts again from that set's original weight.

Drops show up as dashed lines in the rep chart and are saved with the workout.

### 6. Calibrate rope length (optional)
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
