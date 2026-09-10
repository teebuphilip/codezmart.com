# Stripe B2C setup

The custom GTM / SEO / business brief uses a direct Stripe Payment Link. The other package buttons open an email inquiry so availability and delivery can be confirmed before payment.

## What to do in Stripe

1. The `GTM, SEO, Business Brief` card points directly at the Stripe Payment Link.
2. The other package buttons on [`static/buy.html`](./buy.html) open an email draft to `sales@codzmart.com`.
3. Leave `Full Build & Deploy` on the inquiry form so buyers can request scope changes and book a call before you commit.

## Recommended package map

- `customBrief` -> GTM, SEO, Business Brief (Stripe)
- `buildJson` -> Build JSON (email inquiry)
- `grilledBlueprint` -> Grilled Blueprint (email inquiry)
- `plannerPrd` -> Planner / PRD Pack (email inquiry)
- `generatedCode` -> Generated Code ZIP (email inquiry)
## Notes

- The custom brief Payment Link is: `https://buy.stripe.com/fZu4gy2Na4zU2kM3Od87K00`.
- Full Build & Deploy should stay on the inquiry form if you want a negotiation step first.
- All sales are final. No refunds, no partial credits.
