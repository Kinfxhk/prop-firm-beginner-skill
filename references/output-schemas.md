# Output schemas (V0)

## Rule Card row

| field | value | url | opened_at | saw | status |
|-------|-------|-----|-----------|-----|--------|

- `opened_at`: ISO-8601 with Asia/Hong_Kong offset (or `+08:00`)
- `status`: `verified` | `未能核實` | `pending`
- Empty `value` allowed only when `status` is `未能核實` or `pending`

## Shortlist firm line

`id` · `display_name` · `product_line` · flags (`geo_ok` / `platform_ok` / …) · `verify_note`

## CTA block

1. Disclosure (from affiliates yaml)
2. Link (if any)
3. Reminder: rules = official site only; not investment advice
