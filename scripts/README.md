# Scripts

V0 ships **no** automation that places orders or bypasses geo/KYC.

## Manual verify checklist

1. Open firm `urls.homepage` → Help → TOS → pricing/checkout.
2. Record `url`, `opened_at` (Asia/Hong_Kong), `saw` for each Rule Card cell.
3. Optional: official X/Twitter **only** for promo deadline wording.
4. If any step fails → `未能核實`.

## curl homepage health (scaffold)

```bash
curl -sS -o /dev/null -w "%{http_code} %{url_effective}\n" -L --max-time 12 \
  "https://example.com/"
```

Do not scrape closed comparison products. Do not store challenge fees from HTML into `firms/*.yaml`.
