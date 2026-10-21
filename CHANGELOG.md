# Changelog

## 0.1.6 — README：Linktree 與 FUNDING 拆兩行（避免 GitHub 渲染黏連）

- README（繁中＋英文）：第一行只寫 Linktree；第二行另起 GitHub Sponsors／FUNDING 連結（唔用 `_…_` 包住）
- 修復「聯盟／優惠總入口」一行內 linktr.ee 與 `.github/FUNDING.yml` 渲染像連埋

## 0.1.5 — FUNDING/README → linktr.ee/kinfx (drop BMC placeholder)

- `.github/FUNDING.yml`: `custom: ["https://linktr.ee/kinfx"]`；移除 `buy_me_a_coffee` 佔位
- README（繁中＋英文）：贊助段改聯盟／優惠總入口；個別 firm 追蹤碼仍用本地 `affiliates.yaml`（gitignored）
- `affiliates.example.yaml`: 註解說明 linktr 為公開總入口；空 link／code 不變
- 披露：頁上部分連結可能為聯盟連結；≠ firm 推介／背書；非投資建議

## 0.1.4 — Legal tone gate (no hard-sell; info/planning aid; FAQ18 risk-first; NOTICE/README; tier ≠ buy advice)

- SKILL.md: hard rule 12 no hard-sell / no sole recommendation; description「not a solicitation」; workflow shortlist+Rule Cards only; out-of-scope hard-sell
- FAQ 18: risk disclosure first; 非投資／非金融建議; agent forbid「應該買 X」; index title 風險優先
- README／NOTICE: info/planning aid; no endorsement; operator affiliate compliance; hard-rules「唔硬推公司」
- `references/methodology-tier.md`: 非官方評級；≠ buy recommendation；V0 no scored rankings


## 0.1.3 — Live Funded FAQ + multi-account cost/EV HOW-TO; payout Live-trigger sentence; required field live_funded_transition

- SKILL.md: required-attempt `live_funded_transition`; out-of-scope strategy/ICT/backtest + blowup farming; FAQ routing notes 22/23
- FAQ 22 Live Funded／真倉過渡；FAQ 23 多帳戶成本／EV 查法（無鎖定數字、拒爆倉流）
- FAQ 08：出金次數／Live 觸發須跟官方；FAQ 07 交叉連結
- `references/output-schemas.md` + coverage matrix → 0.1.3；`pfd-map` keys；README FAQ 23

## 0.1.2 — user_geo residence gate

- SKILL.md: hard rule `user_geo` gate before usability / payout conclusions; questionnaire requires residence first; Rule Card fields `geo_eligibility` + `payout_methods_for_geo`
- `references/output-schemas.md` + coverage matrix aligned
- FAQ 08／09: user_geo-first flow; HK as example only
- README: hard-rules row「先釐清居住地」(EN parallel)

## 0.1.1 — Diligence verify + required fields

- SKILL.md: diligence verify path, failure output template (no bare「未能核實」), required-attempt Rule Card fields (VPN/VPS, hedging, penalties, sessions, commissions/spreads/fees)
- `references/output-schemas.md` + coverage matrix aligned
- FAQ: strengthen 10/11/12/15 HOW-TO routes; add 19 VPN/VPS、20 hedging、21 commissions/spreads (21 topics); index + pfd-map keys
- README: hard-rules row「盡力查＋列方法」(EN parallel)

## 0.1.0 — V0 scaffold

- Initial Agent Skill: SKILL.md (open-page verify, Rule Card schema, hard rules)
- 10 firm URL stubs + `_template.yaml`
- FAQ 18-topic short answers + `resources/pfd-map.yaml`
- MIT + NOTICE + FUNDING.yml placeholder + `affiliates.example.yaml`
