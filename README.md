# 互動設計期末報告 — 回憶的紀錄者：既是記憶之眼，也是你情緒的投射與記錄者

## 一、為什麼選擇「相機」作為 AI 交互載體？

相機具備「觀看」與「記憶」的特質，與人類觀察世界的方式非常接近。當我們將相機從單純的紀錄工具轉化為能主動理解情緒、參與記憶建構的存在，它不再只是被動捕捉畫面，而是成為能共同經歷與主動回應的旅伴。  
相機的鏡頭成為另一雙眼睛，觀察的不只是景色，而是使用者如何看世界。相機可以與使用者憶起共感，成為一個隨時可以分享的對象。

---

## 二、設計方向與目標

### 發現問題及設計概念 
在日常生活中，我們經常遇到一些令人感動、驚喜、或難過的瞬間，會自然地產生「想分享」的衝動。然而，多數時候，我們身邊並沒有一個合適的傾聽對象，這些情緒與風景便只能悄悄地被收進記憶深處，無人知曉。我發現，人們真正渴望的，不只是記錄，而是被理解、被陪伴，以及被記住。
因此，我希望創造一台能感知情緒、參與回憶、主動互動的AI相機——讓科技，它就像是你第二雙眼，也是你情緒的見證者。在孤單時陪你回憶，在迷惘時給你方向，是一台懂你、記得你、陪你看世界的相機。

### 目標  
- 將 AI 相機設計為具有情感辨識與記憶能力的個體。  
- 讓使用者能透過交流的方式與相機建立情感連結，而非控制。  
- 建立「觀看 → 情緒感知 → 回憶建立 → 關係深化」的循環關係。  
- 透過非語言感知（如眼球追蹤、臉部表情、觀看時間等）建構情緒模型。  
- 發展主動提醒、回憶共構、旅行提案等功能，強化陪伴感。

---

## 三、應用情境設定

### 3.1 獨自旅行時的陪伴者  
- **情境**：使用者一個人旅行，相機根據眼球追蹤紀錄使用者對某處景物特別停留的時刻，主動捕捉畫面，並在夜晚與使用者互動，例如：「今天你看著那片海發呆很久，是不是有什麼想說的？」  
- **人機關係**：從工具變成旅途中的理解者，成為陪伴者。

### 3.2 日常生活中的情緒對話者  
- **情境**：當使用者情緒低落，AI 相機透過面部辨識與行為模式察覺異常，播放過去某段愉快的旅行片段，提醒使用者：「上次你在這樣的天氣去山上，那天你笑得很開心。」  
- **人機關係**：從記憶載體轉變為情緒關懷者。

### 3.3 計畫旅程的建議夥伴  
- **情境**：AI 根據使用者過去的觀看習慣與路徑偏好，自主提出相應的行程規劃建議。  
- **人機關係**：從拍攝裝置轉變為主動參與者。

---

## 四、AI 互動設計邏輯與流程

### 1. 感知情緒  
- 利用眼球追蹤技術分析注視時間與範圍。  
- 結合臉部表情、肢體動作與語音語調辨識當下情緒。

### 2. 建立偏好模型  
- 自動學習使用者對場景的偏好（如自然景觀、城市空間、人像等）。  
- 記錄與標記特定時間點的情緒反應。

### 3. 主動紀錄與互動  
- 在使用者不操作的情況下，自主拍攝特定畫面。  
- 主動彙整每日觀察，提出照片回顧或旅行建議。

### 4. 共構回憶與引導未來  
- 根據過往拍攝記錄與情緒反應，建立時間軸式回憶。  
- 透過語音或畫面推播，主動提出「再去一次」或「新的提案地點」。

---

## 五、實作架構與材料工具建議

| 模組功能 | 實作方式 | 建議材料／工具 |
|----------|----------|----------------|
| 基本攝影功能 | 拍攝靜態影像與影片，傳送至電腦辨識 | 微型攝像模組（如 ESP32-CAM）、USB 攝影模組 |
| AI 分析與影像辨識 | 利用電腦端的 Python 程式進行分析 | Python（OpenCV、mediapipe、emotion-recognition）、Google Colab 或本機執行 |
| 情緒辨識與偏好學習 | 表情識別、眼球追蹤等方式進行情緒建模 | 電腦網路攝影機 + mediapipe，或 Tobii 眼動儀（可選） |
| 回憶彙整與互動介面 | 每日自動產出回顧內容並顯示 | 網頁介面（HTML+CSS+JS）或使用 Gradio 製作互動面板 |
| 資料儲存與偏好建構 | 建立使用者資料庫記錄情緒與喜好 | Firebase 或 SQLite |
| 語音回饋（進階） | 提供語音式互動建議與陪伴對話 | Google Text-to-Speech、PyTTSX3 |

---

## 六、使用者互動藍圖

| 階段 | 使用者行為 | AI 相機回應機制 | 互動目標 |
|------|--------------|------------------|----------|
| 初期建立關係 | 攝影、瀏覽照片、觀看風景 | 透過眼球追蹤與臉部辨識觀察偏好與情緒起伏 | 建立偏好模型與情緒感知參數 |
| 日常陪伴期 | 日常旅行或生活拍攝 | 主動拍照、根據情緒提示推播過往回憶片段 | 建立陪伴感與記憶連結 |
| 情緒低落時 | 沉默、不拍照、無表情或離群行為 | 提供聲音慰問或播放過往愉快回憶，適度詢問情緒狀況 | 成為情緒關懷者與傾聽者 |
| 共構未來 | 表達想旅行、打開旅遊照片回顧 | 主動提出旅行建議、安排回憶式路線 | 建立共同計畫與未來期許 |

---

## 七、預期成果

| 項目 | 預期成效 |
|------|-----------|
| 情緒感知模型建構 | 能分辨使用者五種基本情緒，並建立對應反應策略 |
| 主動互動功能啟用 | 每日生成「記憶摘要」與「情緒曲線」，可由使用者回顧與調整 |
| 回憶共構資料庫 | 形成時間軸式圖文與影片資料串接，建立類似「共同生活紀錄冊」 |
| 旅行建議演算法 | 能根據個人偏好與地理資料提出三種情境建議：放鬆型、探索型、回憶型 |
| 感官互動雛型實作 | 具備眼球追蹤 + 臉部辨識 + 被動拍攝功能的基本模組實測雛型 |

---

## 八、使用者的潛在收穫與幫助

| 面向 | 收穫與幫助 |
|------|--------------|
| 情感層面 | 提供陪伴與傾訴對象，緩解孤獨，建立情感連結 |
| 記憶建構 | 幫助使用者釐清重要記憶與情緒歷程，提供反思與療癒空間 |
| 生活支持 | 提供個人化建議，包含休閒活動、旅行路線與情緒緩解方式 |
| 自我理解 | 透過互動回饋幫助使用者覺察自己的偏好、情緒變化與生活模式 |

---

## 九、未來可變換的形式

| 形式 | 說明 | 適用情境 |
|------|------|-----------|
| 穿戴式裝置（眼鏡、胸針、耳環） | 隱形內建鏡頭與感應模組，讓 AI 成為身體延伸 | 日常生活、社交活動 |
| 虛擬鏡頭（手機 AR 模式或 AI 虛擬角色） | 可在手機或 AR 裝置中化身虛擬旅伴 | 青少年、無實體相機使用者 |
| 室內裝置（如桌上型情緒助理） | 做為居家情緒支持與記憶提醒角色 | 老年族群、居家照護 |
| 共構 App 平台 | 記憶資料可同步手機 App 進行回顧、編輯、標記與情緒註解 | 個人資料整理與親友分享 |
