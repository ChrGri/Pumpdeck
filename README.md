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
- Workout timer, per-rep speed chart, and history stored on the phone (exportable as JSON)
- Protocol log and a raw command sender for debugging

See [PROTOCOL.md](PROTOCOL.md) for the decoded Bluetooth protocol.
