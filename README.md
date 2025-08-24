# RAW11-Gamepad

Ultra-low latency gamepad poller with persistent WebSocket bridge. Designed for iOS Safari, desktop browsers, and integration with bookmarklets or shortcuts.

---

## 🚀 Features

- Polls gamepad axes & buttons at ~1ms intervals.
- Quantized axes with configurable deadzone (`AXIS_EPSILON`) and scale (`AXIS_SCALE`).
- Persistent WebSocket connection to `ws://localhost:8080`.
- Auto-reconnect and queueing for messages during disconnects.
- Keepalive pings for long-running sessions.
- Minimal, self-contained, and bookmarklet-friendly.
- Works on iOS Safari with one-tap launch via bookmarklet or shortcut.

---

## ⚙️ Configuration

You can tweak the following constants in `raw11.js`:

| Parameter       | Default      | Description |
|-----------------|-------------|------------|
| `POLL_MS`       | 1           | Polling interval in milliseconds (~1ms) |
| `AXIS_EPSILON`  | 0.00001     | Deadzone threshold for axes |
| `AXIS_SCALE`    | 1000        | Scale for quantizing axis values |
| `KEEPALIVE_MS`  | 15000       | Interval for sending keepalive pings |
| `WS_URL`        | ws://localhost:8080 | WebSocket server endpoint |

---

## 📥 Usage

### 1. Web Page
1. Open `index.html` in your browser.  
2. The script will automatically start polling if a gamepad is connected.  

### 2. Bookmarklet
1. Minify `raw11.js` and wrap in a single-line bookmarklet:
```js
javascript:(function(){ /* paste raw11.js here */ })();
