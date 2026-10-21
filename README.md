# prop-firm-beginner-skill

**本說明以繁體中文為準。** English follows below.

**狀態：V0 脚手架（0.1.2）** — 開源 Agent Skill，協助新手**選擇 prop firm**、以**即時開頁核實**查閱規則、回答 FAQ，並可選擇連至 [Propfirms Drama](https://propfirmsdrama.com/) 閱讀繁中長文。**非投資建議。** 與任何 proprietary trading firm 無隸屬關係。

[English](#english)

## 這是什麼

適用於 Cursor／Claude／Hermes 等環境的 [`SKILL.md`](./SKILL.md)，另附：

- 公司 **URL stub**（`firms/`）— **不鎖定**挑戰費、回撤等數字
- 21 題 FAQ 短答（`faq/`）— 只教如何查；答案仍須 runtime 開頁
- PFD 主題 → URL 對照**模板**（`resources/pfd-map.yaml`；V0 多數留空，由使用者自行填入）
- 聯盟連結 **範例**模板（`affiliates.example.yaml`）— 強制披露句式

## 硬規則（Agent 必須遵守）

| 規則 | 說明 |
|------|------|
| 開頁核實 | 價格／規則／出金／地區／優惠 → 必須有 `url`＋`opened_at`＋`saw`；失敗輸出跟從 `SKILL.md` Failure template |
| 盡力查＋列方法 | 未試夠路徑不得空口「未能核實」；須列已用方法＋已開 URL＋`opened_at`，再寫「以上來源未見公開資料」；禁止發明數字 |
| 先釐清居住地 | 未取得 `user_geo`（國家／地區，用戶自報即可）前，不給「可用／可出金」結論；出金與適用性須按該地官方頁核實，並標明「以用戶所報居住地＝X 為前提」 |
| AS IS／非投資建議 | 模擬資金＋挑戰費風險；不出交易訊號；不保證通過挑戰 |
| 不冒充 | 不以 firm logo 作為品牌；不扮演官方客服 |
| 不教導規避地區限制／KYC | 僅連至官方地區限制說明 |
| 聯盟披露 | 每次追蹤 CTA 均須披露；不提交未公開追蹤碼 |

## 安裝

1. Clone 或複製本 repo 至 agent skills 目錄（或直接指向 `SKILL.md`）。
2. （可選）複製 `affiliates.example.yaml` → `affiliates.yaml`，填入**你自己的**連結／碼（請勿 commit）。
3. 例如詢問：「我想在香港做期貨 prop，預算有限，請協助短名單並核實規則。」

常見 skills 目錄（實際路徑視 agent 版本而定）：

- Hermes：`~/.hermes/profiles/<profile>/skills/`
- 共享 skills（DeepSeek Harness／OpenCode 等）：`~/.agents/skills/`
- Claude Code：`~/.claude/skills/`
- Cursor：專案的 `.cursor/skills/` 或你設定的全域 skills 目錄

## V0 限制

- 10 個公司 URL stub、21 題 FAQ；**沒有自動 verify script**，`verify` 是 agent 的開頁程序，不是可執行指令。
- `resources/pfd-map.yaml` 是模板；`null` 代表未設定，不要發明 PFD URL。
- `firms/*.yaml` 只存 URL 與 product line，不存費用、回撤、利潤目標或出金日數。
- FAQ 以香港書面語書寫；SKILL.md 為英文。若你要對外發佈，請自行調整語氣及披露。

## 贊助（Buy Me a Coffee）

[`.github/FUNDING.yml`](./.github/FUNDING.yml) 暫用佔位符 `YOUR_BMC_USERNAME`。建立 [Buy Me a Coffee](https://www.buymeacoffee.com/) 頁面並開啟 repo Sponsorships 後再更新。贊助並不等於與任何 firm 有聯盟關係。

## 免責

僅供教學／規劃輔助。Prop firm 產品涉及費用及虧損風險。規則經常變更；請以官網即時核實為準。稅務／KYC 說明不構成專業意見。

## 授權

MIT — 見 [LICENSE](./LICENSE) 及 [NOTICE](./NOTICE)。

---

## English

**The Traditional Chinese section above is authoritative.** English is a parallel summary.

**Status: V0 scaffold (0.1.2)** — Open-source Agent Skill to help beginners **choose a prop firm**, read rules via **open-page verification**, answer FAQ, and optionally bridge to [Propfirms Drama](https://propfirmsdrama.com/) for Chinese deep-dives. **Not investment advice.** Not affiliated with any proprietary trading firm.

### What this is

A Cursor / Claude / Hermes-compatible [`SKILL.md`](./SKILL.md) plus:

- Firm **URL stubs** (`firms/`) — no locked fees or drawdown numbers
- 21-topic FAQ short answers (`faq/`) — HOW to verify; numbers only at runtime
- PFD topic → URL map (`resources/pfd-map.yaml`)
- Affiliate **example** template (`affiliates.example.yaml`) with mandatory disclosure pattern

### Hard guarantees (agent must follow)

| Rule | Meaning |
|------|---------|
| Open-page verify | Price/rules/payout/geo/promo → `url` + `opened_at` + `saw`; failures use SKILL Failure template |
| Diligence + list methods | Do not bare-label「未能核實」without trying the path; list methods + URLs + `opened_at`, then「以上來源未見公開資料」; never invent numbers |
| Clarify residence first | Without `user_geo` (country/region; user self-report OK), do not conclude “usable / can withdraw”; verify geo eligibility and payout methods for that place; state “assuming user-reported residence = X” |
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
