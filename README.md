# PumpDeck

Eine alternative App für die Seilzug-Fitnesspumpen **Rayofi Go Tone** / **TT BOT**. Sie verbindet sich direkt per Bluetooth mit den Pumpen: kein Konto, keine Cloud, nichts zu installieren.

## 👉 App öffnen: **https://chrgri.github.io/Pumpdeck/**

Einfach den Link im Handy-Browser öffnen, fertig. Es muss nichts heruntergeladen oder eingerichtet werden.

**Voraussetzungen**
- **Android:** Chrome
- **iPhone:** die kostenlose App **Bluefy** (Safari kann kein Web-Bluetooth)
- Bluetooth an; Chrome braucht die Berechtigung „Geräte in der Nähe“, auf älteren Android-Versionen den Standort

---

## Kurzes Tutorial

### 1. Pumpen verbinden (einmalig)
1. Beide Pumpen einschalten.
2. Auf **Connect pump** tippen und im Auswahldialog die **linke** Pumpe wählen (Name z. B. `Realtek-F8E4`).
3. Auf **Add second pump** tippen und die **rechte** Pumpe wählen.

Die Karten zeigen jetzt **Left** (orange) und **Right** (grün) mit Akku, Temperatur und Firmware. Ab jetzt merkt sich die App beide Pumpen. Beim nächsten Öffnen verbinden sie sich automatisch, sobald sie eingeschaltet sind.

> Kommt der Hinweis, dass der Browser nicht automatisch verbinden kann: In Chrome `chrome://flags` öffnen, **Web Bluetooth new permissions backend** auf *Enabled* stellen und Chrome neu starten.

### 2. Als App auf den Startbildschirm (empfohlen)
Chrome-Menü **⋮** → **App installieren** bzw. **Zum Startbildschirm hinzufügen**. PumpDeck startet dann im Vollbild mit eigenem Icon. Updates kommen automatisch.

### 3. Gewicht und Modus einstellen
- **Resistance:** mit **−/+** oder dem Schieberegler. Mit **Sync both pumps** (standardmäßig an) bekommen beide Pumpen immer dasselbe Gewicht. Das gilt auch, wenn du an einer Pumpe selbst die Tasten drückst.
- **Mode:**

  | Modus | Wirkung |
  |---|---|
  | Standard | konstanter Widerstand |
  | Eccentric | Zusatzlast beim Zurücklassen (0–50 %) |
  | Concentric | Zusatzlast beim Ziehen (0–50 %) |
  | Rowing | geschwindigkeitsabhängig, Stufe 1–10 |
  | Chain | Last steigt mit dem Seilauszug, wie Ketten (0–50 %) |
  | Power saving | Energiesparmodus |

### 4. Trainieren
1. Unter **Workout** auf **Start** tippen. Der Bildschirm bleibt dann an.
2. Oben siehst du live für links und rechts: **Reps**, **Speed** (+ beim Ziehen, − beim Zurücklassen) und **Rope out** in cm.
3. Die **Live**-Graphen zeigen Geschwindigkeit, Seilauszug und Temperatur. Oben rechts wählst du das Zeitfenster: 10, 30 oder 60 s.
4. Im Balkendiagramm siehst du die Spitzengeschwindigkeit jeder Wiederholung, links und rechts nebeneinander. So erkennst du gut, wann die Kraft nachlässt.
5. **Pause** / **Resume** nach Bedarf, am Ende **Finish & save**. Das Workout landet unter **History** und lässt sich als JSON exportieren.

### 5. Seillänge kalibrieren (optional)
Wenn **Rope out** nicht genau stimmt: **Pump settings** → **Rope calibration**. Seil auf eine gemessene Länge ausziehen, z. B. eine A4-Seite (29,7 cm) oder 1 m mit dem Maßband, dort halten, die echte Länge eintippen und auf **Calibrate** tippen.

### Ohne Pumpe ausprobieren
**Demo (2 pumps)** startet zwei simulierte Pumpen mit unterschiedlicher Bewegung.

---

## Weitere Funktionen

Unter **Pump settings**:
- kg/lb umschalten
- Rep-Zähler zurücksetzen
- Seil-Startpunkt setzen
- Pumpeninfo auslesen
- Pumpen ausschalten

Unter **Protocol log**: alle Bluetooth-Pakete und ein Feld für eigene Befehle, für Tüftler.

## Hinweise
- Die App läuft nur, solange die Seite geöffnet ist. Im Hintergrund oder bei gesperrtem Bildschirm trennt Android die Verbindung.
- Der Workout-Verlauf wird nur auf deinem Handy gespeichert.
- Inoffizielles Projekt, nicht mit dem Hersteller verbunden. Nutzung auf eigene Verantwortung.

## Für Entwickler
Die ganze App ist eine Datei: [`index.html`](index.html). Das entschlüsselte Bluetooth-Protokoll steht in [PROTOCOL.md](PROTOCOL.md).
