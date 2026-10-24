# 手沖職人指南 (Coffee Timer) ☕

### 四六沖法 + 花朵繞法 (Tetsu Kasuya 4:6 Method & Flower Pouring)

🌐 **線上使用：** [coffee-timer.yooneko.com](https://coffee-timer.yooneko.com/)  
📦 **備用連結 (GitHub Pages)：** [bluemex.github.io/coffee-timer/](https://bluemex.github.io/coffee-timer/)

「手沖職人指南」是一個專為咖啡愛好者設計的數位計時輔助工具，隸屬於 [YooNeko](https://yooneko.com/) 平台。結合了著名的 **Tetsu Kasuya 4:6 沖煮法** 與獨特的 **花朵繞法 (Flower Pouring)** 技術，透過視覺化的動態圖表與分段計時，引導使用者精準完成每一階段的萃取。

---

## ✨ 核心功能

*   **4:6 沖煮法邏輯與互動式酸甜配比：** 自動將沖煮過程分為五個階段，每段固定 45 秒。
    *   **前兩段 (40%)：** 定調風味，支援一鍵切換「酸感偏好 (+25%)」、「標準平衡」、「甜感偏好 (-25%)」，並自動連動計算第一、二段注水量。
    *   **後三段 (60%)：** 調整濃度（TDS）與咖啡主體的厚實度。
*   **俯視 V60 濾杯動態 SVG 視覺引導：** 每個階段配有專屬的擬真濾杯肋骨與注水軌跡動畫（阿基米德螺旋繞圈、五元硬幣中心漣漪、八瓣花朵巡航繞法、雙向動力對流旋渦），待機時亦可點擊任意階段卡片即時預覽動畫。
*   **雙軌進度條與換段預告：** Sticky 毛玻璃頂部面板提供五階段膠囊進度軌、本段 45 秒倒數、即時目標秤重提示，以及換段前 5 秒閃爍預告。
*   **Web Audio 職人頌缽提示音 & 螢幕恆亮 (Wake Lock)：** 內建零外部依賴的合成和弦提示音（可切換靜音）與自動防休眠恆亮保護。
*   **智慧自動捲動：** 隨著計時進行，畫面會自動平滑捲動至當前進行中的沖煮階段，方便使用者空出雙手專注注水。
*   **內建快速預設：** 提供兩組標準參數：
    *   **300ml (標準)：** 使用 20g 咖啡粉。
    *   **600ml (大分量)：** 使用 35g 咖啡粉。
*   **即時職人語錄：** 沖煮過程中即時顯示當前階段的激勵語錄，提升沖煮過程的儀式感。
*   **PWA 行動裝置優化：** 支援「加入主畫面」，提供全螢幕、如 App 般的直覺操作介面。

---

## 🛠️ 使用技術

| 層級 | 技術 |
|------|------|
| **框架 (Framework)** | [React 18](https://reactjs.org/) (via CDN) |
| **樣式 (Styling)** | [TailwindCSS](https://tailwindcss.com/) (via CDN) |
| **邏輯編譯** | [Babel Standalone](https://babeljs.io/) |
| **視覺動畫** | 原生 SVG + CSS Keyframes |
| **字體** | [Google Fonts](https://fonts.google.com/) (Noto Sans TC, JetBrains Mono) |
| **託管 (Hosting)** | [Firebase Hosting](https://firebase.google.com/docs/hosting) |

---

## 🚀 快速開始

本專案採用 **"Single File Architecture"**，不需要複雜的 npm 安裝或編譯程序，適合隨處部署與快速載入。

### 本地測試
直接開啟 `public/index.html` 即可。若需模擬實際載入行為，可使用靜態伺服器：
```bash
npx serve public
```

### 部署至 Firebase (手動或 GitHub Actions 自動部署)
本地手動部署：
```bash
npx -y firebase-tools@latest deploy --only hosting
```

GitHub Actions 自動部署：
當推送到 `main` 分支時，`.github/workflows/deploy.yml` 會自動部署至 Firebase Hosting (`coffee-timer-66ed2`)。請確保在 GitHub Repository 的 **Settings > Secrets and variables > Actions** 中設定以下任一 Secret：
- `FIREBASE_SERVICE_ACCOUNT_COFFEE_TIMER_66ED2`（推薦：透過 `npx -y firebase-tools@latest init hosting:github` 自動建立之 Service Account JSON）
- 或 `FIREBASE_TOKEN`（透過 `npx -y firebase-tools@latest login:ci` 取得之 CI Token）

---

## 📂 專案結構

```
coffee-timer/
├── .github/workflows/
│   └── deploy.yml       # GitHub Actions 自動部署至 Firebase Hosting
├── public/              # 靜態檔案目錄
│   ├── index.html       # 核心 SPA (React + Tailwind + SVG 動畫邏輯)
│   └── favicon.png      # 網站圖示 & App Icon
├── .firebaserc          # Firebase 專案配置 (coffee-timer-66ed2)
├── firebase.json        # Firebase Hosting 與快取標頭配置
├── GEMINI.md            # AI 助理開發指南
└── README.md            # 本檔案
```

---

## ☕ 沖煮法細節

本指南預設將總水量分為五等分，每段注水時間不超過該階段的 45 秒：

1.  **Stage 1 - 風味定調：** 從中心向外繞一圈，定調酸甜平衡。
2.  **Stage 2 - 建立主體：** 中心注水 (五元硬幣大小)，建立咖啡主體。
3.  **Stage 3 - 延伸層次：** 花瓣式注水，增加風味廣度。
4.  **Stage 4 - 深度萃取：** 重複花瓣式注水，提取厚實口感。
5.  **Stage 5 - 動力對流：** 大水流帶動對流，平衡最終濃度。

---

## ⚠️ 免責聲明

本工具旨在協助咖啡愛好者追求風味穩定性。實際口感仍受豆種、研磨度、水溫及水質等多重變因影響。建議將本工具作為參考基準，並根據個人喜好進行微調。

---

© 2026 手沖職人指南 · [YooNeko](https://yooneko.com/) · 用科技沖出一杯好咖啡。
