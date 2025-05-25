# 3. 監控與告警 (Monitoring and Alerting)

## 監控儀表板 (Monitoring Dashboards)

- [主要儀表板連結](http://link.to.dashboard)
- 關鍵效能指標 (KPIs):
    - API 平均回應時間
    - 錯誤率
    - CPU/記憶體使用率

## 告警定義與處理 (Alert Definitions and Handling)

| 告警名稱             | 觸發條件        | 嚴重等級 | 處理步驟                                   |
| -------------------- | --------------- | -------- | ------------------------------------------ |
| High CPU Usage       | CPU > 80% for 5m | Critical | 1. 檢查是否有異常程序 2. 考慮擴展資源       |
| API Error Rate Spike | Error > 5%      | High     | 1. 檢查日誌分析錯誤原因 2. 若為部署引起則回滾 |

## 日誌位置與分析 (Log Locations and Analysis)

- 應用程式日誌: `/var/log/app/app.log`
- 系統日誌: `/var/log/syslog`
- 分析工具: [Kibana連結](http://link.to.kibana) 