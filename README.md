# paste. — Pastebin Clone on Vercel + Upstash

Shareable pastes with custom aliases, expiry, syntax labels, fork, and download.
**Fully free** on Vercel hobby + Upstash free tier.

## Features
- 🔗 Custom aliases `/p/my-snippet`
- ⏱ Expiry: 10m / 1h / 1d / 1w / 1mo / Never
- 👁 View counter
- 🍴 Fork any paste
- ⬇️ Download as `.txt`
- 🌙 Dark / light mode
- 18 syntax labels

## Deploy to Vercel (5 steps)

### 1. Create Upstash Redis (free)
- Go to https://console.upstash.com → Create Database
- Choose **Redis**, any region, free tier
- Copy **UPSTASH_REDIS_REST_URL** and **UPSTASH_REDIS_REST_TOKEN**

### 2. Add env vars in Vercel
Vercel Dashboard → your project → Settings → Environment Variables:
```
UPSTASH_REDIS_REST_URL     = https://xxxx.upstash.io
UPSTASH_REDIS_REST_TOKEN   = AXxx...
```

### 3. Redeploy
Vercel Dashboard → Deployments → Redeploy (or push a commit).

### 4. Done 🎉
Your pastebin is live!

## File structure
```
/api/paste.js       ← Serverless API (create / read / delete)
/public/index.html  ← Full frontend SPA
/vercel.json        ← Routing rules
/package.json       ← @upstash/redis dependency
```

## Local dev
```bash
npm install
npx vercel dev
```
Set env vars in `.env.local`:
```
UPSTASH_REDIS_REST_URL=...
UPSTASH_REDIS_REST_TOKEN=...
```
