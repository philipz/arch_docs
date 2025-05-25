# 6. 緊急應變計畫 (Emergency Response Plan)

## 聯絡人清單 (Contact List / Escalation Path)

| 角色             | 姓名     | 電話         | Email             |
| ---------------- | -------- | ------------ | ----------------- |
| 主要維運工程師   | 王大明   | 0912-345-678 | daming@example.com |
| 備援維運工程師   | 李小美   | 0922-333-444 | hsiaomei@example.com |
| 開發團隊負責人   | 陳志強   | 0933-111-222 | chihchiang@example.com |
| 技術主管         | 林經理   | 0988-777-666 | manager.lin@example.com |

**升級路徑:**
1. 主要維運工程師
2. 備援維運工程師 (若主要無法聯繫或30分鐘未解決)
3. 開發團隊負責人 (若需程式碼層級協助)
4. 技術主管 (若影響範圍擴大或需跨部門協調)

## 災難復原計畫 (Disaster Recovery Plan)

- **RPO (Recovery Point Objective):** 1 小時
- **RTO (Recovery Time Objective):** 4 小時
- **步驟:**
    1. 確認主要資料中心服務中斷。
    2. 啟動備援資料中心的災難復原腳本。
    3. 將 DNS 指向備援資料中心。
    4. 驗證服務是否正常運作。
    5. 持續監控並準備主要資料中心恢復後的切回作業。

## 溝通協調計畫 (Communication Plan)

- **內部溝通:** 
    - 使用 Slack #emergency 頻道即時更新狀況。
    - 每30分鐘向相關人員發送 Email 彙報進度。
- **外部溝通 (若影響客戶):**
    - 由客服團隊透過公告系統發布服務中斷通知。
    - 定期更新狀態，直到服務恢復。 