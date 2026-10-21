---
name: prop-firm-beginner
description: >
  Help beginners choose a proprietary trading firm, read challenge/funded rules,
  answer common FAQ, and build Rule Cards with open-page verification. Link
  Chinese deep-dives to propfirmsdrama.com. Use when the user asks which prop
  firm to pick, what drawdown/consistency means, payout timing, or how to verify
  a promo. Not investment advice. Never teach geo/KYC bypass or guarantee a pass.
---

# Prop Firm Beginner Skill (V0)

## Hard rules

1. **Open-page verify (FAIL if missing).** For any price, rule, payout, geo limit, or promo: open the official page (homepage / Help / TOS / checkout; official X only for promo deadlines). Record **`url`**, **`opened_at`** (ISO-8601, Asia/Hong_Kong), and **`saw`** (what you observed). If you did not open the page → output **`未能核實`**. Never treat memory, forums, Trustpilot, Discord, or affiliate emails as the rule source of truth.
2. **Not investment advice.** Prop products typically use **simulated capital** and involve **challenge / subscription fee risk**. Say so on Rule Cards and CTAs. No trading signals. No “guaranteed pass”.
3. **No impersonation.** Do not speak as a firm’s support. Do not embed firm logos as Skill branding. Firm names are descriptive citations only (see NOTICE).
4. **No geo / KYC bypass.** Explain that restrictions exist; link official Help/TOS. Never teach how to circumvent region or identity checks.
5. **Trustpilot / forums = 对照 only.** Useful for risk colour; never for Rule Card numeric fields.
6. **Affiliates.** Every CTA that uses a tracking link must include disclosure (from `affiliates.example.yaml` pattern or local override). Never hardcode secret / unpublished codes in this repo. Operators supply their own compliant codes.
7. **Two layers.** Fact layer = official pages. Interpretation layer = PFD / education links via `resources/pfd-map.yaml` (`resource: pfd`). Do not paste full PFD articles into the repo.
8. **Honest stubs.** `firms/*.yaml` hold URLs + `product_lines` only. Never invent fees, DD, targets, or payout days into YAML.

## Out of scope (explicit)

- WordPress / site ops / auto-publishing to any live site
- Trading signals or “guaranteed challenge pass”
- Teaching geo / KYC / payment bypass
- Bundling locked rule numbers that go stale

## Workflow

1. **Questionnaire** — product line (futures / CFD / forex — do not mix tables), location (esp. HK / restricted), budget, account size preference, platform (NT / Tradovate / Rithmic / MT5 / …), goal (challenge vs instant funded), payout cadence, EA/news preference → optional `profile.yaml` summary.
2. **Shortlist** — match `firms/*.yaml` stubs by `product_lines` + geo/platform hints from **verified** pages; mark `geo_ok` / `platform_ok` / `payout_method_ok` / `active_pending` only after open-page checks (or leave pending).
3. **Rule Card** — one firm × one product line; every cell per schema below.
4. **Verify** — command pattern: `verify firm <name> [topic]` → homepage → Help → TOS → checkout (and official X only for promo deadlines). Missing source → delete claim or mark `未能核實`.
5. **Optional PFD** — if user wants Chinese explainers / case studies / payout stories, add links from `resources/pfd-map.yaml` (do not copy article bodies).
6. **CTA** — if affiliate link used: disclosure sentence every time; rules still “以官網為準”.

## Rule Card output schema

Every row:

| field | value | url | opened_at | saw | status |
|-------|-------|-----|-----------|-----|--------|

- `status`: `verified` | `未能核實` | `pending`
- `opened_at`: Asia/Hong_Kong ISO-8601 when the page was opened
- Typical fields (fill only what you verified): challenge steps, profit target, daily loss, max DD / trailing, consistency, news / overnight, min trading days, reset price, activation, profit split %, payout cycle / min payout, prohibited behaviour, alleged hidden rules (label **alleged** + non-authority source, or omit)

## FAQ routing

Use `faq/index.yaml` + `faq/*.md` for short answers. Point “詳見 PFD” to `resources/pfd-map.yaml` topic keys. Never lock numbers into FAQ bodies.

## Affiliates

Copy `affiliates.example.yaml` → local `affiliates.yaml` (gitignored). Structure: firm id → `link`, `code`, `disclosure`. Empty link/code in the example is intentional.

## Coverage

See `references/coverage-matrix.md`. Methodology / tier scoring is V0.1 stub in `references/methodology-tier.md`.
