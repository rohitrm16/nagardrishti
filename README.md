# NagarDrishti 🇮🇳
### India's Civic Audit Platform

Real-time monitoring of traffic, footpaths, garbage, cleanliness, and water body pollution across India — powered by citizens, documented for accountability.

---

## Live Site

Deploy to GitHub Pages and your site will be live at:
```
https://yourusername.github.io/nagardrishti
```

Or point a custom domain (`nagardrishti.in`) via DNS settings.

---

## What's Inside

```
nagardrishti/
├── index.html          ← Complete landing page (single file)
├── README.md           ← This file
└── _config.yml         ← GitHub Pages configuration
```

Everything — HTML, CSS, and JavaScript — lives in `index.html`. No build tools, no dependencies, no npm. Just open the file in a browser or deploy it anywhere.

---

## Features

- **Live Incident Dashboard** — Leaflet map with CartoDB dark tiles, 16 incident markers across India
- **4 Audit Categories** — Traffic, Footpath, Garbage, Cleanliness
- **Water Pollution Audits** — River / Lake / Water Body Pollution + Aquatic Ecosystem Damage
- **Community Surge Framework** — Auto-escalation when 3 / 5 / 10+ citizens confirm the same issue
- **Citizen Auditor Badge** — 5 levels from Observer to Guardian, points-based system
- **Best Practices** — Before/After scenarios for each category with audit tips
- **Date Range Toggle** — 24h / 7 days / 15 days / 30 days historical view
- **Fully Responsive** — Mobile, tablet, desktop, all browsers
- **Submit an Audit Modal** — Photo + video evidence upload, GPS auto-fill, severity selector
- **Quick Start Guide** — 4-step citizen onboarding flow
- **Incident Lifecycle** — Reported → Validated → Active → Resolved
- **Escalation Pathway** — Issue-type routing to correct municipal authority

---

## Deploy to GitHub Pages (5 minutes)

1. Create a new GitHub repository named `nagardrishti`
2. Upload `index.html`, `README.md`, and `_config.yml`
3. Go to **Settings → Pages**
4. Under **Source**, select `Deploy from a branch`
5. Choose `main` branch, `/ (root)` folder
6. Click **Save**
7. Your site is live in 60 seconds at `https://yourusername.github.io/nagardrishti`

---

## Connect a Custom Domain

After buying `nagardrishti.in` from BigRock / GoDaddy:

1. In your GitHub repo → **Settings → Pages → Custom domain**
2. Enter `nagardrishti.in` and save
3. At your domain registrar, add these DNS records:

```
Type    Name    Value
A       @       185.199.108.153
A       @       185.199.109.153
A       @       185.199.110.153
A       @       185.199.111.153
CNAME   www     yourusername.github.io
```

4. Wait 10–30 minutes for DNS to propagate
5. Site is live at `nagardrishti.in` with automatic HTTPS ✅

---

## Connect Real Data (Supabase / Firebase)

The platform currently runs on demo data. To make it live:

### Firebase (Recommended for India — Mumbai data centre)

1. Create a project at [console.firebase.google.com](https://console.firebase.google.com)
2. Enable Firestore Database
3. Add your Firebase config to `index.html` (replace the `// FIREBASE CONFIG` comment)
4. Wire `doReport()` to insert into Firestore
5. Add Firestore Realtime listener to update map markers live

### Supabase (Recommended for SQL / reporting)

1. Create a project at [supabase.com](https://supabase.com)
2. Create the `incidents` table (schema in `database/schema.sql` — coming soon)
3. Replace `YOUR_SUPABASE_URL` and `YOUR_SUPABASE_ANON_KEY` in `index.html`
4. Wire `doReport()` to INSERT into Supabase

---

## Security Checklist (Before Going Live)

- [ ] Cloudflare DNS (free DDoS protection) — point nagardrishti.in to Cloudflare
- [ ] Firebase Security Rules — `allow delete: if false` on all incident records
- [ ] Firebase Authentication — wire Google / Mobile OTP sign-in
- [ ] Input validation on all audit submissions
- [ ] Rate limiting — max 10 audits per user per hour
- [ ] UptimeRobot monitoring — free ping every 5 minutes
- [ ] Firebase automated daily backup to Cloud Storage

---

## Google Apps Script (Contact / Notifications)

When you re-add a contact form or want email notifications for new audits:

1. Go to [script.google.com](https://script.google.com)
2. Sign in as your Google account
3. Paste the Apps Script code from `scripts/contact-form.gs` (coming soon)
4. Deploy as Web App → Anyone can access
5. Copy the Web App URL into `index.html` → `var APS_URL = 'YOUR_URL'`

---

## Roadmap

```
Phase 1 — Now
  ✅ Landing page live on GitHub Pages
  ✅ Custom domain nagardrishti.in
  ⬜ Firebase connected (real audit storage)
  ⬜ Authentication (Mobile OTP)

Phase 2 — Month 2-3
  ⬜ Real-time map updates (Firestore onSnapshot)
  ⬜ Dynamic city count from real data
  ⬜ Community Surge from real confirmations
  ⬜ Citizen Auditor Badge system live

Phase 3 — Month 4-6
  ⬜ Municipal officer dashboard
  ⬜ Per-city ward-level filtering
  ⬜ Monthly SLA compliance reports
  ⬜ First paying municipal client
```

---

## Cost to Run

| Item | Cost |
|---|---|
| GitHub Pages hosting | ₹0 |
| Cloudflare (DDoS protection) | ₹0 |
| Firebase free tier | ₹0 |
| Domain nagardrishti.in | ₹600/year |
| **Total** | **₹600/year · ₹0/month** |

---

## Tech Stack

| Layer | Tool |
|---|---|
| Frontend | Vanilla HTML / CSS / JavaScript (no framework) |
| Map | Leaflet.js + CartoDB dark tiles |
| Fonts | Plus Jakarta Sans + IBM Plex Mono (Google Fonts) |
| Hosting | GitHub Pages / Netlify |
| CDN + Security | Cloudflare (free tier) |
| Database (planned) | Firebase Firestore / Supabase PostgreSQL |
| Auth (planned) | Firebase Authentication |
| Real-time (planned) | Firestore onSnapshot / Supabase Realtime |

---

## Made with ❤️ in India 🇮🇳

Built for citizens, designed for accountability.

*NagarDrishti — Every city. Every audit. Real change.*
