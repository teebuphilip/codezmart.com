# Stripe B2C setup

Use a tiny checkout service for the fixed B2C packages. That keeps the public site static, avoids creating 4,000 Stripe products or links, and still gives you Stripe receipts and payment notifications.

## What to do in Stripe

1. Create a Stripe secret key for the checkout service.
2. In Stripe, turn on customer email collection and the post-payment behavior you want.
3. In your Stripe customer email settings, enable successful-payment emails if you want automatic notifications.
4. Keep the site static. The package buttons on [`static/buy.html`](./buy.html) will call the checkout service, which creates the Stripe Checkout Session on demand.
5. Leave `Full Build & Deploy` on the inquiry form so buyers can request scope changes and book a call before you commit.
6. Start the checkout service with `python3 checkout_backend.py` after setting `STRIPE_SECRET_KEY` and `CODEZMART_BASE_URL`.

## Recommended package map

- `enrichedIdea` -> Enriched Idea Pack
- `buildJson` -> Build JSON
- `grilledBlueprint` -> Grilled Blueprint
- `plannerPrd` -> Planner / PRD Pack
- `generatedCode` -> Generated Code ZIP
## Notes

- The checkout service can create a Stripe Checkout Session with `client_reference_id` set to the idea id.
- The checkout service can also attach `sku`, `package`, and `idea` metadata to the Checkout Session and the inline Product metadata.
- Stripe can send email receipts automatically after successful payments.
- Successful payments appear in the Stripe Dashboard, where the metadata will make the order easier to identify.
- Full Build & Deploy should stay on the inquiry form if you want a negotiation step first.
- All sales are final. No refunds, no partial credits.
