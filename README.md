# 🐨 KoalaCast

Browser-based audio streaming. Run on a PC, scan a QR code on your phone, hear the audio. No app install required on the receiver — just a browser.

---

## Getting KoalaCast.exe

This repo auto-builds `KoalaCast.exe` via GitHub Actions on every push.

1. Go to the **Actions** tab in this repo
2. Click the latest **Build KoalaCast.exe** run
3. Scroll to **Artifacts** at the bottom
4. Download **KoalaCast** — extract the zip, run `KoalaCast.exe`

That's it. No Node.js needed on your PC.

---

## How It Works

1. Double-click `KoalaCast.exe`
2. A browser opens at `http://localhost:3000/stream`
3. First launch asks how you want the QR code displayed (persistent or occasional)
4. Choose your audio source:
   - 🖥 **Cast mode** — captures system or browser tab audio
   - 📁 **File mode** — play any audio or video file and stream its audio
5. A QR code appears in the bottom-right corner
6. Someone scans it on their phone, browser opens, tap play, audio streams live

---

## Technical Notes

- Uses **WebRTC** for peer-to-peer audio streaming
- Uses **localtunnel** to provide an HTTPS URL (required for getDisplayMedia)
- The localtunnel IP gate is bypassed automatically via response header
- Multiple receivers can listen simultaneously
- QR mode preference is saved to %APPDATA%\koalacast-config.json
- Built as a self-contained exe using **pkg** (Node.js bundled inside)
