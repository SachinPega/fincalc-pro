# FinCalc Pro — Complete Setup Guide
## Phase 1 → Phase 2 → Phase 3 → Earn Money

---

## ✅ PHASE 1: HOST ON GITHUB PAGES (Free — 30 mins)

### Step 1 — Create GitHub Account
1. Go to https://github.com → click Sign Up
2. Enter your email, create a password, verify email

### Step 2 — Create Repository
1. Click the **+** icon (top right) → **New repository**
2. Repository name: `fincalc-pro`
3. Set to **Public**
4. Click **Create repository**

### Step 3 — Upload Your Files
1. Click **Add file → Upload files**
2. Drag and drop ALL files from this folder:
   ```
   index.html
   manifest.json
   sw.js
   privacy-policy.html
   twa-manifest.json
   icons/         (entire folder)
   .well-known/   (entire folder)
   screenshots/   (entire folder)
   ```
3. Click **Commit changes**

### Step 4 — Enable GitHub Pages
1. Go to **Settings** (top menu of your repo)
2. Scroll down to **Pages** (left sidebar)
3. Under Source → select **Deploy from a branch**
4. Branch: **main** | Folder: **/ (root)**
5. Click **Save**

### Step 5 — Get Your Live URL
After 2–3 minutes your app is live at:
```
https://YOUR-GITHUB-USERNAME.github.io/fincalc-pro/
```
Open it on your Android phone in Chrome — it should show an
"Add to Home Screen" banner. That means your PWA works! ✅

---

## ✅ PHASE 2: BUILD ANDROID APP (Free — 1 hour)

### Method A: PWABuilder (No-code, Easiest)
1. Go to https://www.pwabuilder.com
2. Paste your GitHub Pages URL
3. Click **Package for stores**
4. Click **Google Play** → Download
5. You get a `.aab` file — this is your Play Store app! ✅

### Method B: Bubblewrap (More control)
```bash
# Install Node.js from https://nodejs.org first
npm install -g @bubblewrap/cli

mkdir fincalc-android && cd fincalc-android
bubblewrap init --manifest https://YOUR-USERNAME.github.io/fincalc-pro/manifest.json
bubblewrap build
# → Creates app-release-bundle.aab
```

---

## ✅ PHASE 3: PUBLISH ON GOOGLE PLAY ($25 one-time)

### Step 1 — Create Developer Account
1. Go to https://play.google.com/console
2. Sign in → Pay **$25 registration fee**
3. Complete identity verification (1–2 days)

### Step 2 — Create App
1. Click **Create app**
2. Fill in:
   - **App name:** FinCalc Pro - Financial Calculator
   - **Default language:** English (India)
   - **Type:** App | **Category:** Finance
   - **Free or Paid:** Free

### Step 3 — Store Listing
Copy-paste these:

**Short description (80 chars):**
```
EMI, SIP, GST, Tax & Business Calculator — Fast & Free
```

**Full description:**
```
FinCalc Pro is India's most complete financial calculator app.

🔢 BASIC CALCULATOR
Fast calculator with history.

🏦 LOAN / EMI CALCULATOR  
Calculate monthly EMI. See total interest and payment.

📈 INVESTMENT CALCULATORS
• SIP — Plan mutual fund returns
• Lump Sum — See compound growth  
• FD / RD — Fixed deposit maturity
• ROI — Return on investment

💰 TAX CALCULATORS
• Income Tax (New Regime 2024-25)
• GST with CGST/SGST breakup
• Profit & Margin calculator

✨ Works offline | Dark theme | No login needed | Free
```

**App icon:** Upload `icons/icon-512.png`

**Feature graphic (1024×500):**
Create free at https://canva.com → search "App Store Banner"

**Screenshots:**
Install the APK on your phone → take 4-5 screenshots → upload

### Step 4 — Upload App Bundle
1. Go to **Production → Releases → Create new release**
2. Upload your `.aab` file
3. Release notes: `First release of FinCalc Pro`
4. Click **Review → Start rollout**

### Step 5 — Fill Required Sections
- **Privacy policy URL:** `https://YOUR-USERNAME.github.io/fincalc-pro/privacy-policy.html`
- **Data safety:** Select "No data collected"
- **Target audience:** Everyone (13+)
- **Ads:** Yes (after you add AdMob)

### Step 6 — Wait
Google reviews in **3–7 days** → Email notification when LIVE 🎉

---

## 💵 EARN MONEY WITH ADMOB

### Step 1 — Create AdMob Account
1. Go to https://admob.google.com
2. Sign in with your Google account
3. Click **Get started**
4. Add your app → Select **Android** → Add manually
5. Enter package name: `com.fincalcpro.app`

### Step 2 — Create Ad Units
In AdMob dashboard:
1. Click your app → **Ad units → Add ad unit**
2. Create **Banner ad** → name it "Top Banner"
   → Copy the **Ad unit ID** (looks like: ca-app-pub-XXXXX/XXXXXXXX)
3. Create another **Banner ad** → name it "Bottom Banner"
   → Copy this **Ad unit ID** too

### Step 3 — Add AdMob to Your App
Open `index.html` in any text editor (Notepad is fine).

Find this line (near top):
```html
<!-- <script async src="https://pagead2.googlesyndication.com/...
```
Uncomment it and replace with YOUR Publisher ID:
```html
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-app-pub-YOUR_ID" crossorigin="anonymous"></script>
```

Find the top ad slot comment block and replace:
```html
<ins class="adsbygoogle"
  style="display:inline-block;width:320px;height:50px"
  data-ad-client="ca-app-pub-YOUR_PUBLISHER_ID"
  data-ad-slot="YOUR_TOP_AD_UNIT_ID">
</ins>
<script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
```

Do the same for the bottom banner.

### Step 4 — Upload Updated Files to GitHub
Re-upload your updated `index.html` to GitHub →
Rebuild AAB using PWABuilder → Upload new release to Play Store

---

## 💰 INCOME ESTIMATE

| Daily Users | Monthly Impressions | Est. Monthly Income |
|-------------|--------------------|--------------------|
| 200         | 12,000             | $12–$30            |
| 500         | 30,000             | $30–$75            |
| 1,000       | 60,000             | $60–$150           |
| 5,000       | 300,000            | $300–$750          |

*CPM in India: $1–$2.50 for finance apps*

### Tips to grow downloads fast:
- Share in WhatsApp groups (CA groups, finance groups)
- Post on Reddit r/IndiaInvestments
- Post on Facebook finance groups
- ASO: Use keywords like "EMI calculator", "SIP calculator", "GST calculator" in your title/description

---

## 📁 YOUR FILE STRUCTURE (Upload all of these to GitHub)

```
fincalc-pro/                  ← Your GitHub repo
├── index.html                ← Main app (with AdMob slots)
├── manifest.json             ← PWA config
├── sw.js                     ← Offline service worker
├── privacy-policy.html       ← Required for Play Store
├── twa-manifest.json         ← TWA/Bubblewrap config
├── .well-known/
│   └── assetlinks.json       ← Links website to Android app
├── icons/
│   ├── icon-72.png
│   ├── icon-96.png
│   ├── icon-128.png
│   ├── icon-144.png
│   ├── icon-152.png
│   ├── icon-192.png
│   ├── icon-384.png
│   └── icon-512.png          ← Play Store icon
└── screenshots/              ← Add phone screenshots here
```

---

*All the best! Your first dollar is just one week away. 🚀*
