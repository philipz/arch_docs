# 8. 服務等級協議 (Service Level Agreements - SLAs)

## 系統可用性 (System Availability)

- **目標:** 99.95% (每月)
- **計算方式:** (總時間 - 停機時間) / 總時間 * 100%
- **排除事項:** 計畫性維護 (需提前通知)、第三方服務中斷。

## 效能指標 (Performance Metrics)

- **API 平均回應時間:** 
    - 核心 API: < 200ms (P95)
    - 一般 API: < 500ms (P95)
- **頁面載入時間 (Web):** 
    - 首次內容繪製 (FCP): < 2秒
    - 最大內容繪製 (LCP): < 4秒

## 維護窗口 (Maintenance Window)

- **計畫性維護時間:** 每月第一個星期日的凌晨 02:00 - 04:00 (UTC+8)。
- **通知方式:** 維護前 72 小時透過 Email 及系統公告通知客戶。

## SLA 未達成之後果 (Consequences of not meeting SLA)

- (此部分需根據公司政策或與客戶的合約具體定義，例如服務積分、補償方案等)
- 範例：若當月可用性低於 99.9%，將提供 5% 的服務費用減免。

## 報告與檢視 (Reporting and Review)

- 每月產生 SLA 達成率報告。
- 每季進行 SLA 目標及實際達成情況檢討會議。 