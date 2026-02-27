# ◈ Ledger — Personal Finance Manager

> A private, offline-first, AI-powered personal finance manager built as a single HTML file. No server. No subscription. Your data never leaves your device.

![PWA](https://img.shields.io/badge/PWA-installable-2D5BE3?style=flat-square)
![Offline](https://img.shields.io/badge/works-offline-2A7D4F?style=flat-square)
![Zero Cost](https://img.shields.io/badge/hosting-free-orange?style=flat-square)

---

## Features

**Core tracking**
- Income & expense logging with categories
- Monthly budget limits with over-budget alerts
- Debt tracker — money you owe and money owed to you
- Savings goals with progress tracking
- Upcoming obligations (one-off events + recurring monthly payments)
- Bank savings journal with balance history chart

**AI-powered (optional — requires your own API key)**
- Bill & receipt scanning via camera photo — auto-extracts vendor, amount, date, line items
- AI financial advisor chat (brutally honest, firm, or gentle — your choice)
- Smart income allocation plan when you log income
- Monthly review with auto-generated budget suggestions for next month
- Recursive monthly summary — history compresses automatically so AI context stays lean and cheap

**Privacy & access**
- Password-protected login screen
- Session-based auth — close the tab and it locks automatically
- All data stored in browser localStorage — nothing sent to any server
- Export/import JSON backup

**Progressive Web App**
- Installable on Android and iPhone — works like a native app
- Offline capable after first load
- Responsive — works on phone, tablet, desktop

---

## Deploy in 5 minutes

### What to upload
You need **5 files** — upload all of them to the same folder:
```
finance-manager.html
manifest.json
icon-192.svg
icon-512.svg
README.md  (optional)
```

### Steps

**1. Create a GitHub account** at github.com if you don't have one.

**2. Create a new repository**
- Click **+** → New repository
- Name it `ledger` (or anything)
- Set to **Public**
- Check "Add a README file"
- Click **Create repository**

**3. Upload your files**
- In your repo, click **Add file → Upload files**
- Drag all 5 files in
- Click **Commit changes**

**4. Enable GitHub Pages**
- Go to repo **Settings** → **Pages** (left sidebar)
- Source: **Deploy from a branch**
- Branch: **main**, Folder: **/ (root)**
- Click **Save**
- Wait ~60 seconds

**5. Your app is live at:**
```
https://YOUR_USERNAME.github.io/ledger/finance-manager.html
```

---

## Install on your phone

**Android (Chrome):**
1. Open the URL in Chrome
2. The "Install Ledger" banner appears at the bottom — tap **Install**
3. Or: 3-dot menu → **Add to Home Screen**

**iPhone (Safari):**
1. Open the URL in **Safari** (must be Safari, not Chrome)
2. Tap the **Share** button → **Add to Home Screen** → **Add**

---

## First login

Default credentials:
- **Username:** `ledger`
- **Password:** `ledger123`

**Change these immediately** — Settings → Change Password.

---

## AI setup (optional)

### Claude (Anthropic) — Best quality, ~$1–2/month with daily use
1. Sign up at [console.anthropic.com](https://console.anthropic.com)
2. Go to API Keys → Create key
3. In Ledger: Settings → AI Provider → Claude → paste key
4. Set a monthly spend limit of $2–3 in the Anthropic console

### Gemini (Google) — Free tier, no credit card required
1. Go to [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)
2. Create an API key (free, 15 requests/minute)
3. In Ledger: Settings → AI Provider → Gemini → paste key

---

## Google Calendar sync (optional)

1. Go to [console.cloud.google.com](https://console.cloud.google.com)
2. Create a project → Enable **Google Calendar API**
3. Create an **API Key** under Credentials
4. In Ledger: Settings → Google Calendar → paste key
5. Set Calendar ID to `primary`
6. Hit **Import from Calendar** — events auto-import as upcoming obligations

---

## Token cost breakdown

| Action | Tokens | Cost (Claude Sonnet) |
|---|---|---|
| Bill scan (iPhone photo, resized) | ~1,100 | ~$0.005 |
| AI chat message | ~700 | ~$0.003 |
| Income plan | ~600 | ~$0.003 |
| Monthly review (2 calls) | ~1,800 | ~$0.008 |
| **Daily use, 1 month** | **~200,000** | **~$0.80** |

The app automatically resizes photos before sending and uses a compressed recursive summary of your financial history — so token usage stays low even after months of data.

---

## Updating

When you get an updated `finance-manager.html`:
1. Go to your GitHub repo
2. Click the file → **pencil icon** (Edit)
3. Select all, paste new content → **Commit changes**
4. Live in ~60 seconds. Your data is untouched.

---

## Privacy

- Everything lives in your **browser's localStorage** on your device
- AI features send data only to Anthropic or Google — using **your own API key**
- Anthropic/Google never receive your financial data without your explicit action
- The GitHub repo only hosts the HTML/JS app shell — no data, no backend
- Export your data regularly: Settings → Export Data

---

## Tech stack

Single HTML file · Vanilla JS · localStorage · Claude/Gemini APIs · GitHub Pages · PWA / Service Worker · SHA-256 auth (WebCrypto API)
