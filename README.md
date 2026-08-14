# VIZLO — Deploy Guide

This turns VIZLO into a real, live website with its own working AI brain — no coding needed, just follow the steps.

## What's inside
- `public/index.html` — the VIZLO console (frontend you see and use)
- `api/chat.js` — a small backend that talks to Anthropic on your behalf, keeping your API key private
- Your API key is NEVER in this code — it's added separately in Step 3, safely.

## Step 1 — Get an Anthropic API key
1. Go to https://console.anthropic.com
2. Sign up / log in
3. Go to "API Keys" and create a new key
4. Copy it somewhere safe (you'll paste it once in Step 3)
5. Note: this is pay-as-you-go, separate from any Claude.ai subscription. Add a small amount of credit to your account — light daily use is usually just a few dollars a month.

## Step 2 — Put this project on GitHub
1. Go to https://github.com and create a free account if you don't have one
2. Create a new repository (name it `vizlo` or whatever you like)
3. Upload all the files from this folder into that repository
   (Easiest way: on the repo page, click "Add file" → "Upload files", then drag in everything from this folder)

## Step 3 — Deploy on Vercel (free)
1. Go to https://vercel.com and sign up using your GitHub account
2. Click "Add New Project"
3. Select the GitHub repo you just created
4. Before clicking Deploy, open "Environment Variables" and add:
   - Name: `ANTHROPIC_API_KEY`
   - Value: (paste the key you copied in Step 1)
5. Click Deploy
6. Wait ~30 seconds — Vercel gives you a live link like `https://vizlo-yourname.vercel.app`

That's it. Open that link on your phone or laptop — VIZLO is now live, with a real working brain, safely deployed.

## If something breaks
- **"Server is missing ANTHROPIC_API_KEY"** → you skipped Step 3.4, go add the environment variable in your Vercel project settings, then redeploy.
- **Still not responding** → check your Anthropic console has credit/billing set up.
- Want changes to how VIZLO looks or behaves? Just edit `public/index.html` and push the change to GitHub — Vercel redeploys automatically.

## A note on cost & safety
- Never share your API key with anyone or paste it into the frontend code — it must only ever live in Vercel's Environment Variables.
- You control usage and cost directly from console.anthropic.com — you can set spend limits there too.
