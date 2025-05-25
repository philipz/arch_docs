# 4. 維運程序 (Operational Procedures)

## 啟動與停止程序 (Startup and Shutdown Procedures)

- **啟動服務:** `systemctl start my-app.service`
- **停止服務:** `systemctl stop my-app.service`
- **檢查服務狀態:** `systemctl status my-app.service`

## 備份與還原 (Backup and Restore Procedures)

- **備份策略:** 每日凌晨2點進行完整資料庫備份，保留最近7天份。
- **還原步驟:** 
    1. 從備份儲存中取得最新的備份檔案。
    2. 停止應用程式服務。
    3. 執行資料庫還原指令: `pg_restore -d mydb latest_backup.dump`
    4. 啟動應用程式服務。

## 例行維護任務 (Routine Maintenance Tasks)

- **每週一:** 清理過期日誌檔案。
- **每月一日:** 資料庫索引重建。

## 擴展與縮減 (Scaling Procedures)

- **手動擴展:** 
    1. 登入 Kubernetes 主控台。
    2. 調整 Deployment 的副本數量。
- **自動擴展:** 基於 CPU 使用率的 HPA (Horizontal Pod Autoscaler) 已設定。 