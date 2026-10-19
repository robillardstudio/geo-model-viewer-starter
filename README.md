# Found on the Oval — starter

DESIGN 4106 · Training 2. Assignment: [ASSIGNMENT.md](ASSIGNMENT.md)

A .glb stays locked until your phone's GPS says you are at the spot. Then it opens in [model-viewer](https://modelviewer.dev), with a **View in AR** button. One HTML file, no install.

## Run it (no install, in GitHub Codespaces)

1. On your repo page: **Code → Codespaces → Create codespace on main**
2. In the Codespace terminal:
   ```bash
   python3 -m http.server 8000
   ```
3. Open the **Ports** tab → port 8000 → globe icon. That's your HTTPS address.

**Desktop test:** add `?fake` to the address and click Start. It simulates walking in from 60 m.

**Phone test:** in Ports, right-click port 8000 → **Port Visibility → Public**, then open the same address on your phone and tap Start. Allow location.

Stop the Codespace when done (Codespaces menu → Stop) to save your free hours.

## Edit

| File | What |
|---|---|
| `index.html` → `TARGET` | your spot's latitude/longitude |
| `index.html` → `RADIUS` | how close (metres) before it opens |
| `models/object.glb` | your model (replace the placeholder, keep the name) |

**Finding your coordinates:** stand on your spot with the page open; it prints your live coordinates. Wait for ±10 m or better, then paste them into `TARGET`.

## How it works

```js
navigator.geolocation.watchPosition(onPosition);   // GPS listener
// in onPosition: if distance to TARGET < RADIUS → show <model-viewer>
```

## My project

- **Coordinates:**
- **Intent (one line):**
- **Video:**
