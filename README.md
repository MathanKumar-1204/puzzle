# PuzzleCam — Gesture Capture

Gesture-controlled photobooth app running entirely in the browser. Zero installation, no backend, no dependencies to install.

---

## **DESCRIPTION**

PuzzleCam captures a photo using your hands as a frame, converts it into a 3x3 puzzle with a black & white photobooth effect, and lets you assemble it using pinch gestures. Once completed, it is saved to a downloadable photo strip.

---

## **SYSTEM REQUIREMENTS**

- **Browser:** Chrome or Edge (recommended), Firefox
- **Hardware:** Webcam
- **Internet connection:** Required to load the MediaPipe model (~10MB, first time only)
- **Local server:** Required to run the app (cannot be opened directly as a file)

---

## **INSTALLATION AND SETUP**

### 1. Clone the repository

```bash
git clone https://github.com/mishu006/Puzzle.git
cd Puzzle
```

### 2. Start a local server

The app uses ES modules and camera access, so it needs to run over HTTP.

Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension in VS Code and click **Go Live**.

### 3. Open in browser

```
http://localhost:5500
```

Allow camera access when prompted by your browser.

---

## **PROJECT STRUCTURE**

```
Puzzle/
├── index.html        # App entry point
├── app.js            # Complete logic (tracking, puzzle, gallery)
├── css/
│   └── styles.css    # Styles and layout
└── .gitignore
```

---

## **CONTROL GESTURES**

| Gesture | Action |
|---|---|
| Both hands pinching | Freeze area and start countdown |
| One hand pinching a piece | Drag puzzle piece |
| Closed fist (hold) | Save completed puzzle / Reset board |

---

## **APPLICATION FLOW**

1. Show both hands to the camera and pinch to define the capture box
2. Hold the pinch during the countdown — the photo will be taken automatically
3. The photo is split into a 3x3 puzzle with a B&W photobooth filter
4. Rearrange the pieces using pinch gestures
5. When complete, close your fist to save to the strip with a shattering animation
6. Download the full strip once you have saved 3 puzzles

---

## **TECH STACK**

- **[MediaPipe Tasks Vision](https://developers.google.com/mediapipe)** `v0.10.14` — hand landmark detection
- **Canvas 2D API** — rendering, puzzle pieces, photobooth effect
- **JavaScript (ES Modules)** — framework-free
- **CSS Custom Properties** — theming and layout

All external dependencies are loaded via CDN. No additional installation required.

---

## **TROUBLESHOOTING GUIDE**

### **Camera does not turn on**

Ensure no other app (Teams, Zoom, Discord, etc.) is using the camera in the background.

### **App fails to load the model**

Check your internet connection. The MediaPipe model (~10MB) is fetched from `storage.googleapis.com` and the runtime from `cdn.jsdelivr.net`. If either domain is blocked on your network, the app cannot start.

### **App shows a black screen**

Make sure you are opening the app from a local web server (HTTP), not directly as a file from your file explorer.

### **Pinch gesture is not detected**

Ensure good lighting and that both hands are visible to the camera. Bring your index finger and thumb closer together until the status indicator activates.

---

## **BROWSER COMPATIBILITY**

| Browser | Support |
|---|---|
| Chrome / Edge | Recommended |
| Firefox | Supported |
| Safari | Limited (may require additional permissions) |
| Mobile | Limited (desktop recommended) |

---

## **LICENSE**

MIT — free to use, modify, and share.

