# PumpDeck

A replacement control app for TT BOT / Rayofi Go Tone smart fitness pumps. It is a single HTML page that talks to the pump directly over Web Bluetooth, with no account and no cloud.

## Use

1. Serve `index.html` over HTTPS (GitHub Pages, Netlify, etc.).
2. Open it in Chrome on Android, or in the Bluefy browser on iPhone, with Bluetooth and location switched on.
3. Switch the pump on and tap **Connect pump**. Connect a second pump for two-handed training.

**Demo pump** simulates a pump, so you can try the app without hardware.

## Features

- Resistance control, limited to the range the pump reports (kg or lb)
- All 6 modes: standard, eccentric, concentric, rowing, iron chain, power saving
- Live reps, speed and rope position, for one or two pumps
- Live speed, rope-length and temperature graphs with a 10, 30 or 60 s window
- Two-pump sync: same resistance, unit, mode and mode settings on both, including changes made with the pump's own buttons
- Remembers your pumps and reconnects to them automatically (Chrome on Android)
- Installable: "Add to Home screen" opens it full screen, also offline
- Workout timer, per-rep speed chart, and history stored on the phone (exportable as JSON)
- Protocol log and a raw command sender for debugging

See [PROTOCOL.md](PROTOCOL.md) for the decoded Bluetooth protocol.

## Automatic connection (Android)

1. Open the app in Chrome and connect each pump once with **Connect pump**: left first, then right.
2. From then on, the app connects to both pumps by itself whenever it is opened and the pumps are on. It also reconnects if a pump drops out mid-workout.
3. If the app says your browser can't reconnect by itself, open `chrome://flags`, enable **Web Bluetooth new permissions backend**, and restart Chrome.
4. Chrome menu → **Add to Home screen** / **Install app** puts PumpDeck on your home screen as a full-screen app.
