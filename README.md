# Perfect Circle 100% — Chrome Extension

A Chrome extension that automatically draws a perfect circle on [neal.fun/perfect-circle](https://neal.fun/perfect-circle) and patches the score to always show **99.9%**.

---

## How It Works

The extension has two components working together:

**1. Score Patcher (`inject.js`)**
Runs before the page loads and patches `Math.round` and `Number.prototype.toFixed` — the exact functions the game uses to calculate and display your score. Any result between 90–100 gets rounded up to 100.

**2. Circle Drawer (`popup.js`)**
When you click the button, it injects a script directly into the page's JavaScript context. It fires both `PointerEvent` and `MouseEvent` in sync (because the game listens to both), and uses `requestAnimationFrame` for smooth, natural-looking timing — exactly how a real mouse would move.

---

## Installation

1. Download and extract the ZIP file
2. Open Chrome and go to `chrome://extensions`
3. Enable **Developer mode** (toggle in the top right)
4. Click **Load unpacked** and select the extracted folder
5. The extension is now installed

---

## Usage

1. Go to [neal.fun/perfect-circle](https://neal.fun/perfect-circle)
2. **Reload the page** after installing (important — the score patcher runs on page load)
3. Click the extension icon in Chrome
4. Press **▶ Draw circle**
5. Click the white dot in the center of the game
6. Watch it draw a perfect circle and score 100%

---

## Files

| File | Description |
|------|-------------|
| `manifest.json` | Chrome extension configuration |
| `inject.js` | Score patcher — runs before page loads |
| `popup.html` | Extension popup UI |
| `popup.js` | Circle drawing logic |
| `icon.png` | Extension icon |

---

## Credits

Built by **Claude** (claude.ai) — Anthropic's AI assistant.  

---

## Notes

- Works on Chrome and any Chromium-based browser (Edge, Brave, etc.)
- The score patch is active for 30 seconds after page load, then disables itself
- Does not modify any game files or make any network requests
- For educational and entertainment purposes only
