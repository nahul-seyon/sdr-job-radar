# SDR Job Radar

An [n8n](https://n8n.io) workflow that monitors a list of SaaS company careers pages every morning, classifies new job openings with an LLM, and sends me a daily email of roles worth applying to.

I'm a CS graduate looking for my first Sales Development Representative role. Checking 20 careers pages every morning was burning an hour a day and making me apply to fewer roles, not more. So I automated it.

## Status

🚧 **In active development — v1 shipping by May 2, 2026.**

This README will be updated with screenshots, a demo video, and setup instructions as each piece lands.

## What it does

Every morning at 8 AM IST, the workflow:

1. Reads a list of target companies from a Google Sheet
2. Fetches each company's careers page
3. Extracts the current job listings
4. Sends each listing through a Gemini LLM call that classifies whether it's an SDR, BDR, or Inside Sales role appropriate for a recent graduate
5. Appends qualifying roles to a second Google Sheet with the company name, role title, link, and one-line reason
6. Emails me a clean summary of the day's matches

I wake up. I open one email. I apply. That's the whole point.

## Stack

- **Workflow orchestration:** n8n (cloud, free tier)
- **LLM:** Google Gemini Flash (free tier via Google AI Studio)
- **Data store:** Google Sheets
- **Delivery:** Gmail
- **Schedule:** Daily cron, 8 AM IST

No paid infrastructure. The entire stack runs on free tiers, which is deliberate — the project should be reproducible by any other job-seeking fresher with zero budget.

## Why I'm building this in public

Two reasons. First, a project I use daily is a project I can demonstrate and defend in any interview — and that's worth more to me right now than a portfolio of half-finished experiments. Second, building in public forces me to ship. If this repo sits empty for two weeks after this README, that's public evidence I didn't follow through, and I don't want to live with that.

## What's coming

- [ ] n8n cloud setup, Google Sheets wiring, cron trigger working
- [ ] HTTP fetch + HTML extract for first company (Freshworks)
- [ ] Gemini classification node, prompt tuned on real listings
- [ ] End-to-end flow for one company, then expand to five
- [ ] Ten companies, README updated with screenshots, Loom demo recorded
- [ ] v1.1 — Handle JavaScript-rendered careers pages
- [ ] v1.2 — WhatsApp delivery instead of email
- [ ] v2 — Score each role 1-10 for fit based on my resume, not just yes/no

## About me

I'm Nahul Seyon, a 2025 CS graduate from Tamil Nadu looking for SDR roles at SaaS and AI-native companies. If you're a hiring manager reading this: this project is a small window into how I'll think about your team's tooling and pipeline from day one. I'd love to talk. [LinkedIn](https://linkedin.com/in/nahul-seyon) / seyonnahul@gmail.com
