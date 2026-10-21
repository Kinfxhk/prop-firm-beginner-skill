# prop-firm-beginner-skill

**Status: V0 scaffold** — Open-source Agent Skill to help beginners **choose a prop firm**, read rules via **open-page verification**, answer FAQ, and optionally bridge to [Propfirms Drama](https://propfirmsdrama.com/) for Chinese deep-dives. **Not investment advice.** Not affiliated with any proprietary trading firm.

[繁體中文見下方](#繁體中文)

## What this is

A Cursor / Claude / Hermes-compatible [`SKILL.md`](./SKILL.md) plus:

- Firm **URL stubs** (`firms/`) — no locked fees or drawdown numbers
- 18-topic FAQ short answers (`faq/`)
- PFD topic → URL map (`resources/pfd-map.yaml`)
- Affiliate **example** template (`affiliates.example.yaml`) with mandatory disclosure pattern

## Hard guarantees (agent must follow)

| Rule | Meaning |
|------|---------|
| Open-page verify | Price/rules/payout/geo/promo → `url` + `opened_at` + `saw`, else **未能核實** |
| AS IS / not advice | Simulated capital + challenge-fee risk; no signals; no guaranteed pass |
| No impersonation | No firm logos as branding; do not act as firm support |
| No geo/KYC bypass | Link official restrictions only |
| Affiliate disclosure | Every tracking CTA; never commit secret codes |

## Install

1. Clone or copy this repo into your agent skills folder (or point the agent at `SKILL.md`).
2. Optionally copy `affiliates.example.yaml` → `affiliates.yaml` and fill **your** links/codes (do not commit).
3. Ask e.g. “我想喺香港做期貨 prop，預算有限，幫我短名單同核實規則。”

## Sponsor (Buy Me a Coffee)

[`.github/FUNDING.yml`](./.github/FUNDING.yml) uses placeholder `YOUR_BMC_USERNAME`. Replace after you create a [Buy Me a Coffee](https://www.buymeacoffee.com/) page and enable repo Sponsorships. Funding ≠ affiliation with any firm.

## Disclaimer

Educational planning aid only. Prop firm products involve fees and risk of loss. Rules change; always re-verify on the firm’s official site. Tax/KYC notes are not professional advice.

## License

MIT — see [LICENSE](./LICENSE) and [NOTICE](./NOTICE).

---

## 繁體中文

開源 Agent Skill：幫新手**選 prop firm、睇規則、FAQ、Rule Card**；數字／規則必須**即時開官網核實**（`url`＋`opened_at`＋`saw`，否則標「未能核實」）。中文長文連 [Propfirms Drama](https://propfirmsdrama.com/)。**非投資建議**；唔教繞過地區／KYC；唔保證通過挑戰。聯盟連結每次要披露；repo 唔放未公開追蹤碼。
