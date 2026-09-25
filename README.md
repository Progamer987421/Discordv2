# AppleMC Bot Manager — Local PC Setup

## Requirements
- **Node.js v18+** — download at https://nodejs.org (pick the LTS version)
- That's it.

---

## Setup (one time)

1. Extract this folder anywhere on your PC
2. Open the folder, double-click **`start.bat`**
   - First run installs dependencies automatically
3. Browser opens at **http://localhost:3000**

---

## Starting after first setup

Double-click **`start.bat`** every time.  
Or open a terminal in the folder and run:
```
node index.js
```

---

## Config (optional)

Edit **`.env`** to change settings:

| Setting | Default | What it does |
|---|---|---|
| `PORT` | `3000` | Port the UI runs on |
| `ADMIN_KEY` | _(blank)_ | Password to protect the UI. Leave blank for no password |
| `WEBSHARE_API_KEY` | _(blank)_ | Auto-loads your Webshare proxy pool on startup |

---

## Bot flow

1. Launch bot → bot spawns frozen, no movement
2. ANTIBOT check passes → status shows **"waiting for captcha"**
3. Go to **Captcha Viewer**, fetch the captcha image
4. Type the answer, hit **Submit**
5. Bot automatically sends `/register password password` after 4.5 seconds
6. Bot stays still — done

---

## Folder structure

```
applemc-local/
├── index.js          ← server entry point
├── botManager.js     ← bot logic
├── proxyManager.js   ← proxy pool
├── captchaSolver.js  ← captcha handling
├── package.json      ← dependencies
├── .env              ← config
├── start.bat         ← Windows launcher
└── public/
    └── index.html    ← web UI
```
