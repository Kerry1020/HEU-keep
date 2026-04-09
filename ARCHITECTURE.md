# HEU-keep Architecture

## 1. System Goal

HEU-keep is a browser-based generator for Keep-style running summary cards. The system is designed to:
- let users edit workout data visually
- generate or draw realistic running tracks
- persist user preferences locally
- export a high-resolution final image

## 2. High-Level Architecture

```text
+-------------------------+
| Frontend UI             |
| - form inputs           |
| - preview rendering     |
| - theme / layout        |
| - export controls       |
+-----------+-------------+
            |
            v
+-------------------------+
| Frontend Data / Render  |
| - render.js             |
| - init.js               |
| - IndexedDB state       |
| - local track helpers   |
+-----------+-------------+
            |
            +-------------------+
            |                   |
            v                   v
+---------------------+   +----------------------+
| Canvas Drawing      |   | Backend Track API    |
| - manual track      |   | - Flask endpoint     |
| - personalization   |   | - NumPy generation   |
+---------------------+   +----------------------+
            |
            v
+-------------------------+
| Export Pipeline         |
| - off-screen clone      |
| - canvas copy repair    |
| - html2canvas render    |
+-------------------------+
```

## 3. Frontend Modules

### 3.1 Entry Pages
- `index.html` — standard entry page
- `liquid.html` — alternate liquid / glassmorphism theme

### 3.2 Styling Layer
- `css/base.css` — reset and global foundation
- `css/styles.css` — standard theme styling
- `css/liquid.css` — liquid / glass-like visual treatment

### 3.3 Rendering Layer
- `js/render.js`
  - binds form data to the Keep-style preview card
  - computes derived fields like pace, duration, calories

### 3.4 Initialization / State
- `js/init.js`
- `js/onload.js`
- `js/indexedDB.js`
  - persist local assets and user preferences
  - restore previous state after refresh

### 3.5 Track Layer
- `js/draw_personalization.js`
  - manual drawing logic
- `js/drawMine.js`
  - trigger random/generated path logic
- `js/localTrackGen.js`
  - local track generation support

### 3.6 Export Layer
- `js/download_img.js`
- inline export override in HTML
  - clones preview DOM off-screen
  - copies canvas state manually
  - removes problematic transform/shadow effects
  - calls `html2canvas` for final output

## 4. Backend Module

### `Json2Png.py`
A Flask-based backend that exposes `/generate-track`.

Responsibilities:
- generate multiple lap-like ellipse tracks
- simulate path randomness and GPS-like drift
- add extra entry/exit line behavior
- output structured coordinate points for frontend use

Main backend techniques:
- NumPy array operations
- segment-based ellipse construction
- random perturbation
- rotation matrix transformation

## 5. Collaboration Split in Architecture Terms

### Kerry1020 side
Focuses mainly on:
- frontend usability
- visual polish
- mobile adaptation
- interaction testing
- export-flow validation

### Lingion side
Focuses mainly on:
- backend API and generation logic
- integration of generated data into frontend flows
- deployment and project-level structure
- engineering packaging and delivery

## 6. Engineering Risks / Current Weak Points

1. Frontend logic is still script-heavy and can be further modularized.
2. Backend currently ships as a single-file Flask app and could be turned into a cleaner API service.
3. There is no formal test suite yet for export fidelity / render correctness.
4. The project would benefit from a clearer build/deploy story for online demo hosting.

## 7. Suggested Next-Step Refactors

- split rendering, state, and export into clearer modules
- define a formal JSON schema for generated track output
- add sample presets and regression screenshots
- add a lightweight deployment story for demo hosting
