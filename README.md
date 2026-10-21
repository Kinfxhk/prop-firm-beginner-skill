# prop-firm-beginner-skill

**本說明以繁體中文為準。** English follows below.

**狀態：V0 脚手架** — 開源 Agent Skill，協助新手**選擇 prop firm**、以**即時開頁核實**查閱規則、回答 FAQ，並可選擇連至 [Propfirms Drama](https://propfirmsdrama.com/) 閱讀繁中長文。**非投資建議。** 與任何 proprietary trading firm 無隸屬關係。

[English](#english)

## 這是什麼

適用於 Cursor／Claude／Hermes 等環境的 [`SKILL.md`](./SKILL.md)，另附：

- 公司 **URL stub**（`firms/`）— **不鎖定**挑戰費、回撤等數字
- 18 題 FAQ 短答（`faq/`）
- PFD 主題 → URL 對照（`resources/pfd-map.yaml`）
- 聯盟連結 **範例**模板（`affiliates.example.yaml`）— 強制披露句式

## 硬規則（Agent 必須遵守）

| 規則 | 說明 |
|------|------|
| 開頁核實 | 價格／規則／出金／地區／優惠 → 必須有 `url`＋`opened_at`＋`saw`，否則標示 **未能核實** |
| AS IS／非投資建議 | 模擬資金＋挑戰費風險；不出交易訊號；不保證通過挑戰 |
| 不冒充 | 不以 firm logo 作為品牌；不扮演官方客服 |
| 不教導規避地區限制／KYC | 僅連至官方地區限制說明 |
| 聯盟披露 | 每次追蹤 CTA 均須披露；不提交未公開追蹤碼 |

## 安裝

1. Clone 或複製本 repo 至 agent skills 目錄（或直接指向 `SKILL.md`）。
2. （可選）複製 `affiliates.example.yaml` → `affiliates.yaml`，填入**你自己的**連結／碼（請勿 commit）。
3. 例如詢問：「我想在香港做期貨 prop，預算有限，請協助短名單並核實規則。」

## 贊助（Buy Me a Coffee）

[`.github/FUNDING.yml`](./.github/FUNDING.yml) 暫用佔位符 `YOUR_BMC_USERNAME`。建立 [Buy Me a Coffee](https://www.buymeacoffee.com/) 頁面並開啟 repo Sponsorships 後再更新。贊助並不等於與任何 firm 有聯盟關係。

## 免責

僅供教學／規劃輔助。Prop firm 產品涉及費用及虧損風險。規則經常變更；請以官網即時核實為準。稅務／KYC 說明不構成專業意見。

## 授權

MIT — 見 [LICENSE](./LICENSE) 及 [NOTICE](./NOTICE)。

---

## English

**The Traditional Chinese section above is authoritative.** English is a parallel summary.

**Status: V0 scaffold** — Open-source Agent Skill to help beginners **choose a prop firm**, read rules via **open-page verification**, answer FAQ, and optionally bridge to [Propfirms Drama](https://propfirmsdrama.com/) for Chinese deep-dives. **Not investment advice.** Not affiliated with any proprietary trading firm.

### What this is

A Cursor / Claude / Hermes-compatible [`SKILL.md`](./SKILL.md) plus:

- Firm **URL stubs** (`firms/`) — no locked fees or drawdown numbers
- 18-topic FAQ short answers (`faq/`)
- PFD topic → URL map (`resources/pfd-map.yaml`)
- Affiliate **example** template (`affiliates.example.yaml`) with mandatory disclosure pattern

### Hard guarantees (agent must follow)

| Rule | Meaning |
|------|---------|
| Open-page verify | Price/rules/payout/geo/promo → `url` + `opened_at` + `saw`, else **未能核實** |
| AS IS / not advice | Simulated capital + challenge-fee risk; no signals; no guaranteed pass |
| No impersonation | No firm logos as branding; do not act as firm support |
| No geo/KYC bypass | Link official restrictions only |
| Affiliate disclosure | Every tracking CTA; never commit secret codes |

### Install

1. Clone or copy this repo into your agent skills folder (or point the agent at `SKILL.md`).
2. Optionally copy `affiliates.example.yaml` → `affiliates.yaml` and fill **your** links/codes (do not commit).
3. Ask e.g. “我想在香港做期貨 prop，預算有限，請協助短名單並核實規則。”

### Sponsor (Buy Me a Coffee)

[`.github/FUNDING.yml`](./.github/FUNDING.yml) uses placeholder `YOUR_BMC_USERNAME`. Replace after you create a [Buy Me a Coffee](https://www.buymeacoffee.com/) page and enable repo Sponsorships. Funding ≠ affiliation with any firm.

### Disclaimer

Educational planning aid only. Prop firm products involve fees and risk of loss. Rules change; always re-verify on the firm’s official site. Tax/KYC notes are not professional advice.

### License

MIT — see [LICENSE](./LICENSE) and [NOTICE](./NOTICE).
