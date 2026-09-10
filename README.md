# QR Share – v1.0.0

> A modern, lightweight **peer-to-peer file transfer app** built with **WebRTC** and **PeerJS**.  
> Scan a QR code, open a direct connection, and move files straight between two browsers — no accounts, no uploads, no server in between.

<p align="center">
  <img src="https://img.shields.io/badge/WebRTC-P2P-blue" />
  <img src="https://img.shields.io/badge/PeerJS-Signaling-orange?logo=peerjs" />
  <img src="https://img.shields.io/badge/HTML5-Frontend-red?logo=html5" />
  <img src="https://img.shields.io/badge/JavaScript-Vanilla-yellow?logo=javascript" />
  <img src="https://img.shields.io/badge/License-MIT-lightgrey" />
</p>

---

## Features

| Feature | Description |
|---------|-------------|
| 📱 **QR Code Handshake** | Start a room and instantly get a QR code — the other device connects with one scan. |
| 🔗 **Direct Link Sharing** | Prefer a link? Copy the invite URL with one tap, or copy the QR code as an image. |
| 📂 **Drag & Drop Upload** | Drop files into the room — they stream straight to the connected device. |
| 📶 **Real P2P Transfer** | Data flows over WebRTC DataChannels — nothing is uploaded, cached, or logged. |
| 🖥️ **Live Progress** | Chunked streaming (256 KB chunks) with buffer-aware sending and live progress bars on both ends. |
| 📷 **Built-in Scanner** | Camera-powered QR scanning via html5-qrcode — works right on mobile. |
| 🔗 **Manual Connect** | No camera access? Paste the invite link manually to join. |
| 🔒 **Zero Accounts** | No registration, no server-side storage, no files kept anywhere. |
| 🎨 **Modern UI** | Clean responsive design with a live progress guide and subtle micro-animations. |

---

## Getting Started

### Prerequisites
- A modern browser with **WebRTC** support (Chrome, Firefox, Edge, Safari)
- **HTTPS** (or `localhost`) — required for camera access and WebRTC
- Internet connection for the PeerJS signaling server (used only to establish the connection)

### Installation
```bash
# 1. Clone the repository
git clone https://github.com/username/qr-share.git
cd qr-share

# 2. (Optional) Add a custom favicon
# Place your ico.ico inside an `images/` folder for the tab icon

# 3. Run the app
# Option A — just open index.html in your browser
# Option B — serve it locally (recommended for camera access)
python -m http.server 8000
# then visit http://localhost:8000
```

---

## Usage

### 1️⃣ Start Sending
Click **Start sending** — a QR code and invite link appear instantly.

### 2️⃣ Share the Code
Let the other device scan the QR code with its camera, or paste the copied link directly.

### 3️⃣ Wait for the Handshake
The moment both devices meet, the status turns green — no delay, no approval step.

### 4️⃣ Drop Your Files
Drag files into the room and they stream straight to the other device, chunk by chunk, with live progress.

### Additional controls
- **Copy link** — copies the invite URL to the clipboard.
- **Copy QR image** — copies the QR code as a PNG (auto-downloads if unsupported).
- **End session** — destroys the peer connection and clears everything instantly.

> **Tip:** Both devices only need the same page — the sender opens a room, the receiver scans or pastes the link.

---

## Project Structure

```
qr-share/
├── index.html           # The whole app (UI + WebRTC logic, single file)
├── images/
│   └── ico.ico          # Favicon (optional)
└── README.md
```

---

## Tech Stack

- [`PeerJS`](https://peerjs.com/) — WebRTC wrapper with free cloud signaling
- [`WebRTC DataChannels`](https://webrtc.org/) — direct peer-to-peer file streaming
- [`html5-qrcode`](https://github.com/mebjas/html5-qrcode) — camera-based QR scanning
- [`qrcodejs`](https://github.com/davidshimjs/qrcodejs) — client-side QR code generation
- [`STUN/TURN`](https://webrtc.org/getting-started/turn-server) — NAT traversal (Google STUN + public TURN fallback)

---

## Author

Developed by **[Tim](https://github.com/timignatenko)**

---

## License

This project is open-source under the **MIT License**. Feel free to use, modify, and distribute.

---

<p align="center"><b>⭐ Star this repo if you found it useful!</b></p>
