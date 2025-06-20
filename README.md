展示如何用 Mermaid 和 PlantUML 實現 C4 Model 的各層架構圖：

## 補充說明和最佳實務

### 工具選擇建議

**Mermaid 適用場景**：
- 團隊剛開始導入架構圖文檔化
- 需要快速在 GitHub/GitLab 中展示
- 架構相對簡單的系統
- 重視工具的輕量化和易用性

**PlantUML 適用場景**：
- 需要完整的 C4 Model 支援
- 複雜的企業級系統架構
- 需要高度客製化的圖表樣式
- 已有完善的 CI/CD 流程整合

### 企業導入策略

**階段性導入**：
1. **第一階段**：從 System Context 開始，讓團隊熟悉語法
2. **第二階段**：加入 Container 圖，建立服務邊界共識
3. **第三階段**：針對關鍵模組建立 Component 圖
4. **第四階段**：補充部署和運營相關架構圖

**標準化建議**：
- 建立統一的命名規範和顏色配置
- 設定 Git Hooks 確保圖表可正常渲染
- 整合到 CI/CD 自動生成 PDF 和圖片格式
- 定期 Review 確保架構圖與實際系統同步

**常見陷阱避免**：
- 避免過度細節化，每層圖表要保持適當抽象層級
- 避免一次建立所有圖表，應該漸進式完善
- 避免只有架構師維護，應該讓開發團隊共同參與

這種方式能讓架構圖真正成為團隊溝通的共同語言，而不只是文檔庫中的靜態資料。