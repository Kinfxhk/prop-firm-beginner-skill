# 平台與資料費

期貨常見 NinjaTrader／Tradovate／Rithmic 等；CFD／外匯常見 MT5 等——視產品線而定。  
平台授權、即時行情、額外資料費可能獨立於挑戰費。

## 如何核實（佣金／點差／平台費）

1. 官網首頁 → Help／FAQ 搜尋「platform」「data fee」「commission」「spread」「pricing」。
2. 定價／結帳頁：是否另列平台月費、行情費、啟動費。
3. 平台文件或合作券商頁（若官網有連）：佣金表、點差說明。
4. 記入 Rule Card 欄位 `commissions_spreads_fees`：`url`＋`opened_at`＋`saw`。
5. 適用路徑試盡仍無公開數字 → 用 SKILL **Failure output template**，結論寫「以上來源未見公開資料」；禁止用記憶報價或發明數字。

詳見 PFD: `platforms_data_fees`（見 `resources/pfd-map.yaml`）
