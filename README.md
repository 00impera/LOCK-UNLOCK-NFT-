# 🔒 NFT LOCKED IMAGE GENERATOR

> Generate blurred "locked" preview images for your NFTs in seconds. Upload your artwork, customize the lock overlay, mint on Monad Mainnet for 100 MON, and download the locked.png ready for IPFS + OpenSea metadata.

[![Monad](https://img.shields.io/badge/Network-Monad%20Mainnet-00ff44?style=flat-square&labelColor=020a02)](https://monad.xyz)
[![HTML](https://img.shields.io/badge/Stack-Pure%20HTML%2FJS-00cc33?style=flat-square&labelColor=020a02)](#)
[![License](https://img.shields.io/badge/License-MIT-008822?style=flat-square&labelColor=020a02)](LICENSE)

---

## 🌐 Live Demo

**[→ Open NFT Locked Image Generator](https://nft-rarity.imperamonad.xyz)**

---

## 📸 Preview

<img width="800" height="800" alt="locked" src="https://github.com/user-attachments/assets/8f6f4f65-775e-4d08-905b-7f8b734544a7" />

<img width="800" height="800" alt="download" src="https://github.com/user-attachments/assets/04cff51b-fe82-435f-9703-9f6f6c390eac" />

---

## ✨ Features

- 📤 **Drag & drop** or click to upload your NFT image
- 🎨 **Auto-preview** — original vs locked side-by-side in real-time
- ⚙️ **Customize** — blur, darkness, main text, sub text
- 💾 **Download** — one click to get your `locked.png`
- 🌿 **Mint on Monad** — send 100 MON to register ownership
- 🔥 Flame green/black interface with rising ember particles
- ⚡ Every button vibrates on click
- 📱 Fully responsive — works on mobile

---

## 🚀 HOW TO USE — SUPER SIMPLE

### STEP 1 — Upload Your NFT Image
- Click the upload box **OR** drag your image directly onto it
- Accepts: **JPG · PNG · GIF · WEBP**
- Max size: 10MB

### STEP 2 — Adjust Settings

| Setting | What it does | Default |
|---|---|---|
| **Blur Amount** | Slide to blur more / less | 50px |
| **Darkness** | Make the overlay darker / lighter | 50% |
| **Main Text** | Change the big lock text | `🔒 LOCKED` |
| **Sub Text** | Change the small description | `PURCHASE TO UNLOCK` |

### STEP 3 — See Live Preview
- **Left side** = Your original image
- **Right side** = Locked version — updates automatically as you change settings

### STEP 4 — Download or Mint

| Action | Description |
|---|---|
| 💾 **DOWNLOAD LOCKED.PNG** | Saves `locked-nft.png` to your computer |
| 🌿 **MINT — 100 MON** | Sends 100 MON on Monad Mainnet → auto-downloads after confirmation |

---

## 📋 NEXT STEPS AFTER DOWNLOAD

```
✅  You now have locked.png
📤  Upload to IPFS → Pinata.cloud or NFT.Storage
📝  Copy the IPFS hash (ipfs://Qm...)
🔄  Update your NFT JSON metadata:
        "image": "ipfs://YOUR_LOCKED_HASH"
🚀  Mint on OpenSea with locked preview!
```

**Example metadata JSON:**
```json
{
  "name": "My NFT #001",
  "description": "Purchase to unlock the full artwork.",
  "image": "ipfs://QmYOUR_LOCKED_IMAGE_HASH",
  "animation_url": "ipfs://QmYOUR_FULL_IMAGE_HASH"
}
```

---

## ⚙️ All Functions

| Function | Description |
|---|---|
| `loadImage(file)` | Reads file via FileReader, sets canvas size, draws original + locked |
| `setupCanvases()` | Sets both canvases to `min(width, height, 800)` square |
| `drawOriginal()` | Draws the source image centered and scaled on the left canvas |
| `drawLocked()` | Draws blurred image + darkness + green tint + scanlines + lock icon + text + border glow |
| `downloadLocked()` | `canvas.toBlob()` → creates download link → triggers save as `locked-nft.png` |
| `mintOnChain()` | Connects MetaMask → switches to Monad → sends 100 MON → polls receipt → auto-downloads on success |
| `resetAll()` | Clears canvases, resets all inputs to defaults |

---

## 🌿 Mint Configuration

```javascript
const OWNER     = '0x592B35c8917eD36c39Ef73D0F5e92B0173560b2e'; // receives MON
const CHAIN_HEX = '0x8F';                                        // Monad chain ID 143
const PRICE_WEI = '0x' + BigInt('100000000000000000000').toString(16); // 100 MON
```

**Mint flow:**
1. `eth_requestAccounts` — connect wallet
2. `wallet_switchEthereumChain` — switch to Monad (adds it automatically if missing)
3. `eth_sendTransaction` — sends 100 MON to owner (gas: 21000)
4. Polls `eth_getTransactionReceipt` every 2s (max 3 minutes)
5. On success → shows clickable TX link to Monad explorer → auto-downloads PNG

---

## 🗂 File Structure

```
NFT-CARD-GENERATOR-RARITY/
├── index.html     # Complete app — single file, zero dependencies
└── README.md
```

---

## 📱 Browser Support

| Browser | Upload | Preview | Download | Mint |
|---|---|---|---|---|
| Chrome | ✅ | ✅ | ✅ | ✅ |
| Firefox | ✅ | ✅ | ✅ | ✅ |
| Safari | ✅ | ✅ | ✅ | ✅ |
| Mobile Chrome | ✅ | ✅ | ✅ | ✅ |
| Mobile Safari | ✅ | ✅ | ✅ | ✅ |

---

## 🔗 Related Projects

| Project | URL |
|---|---|
| NFT Card Generator | [nft-rarity.imperamonad.xyz](https://nft-rarity.imperamonad.xyz) |
| PYRATHOS Mining | [pyrathos.imperamonad.xyz](https://pyrathos.imperamonad.xyz) |
| Quantum Engine NFT | [quantum-engine.imperamonad.xyz](https://quantum-engine.imperamonad.xyz) |
| IceBox Mint | [icebox.imperamonad.xyz](https://icebox.imperamonad.xyz) |
| Portfolio | [imperamonad.xyz](https://imperamonad.xyz) |

---

## 📄 License

MIT — see [LICENSE](LICENSE)

---

*Built on [Monad Mainnet](https://monad.xyz) · Pure HTML/Canvas/JS · No dependencies*
