# CodezMart

> Tools built by a guy who made every mistake.

Static site for [codezmart.com](https://codezmart.com) — a storefront for done-for-you builder services. No SaaS. No subscriptions. No VC deck. Just cheap, battle-tested tools that tell you the truth.

Built by Lou Zerr. 943 mistakes and counting.

---

## What's in the yard

| Product | Price | Status |
|---|---|---|
| Startup Idea Validation Report | $97 | ✅ Live |
| Job Score Service | $47 | 🔜 Coming soon |
| Build-Ready Spec | $197 | 🔜 Coming soon |

---

## How it works

Customer pays via Stripe → operator runs pipeline on `fo-brain` → report delivered in 48 hours.

No app. No dashboard. No auth. Pipeline cost per run: ~$0.05.

---

## Files

```
index.html          → Main storefront (codezmart.com)
sample-report.html  → Live sample Pass 0.5 report (codezmart.com/sample)
lou-zerr.svg        → Brand mascot
README.md           → This file
```

---

## Deploy

Hosted on Vercel. Push to `main` → auto-deploy.

```bash
# connect once
vercel --prod

# all subsequent deploys are just
git push origin main
```

Point `codezmart.com` DNS to Vercel via dashboard.

---

## Adding a new product

1. Create a Stripe payment link at [stripe.com/dashboard](https://stripe.com/dashboard)
2. In `index.html`, find the `soon` card you want to activate
3. Change `class="card soon"` → `class="card live"`
4. Replace `<div class="btn-soon">Notify Me</div>` with:
```html
<a href="YOUR_STRIPE_LINK" class="btn" target="_blank">Get Report →</a>
```
5. Update `card-status` from `○ Coming soon` to `● Live now`
6. Push to main

---

## Fulfillment

When a Stripe payment hits:

```bash
# on fo-brain
cd ~/AFH/gap-analysis
./run_full_pipeline.sh <customer_idea.json>

# outputs land in
gap-analysis/outputs/
```

Zip the outputs directory and email to customer. Done.

---

## Brand

- **Mascot:** Lou Zerr — `lou-zerr.svg`
- **Substack:** [confessionsofaloser.substack.com](https://confessionsofaloser.substack.com)
- **Voice:** Uncorporate. Blunt. Built by someone who failed publicly for 25 years.
- **Colors:** Black `#0a0a0a`, Cream `#f5f0e8`, Yellow `#f5c518`, Red `#e63425`
- **Fonts:** Bebas Neue (headings), Space Mono (body), DM Sans (copy)

---

## Contact

[teebu@yahoo.com](mailto:teebu@yahoo.com)
