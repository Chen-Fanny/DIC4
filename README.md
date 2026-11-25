# DIC4：overleaf draft for conference using MCP and openspec


## 1. 作業目標

本次作業旨在透過 MCP（Model Context Protocol）與 OpenSpec 建立 AI 輔助學術論文撰寫流程，結合 GitHub 進行專案與規格管理，並使用 Overleaf 完成符合 IEEE Conference 格式的學術論文初稿。

除了利用 AI 協助建立論文架構及撰寫內容之外，也針對生成的論文進行後續檢查、修改與排版調整，使論文更加符合學術會議的撰寫規範。

## 2. 作業要求（Assignment Requirements）

- [x] Overleaf draft for IEEE conference：使用 Overleaf 完成 IEEE 會議論文初稿。
- [x] OpenSpec on GitHub：將 OpenSpec 相關規格與文件上傳至 GitHub。

## 3. 研究主題：Food Guardian

本次論文以 Food Guardian 智慧家庭食材管理系統作為研究主題，主要探討如何結合 AI Agent、Retrieval-Augmented Generation（RAG）及食材庫存管理機制，協助使用者有效管理家庭食材、降低食物浪費，並提供具有食品安全考量的食譜推薦。

系統主要包含以下功能：

- 家庭食材庫存管理。
- 食材有效期限追蹤與提醒。
- 根據現有食材進行食譜推薦。
- 食材數量與單位換算。
- 食品安全判斷與風險篩選。
- 基於 RAG 的食品安全知識查詢。
- AI Agent 工具呼叫與任務處理。
- 食物浪費紀錄與統計分析。

## 4. IEEE Conference 論文撰寫

本次論文以 ICEIB Conference 為目標，透過 Overleaf 與 LaTeX 進行論文撰寫，並採用 IEEE Conference 的雙欄排版格式。

論文內容主要包含以下章節：

1. Abstract（摘要）
2. Introduction（前言）
3. Related Work（相關研究）
4. Proposed Design（提出的方法與系統設計）
5. Experiment（實驗與結果分析）
6. Limitations and Future Work（研究限制與未來工作）
7. Conclusion（結論）
8. References（參考文獻）

透過規格驅動的撰寫方式，使論文內容能夠依照預先設定的研究目標、章節架構與格式要求進行整理。

## 5. 論文版本與修改說明（Paper Revision）

本次作業並非直接將 AI 生成的論文初稿作為最終成果，而是在完成初稿後，進一步檢查論文內容及實際編譯結果，並針對發現的排版問題進行修改。

### 5.1 原始版本與修正版本

| 檔案名稱 | 說明 |
|---|---|
| `main.tex` | 原始 IEEE Conference 論文初稿 |
| `修正.tex` | 以 `main.tex` 為基礎，經過後續修改與排版調整的版本 |

**其中，`修正.tex` 為原始 `main.tex` 修改後的版本，並非另一篇獨立的論文。**

保留兩個版本的目的，是為了呈現論文從原始初稿到後續修正的過程，並方便比較修改前後的排版差異。

### 5.2 主要修改內容

在使用 Overleaf 編譯原始論文後，發現部分內容存在超出 IEEE 雙欄版面範圍的問題，因此進行以下修改：

- 調整表格寬度，避免表格超出頁面範圍。
- 修正 TABLE III 的欄位寬度及文字換行問題。
- 調整表格內的文字對齊方式與欄位間距。
- 將過長的公式拆分為多行，避免超出單一欄位。
- 修正 Related Work 中研究缺口流程的公式排版。
- 修正部分 LaTeX 語法及套件問題。
- 改善論文整體的閱讀性與版面配置。
- 保留原始研究內容、實驗數據及參考文獻。

### 5.3 修正成果

透過上述修改，改善原始論文初稿中的表格與公式溢出問題，使論文版面更加符合 IEEE 雙欄格式的要求。

建議以 `修正.tex` 作為後續閱讀、編譯及持續修改的主要版本，而 `main.tex` 則保留作為原始版本的紀錄。

## 6. OpenSpec 規格管理

本次作業使用 OpenSpec 建立 Specification-Driven Development（SDD，規格驅動開發）的工作流程，將其應用於學術論文撰寫與修改。

在進行論文撰寫前，先定義相關需求、研究方向、章節架構與格式規範，再透過 AI 輔助完成各項撰寫任務。

OpenSpec 的主要用途包含：

- 定義論文撰寫目標與需求
