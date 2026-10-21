# Contributing

- Clean-room: do not scrape closed comparison apps or copy proprietary rule tables into this tree.
- `firms/*.yaml` may only hold URLs, product-line labels, and verification metadata — **no locked fee / DD / profit-target numbers**.
- Every Rule Card cell must be filled at runtime with `url` + `opened_at` + `saw`, or marked `未能核實`.
- Affiliate: never commit real tracking codes; update `affiliates.example.yaml` structure only.
- FAQ answers stay short; deep Chinese explainers belong on [Propfirms Drama](https://propfirmsdrama.com/) via `resources/pfd-map.yaml` URL slots.
- AI-assisted patches OK if a human reviews: no secrets, no firm logos as branding, no geo/KYC bypass guidance.
