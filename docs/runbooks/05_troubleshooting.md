# 5. 故障排除 (Troubleshooting)

## 常見問題與解決方案 (Common Issues and Solutions / FAQ)

- **問題:** 使用者回報無法登入。
    - **可能原因:** 
        1. 認證服務異常。
        2. 資料庫連線問題。
        3. 使用者帳號被鎖定。
    - **解決步驟:** 
        1. 檢查認證服務狀態及日誌。
        2. 檢查資料庫連線池狀態。
        3. 確認使用者帳號狀態。

- **問題:** API 回應緩慢。
    - **可能原因:** 
        1. 後端依賴服務緩慢。
        2. 資料庫查詢效率低。
        3. 應用程式資源不足 (CPU/Memory)。
    - **解決步驟:** 
        1. 使用追蹤工具 (e.g., Jaeger) 分析請求鏈路。
        2. 檢查慢查詢日誌。
        3. 監控應用程式資源使用率。

## 故障排除流程圖 (Troubleshooting Flowcharts)

(此處可嵌入流程圖圖片或連結)

- [範例：服務無法存取排除流程](link.to.flowchart.image)

## 診斷工具 (Diagnostic Tools)

- `ping`, `traceroute`: 網路連線測試。
- `netstat`, `ss`: 查看網路連線狀態。
- `top`, `htop`: 系統資源監控。
- `kubectl logs <pod_name>`: 查看 Kubernetes Pod 日誌。
- `curl`, Postman: API 接口測試。 