# 新聞單／隔夜／週末／交易時段

部分計劃限制高影響新聞前後開倉、隔夜或週末持倉；交易時段定義因產品線（期貨 vs CFD）差異大。  
日曆來源、窗口分鐘數、是否強制平倉——一律以官網為準；FAQ **不鎖定**任何數字。

## 如何核實（盡力路徑）

1. 官網 → Help／FAQ 搜尋「news」「overnight」「weekend」「trading hours」「session」。
2. TOS／規則 PDF：trading hours、restricted events、持倉限制。
3. 若有平台／狀態頁說明交易時段，一併開頁記錄。
4. 記入 Rule Card 欄位 `trading_sessions`（及相關 news／overnight 細項）：`url`＋`opened_at`＋`saw`。
5. **未試夠路徑 ≠ 可空口「未能核實」。** 適用路徑試盡仍無 → 列 `methods_tried`＋已開 URL＋`opened_at`，結論「以上來源未見公開資料」（見 `SKILL.md` Failure output template）。

詳見 PFD: `news_overnight_weekend`（見 `resources/pfd-map.yaml`）
