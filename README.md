# prop-firm-beginner-skill

**本說明以繁體中文為準。** English follows below.

**狀態：V0 腳手架（0.1.7）** — 開源 Agent Skill，協助新手**選擇 prop firm**、以**即時開頁核實**查閱規則、回答 FAQ，並可選擇連至 [Propfirms Drama](https://propfirmsdrama.com/) 閱讀繁中長文。**非投資建議。** 與任何 proprietary trading firm 無隸屬關係。

> 如果你的 AI 根本無法解答正確的 Prop firm 資訊，這個可能幫到你。

[English](#english)

## 這是什麼

適用於 Cursor／Claude／Hermes 等環境的 [`SKILL.md`](./SKILL.md)，另附：

- 公司 **URL stub**（`firms/`）— **不鎖定**挑戰費、回撤等數字
- 23 題 FAQ 短答（`faq/`）— 只教如何查；答案仍須 runtime 開頁
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
| 不硬推公司 | 只輸出短名單＋條件對照＋開頁核實卡；禁用「一定要買／唯一推薦／保證通過」；用「可能適合／需自行核實」；本 Skill 非任何 firm 的產品推銷 |

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

- 10 個公司 URL stub、23 題 FAQ；**沒有自動 verify script**，`verify` 是 agent 的開頁程序，不是可執行指令。
- Live／成本 FAQ（22／23）只教查法；不鎖定出金次數門檻，不教爆倉流。
- `resources/pfd-map.yaml` 是模板；`null` 代表未設定，不要發明 PFD URL。
- `firms/*.yaml` 只存 URL 與 product line，不存費用、回撤、利潤目標或出金日數。
- FAQ 以香港用語書寫；SKILL.md 為英文。若你要對外發佈，請自行調整語氣及披露。

## 聯盟／優惠總入口（Linktree）

維護者聯盟／優惠總入口：https://linktr.ee/kinfx

GitHub Sponsors／FUNDING：見 [.github/FUNDING.yml](./.github/FUNDING.yml)。

- 個別 firm 追蹤碼仍用本地 `affiliates.yaml`（由 `affiliates.example.yaml` 複製；**gitignored**），**勿 commit 真碼**。
- 【聯盟披露】該頁部分連結可能為聯盟／推薦連結；經此註冊或付費，維護者可能獲得佣金。使用連結或贊助**不等於**對任何 proprietary trading firm 的推介或背書。規則、價錢、出金以該公司官網為準。**非投資建議。**
- 本 Skill 仍遵守「不硬推公司」硬規則：只輸出短名單＋條件對照＋開頁核實卡。

## 免責

僅供教學／規劃輔助。Prop firm 產品涉及費用及虧損風險。規則經常變更；請以官網即時核實為準。稅務／KYC 說明不構成專業意見。

本 Skill 是**資訊／規劃輔助**，不構成對任何 proprietary trading firm 的推介或背書；運營者若使用 affiliate，自負合規與披露。

## 授權

MIT — 見 [LICENSE](./LICENSE) 及 [NOTICE](./NOTICE)。

---

## English

**The Traditional Chinese section above is authoritative.** English is a parallel summary.

**Status: V0 scaffold (0.1.7)** — Open-source Agent Skill to help beginners **choose a prop firm**, read rules via **open-page verification**, answer FAQ, and optionally bridge to [Propfirms Drama](https://propfirmsdrama.com/) for Chinese deep-dives. **Not investment advice.** Not affiliated with any proprietary trading firm.

> If your AI can't get prop-firm facts right, this may help.

### What this is

A Cursor / Claude / Hermes-compatible [`SKILL.md`](./SKILL.md) plus:

- Firm **URL stubs** (`firms/`) — no locked fees or drawdown numbers
- 23-topic FAQ short answers (`faq/`) — HOW to verify; numbers only at runtime
- PFD topic → URL template (`resources/pfd-map.yaml`)
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
| No hard-sell | Output only shortlist + condition comparison + open-page Rule Cards; forbid “must buy / only recommended / guaranteed pass”; use “may fit / verify yourself”; this Skill is not a product pitch for any firm |

### Install

1. Clone or copy this repo into your agent skills folder (or point the agent at `SKILL.md`).
2. Optionally copy `affiliates.example.yaml` → `affiliates.yaml` and fill **your** links/codes (do not commit).
3. Ask e.g. “我想在香港做期貨 prop，預算有限，請協助短名單並核實規則。”

### Affiliate / promo hub (Linktree)

Maintainer affiliate / promo hub: https://linktr.ee/kinfx

GitHub Sponsors / FUNDING: see [.github/FUNDING.yml](./.github/FUNDING.yml).

- Per-firm tracking codes still live in local `affiliates.yaml` (copied from `affiliates.example.yaml`; **gitignored**) — **do not commit real codes**.
- **Affiliate disclosure:** some links on that page may be affiliate / referral links; the maintainer may earn a commission if you register or pay through them. Using a link or funding **does not** recommend or endorse any proprietary trading firm. Rules and prices are always those on the firm’s official site. **Not investment advice.**
- Hard-sell bans in this Skill still apply: shortlist + condition comparison + open-page Rule Cards only.

### Disclaimer

Educational planning aid only. Prop firm products involve fees and risk of loss. Rules change; always re-verify on the firm’s official site. Tax/KYC notes are not professional advice.

This Skill is an **informational / planning aid** only; it does **not** constitute a recommendation or endorsement of any proprietary trading firm. Operators who use affiliates are solely responsible for disclosure and advertising compliance.

### License

MIT — see [LICENSE](./LICENSE) and [NOTICE](./NOTICE).
