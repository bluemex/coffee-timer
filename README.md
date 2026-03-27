# 手沖職人指南 (Coffee Timer) ☕

### 四六沖法 + 花朵繞法 (Tetsu Kasuya 4:6 Method & Flower Pouring)

🌐 **線上使用：** [coffee-timer.yooneko.com](https://coffee-timer.yooneko.com/)  
📦 **備用連結 (GitHub Pages)：** [bluemex.github.io/coffee-timer/](https://bluemex.github.io/coffee-timer/)

「手沖職人指南」是一個專為咖啡愛好者設計的數位計時輔助工具，隸屬於 [YooNeko](https://yooneko.com/) 平台。結合了著名的 **Tetsu Kasuya 4:6 沖煮法** 與獨特的 **花朵繞法 (Flower Pouring)** 技術，透過視覺化的動態圖表與分段計時，引導使用者精準完成每一階段的萃取。

---

## ✨ 核心功能

*   **4:6 沖煮法邏輯：** 自動將沖煮過程分為五個階段，每段固定 45 秒。
    *   **前兩段 (40%)：** 定調風味，可調整水量比例來強化「酸感」或「甜感」。
    *   **後三段 (60%)：** 調整濃度（TDS）與咖啡主體的厚實度。
*   **動態 SVG 視覺引導：** 每個階段配有專屬的動態圖解（如中心注水、花瓣式繞圈、動力對流繞法），即時顯示注水路徑。
*   **智慧自動捲動：** 隨著計時進行，畫面會自動平滑捲動至當前進行中的沖煮階段，方便使用者空出雙手專注注水。
*   **內建快速預設：** 提供兩組標準參數：
    *   **300ml (標準)：** 使用 20g 咖啡粉。
    *   **600ml (大分量)：** 使用 35g 咖啡粉。
*   **即時職人語錄：** 沖煮過程中隨機顯示激勵語錄，提升沖煮過程的儀式感。
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

### 部署至 Firebase
```bash
cd coffee-timer
firebase deploy --only hosting
```

---

## 📂 專案結構

```
coffee-timer/
├── public/              # 靜態檔案目錄
│   ├── index.html       # 核心 SPA (React + Tailwind + 邏輯)
│   └── favicon.png      # 網站圖示 & App Icon
├── .firebaserc          # Firebase 專案配置
├── firebase.json        # Firebase Hosting 與 Redirects 配置
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
