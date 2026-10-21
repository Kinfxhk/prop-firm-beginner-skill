# Output schemas (V0.1.1)

## Rule Card row

| field | value | url | opened_at | saw | status |
|-------|-------|-----|-----------|-----|--------|

- `opened_at`: ISO-8601 with Asia/Hong_Kong offset (or `+08:00`)
- `status`: `verified` | `pending` | **failure-template** when official sources lack the fact
- Empty `value` allowed only when:
  - mid-check (`status: pending`), **or**
  - failure template is attached (`methods_tried` + `urls_opened` + conclusion `以上來源未見公開資料`)
- Do **not** use bare「未能核實」without `methods_tried` + at least one opened URL (or an explicit note that the applicable path had no link to open after homepage/Help search)

## Required-attempt fields (every firm × product-line)

Must attempt (verified, pending, or failure-template):

| key | what to look for on official pages |
|-----|-------------------------------------|
| drawdown / max DD / trailing | existing |
| daily_loss | existing |
| consistency / min trading days | existing |
| payout / profit split | existing |
| geo / region | existing |
| `vpn_vps_multi_location_login` | VPN / VPS / multi-location or multi-device login limits |
| `hedging` | hedging, opposite positions, multi-account hedge |
| `penalties` | official consequences only (account disable, profit confiscation, void account, etc.) |
| `trading_sessions` | session hours, overnight, weekend, news trading windows |
| `commissions_spreads_fees` | commission, spread, platform / data fees |

## Failure template (replaces bare「未能核實」)

```text
- topic: …
- methods_tried: [homepage | help_search | tos_pdf | checkout | official_x]
- urls_opened:
  - url: …
    opened_at: …
    saw: …
- conclusion: 以上來源未見公開資料
```

`official_x` only for promo deadlines. Never invent fees, DD, or day counts.

## Shortlist firm line

`id` · `display_name` · `product_line` · flags (`geo_ok` / `platform_ok` / …) · `verify_note`

## CTA block

1. Disclosure (from affiliates yaml)
2. Link (if any)
3. Reminder: rules = official site only; not investment advice
