# 🛺 Rickshaw Run

A 3D auto-rickshaw driving game set on the streets of Mumbai.

![Three.js](https://img.shields.io/badge/Three.js-r128-black?logo=three.js&logoColor=white)
![No build](https://img.shields.io/badge/no%20build%20step-just%20open%20it-brightgreen)

Just open `rickshaw-run.html` in your browser and go. It pulls Three.js from a CDN so you need internet the first time, but that's it.

## How to play
Arrow keys or WASD to drive. Pick up passengers (yellow marker), drop them off (green marker), try not to crash, stop at red lights. Chain rides together for combo bonuses.

```
↑ / W     — gas
↓ / S     — brake
← → / A D — steer
P / Esc   — pause
```

The streets get busier as you level up, so it does get harder.

## What's in it
- 3D world built with Three.js — road tiles, buildings, street lamps, zebra crossings
- Traffic signals that actually work (and a penalty if you blow through a red)
- AI vehicles in both directions that brake for signals and keep following distance
- Pedestrians wandering around
- Passenger missions with randomised names, destinations, and fares
- Combo multiplier for chaining rides
- Minimap, canvas speedometer, lives system
- Cinematic end screen with confetti

## Running it locally

```bash
git clone https://github.com/YOUR_USERNAME/rickshaw-run.git
cd rickshaw-run
open rickshaw-run.html
```

## How the code is structured
It's one file so I'll just describe what's in the `<script>` block:
- `init3D()` — sets up the Three.js scene, camera, lights
- `buildRoad()` / `buildBuildings()` — procedural world generation
- `buildSignal()` + `tickSig()` — traffic light logic
- `buildRickshaw()` — the rickshaw mesh, assembled from boxes and cylinders
- `spawnT()` / `spawnO()` / `spawnP()` — traffic and pedestrian spawning
- `spawnMission()` / `checkMission()` — passenger pickup/dropoff system
- `mainLoop()` — the main game loop (input, physics, collisions, render)
- `drawSpeedo()` / `drawMinimap()` — canvas-drawn HUD elements

## Things we want to add eventually
- [ ] Touch controls for mobile
- [ ] Sound effects
- [ ] Save high score to localStorage
- [ ] Night mode
- [ ] More cities
