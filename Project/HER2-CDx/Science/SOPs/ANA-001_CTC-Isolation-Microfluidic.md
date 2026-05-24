# ANA-001：CTC 捕獲流程——生物素化抗體懸液預標記 + SA 微流道捕獲
## CTC Isolation: Antibody Pre-labeling in Suspension + Streptavidin Microfluidic Capture

**文件編號**：ANA-001  
**版本**：Draft v1.1（工作草稿）  
**日期**：2026-05-23  
**狀態**：⚠️ Working Draft — 以下參數已由 RD 文件初步填入，待對應驗證實驗最終確認後升版：
- 抗體濃度（5 μg/mL each，20 μL cocktail / 4 mL）→ Phase 1 P1-Test 1 最佳化確認
- 捕獲流速（Q_std = 1.5 mL/min）→ Phase 2 Exp 5A 範圍驗證
- 洗滌條件（Q_wash = 2.0 mL/min × 5 mL × 3 washes）→ Phase 2 Exp 5A/5B 確認
- 洗滌 pH 允許範圍 → Phase 2 Exp 5B
- 抗體 Lot 批間差規格（CV 限制）→ Phase 2 Exp 1

**格式**：CLSI QMS02

**v1.1 修訂摘要**：  
⚠️ **重大修訂**——捕獲機制完全重新設計。由 v1.0 的「抗體晶片預包覆法（antibody-coated chip）」改為「懸液抗體預標記法（antibody pre-labeling in suspension）」：生物素化抗體先在細胞懸液中（RT, 30 min, 10–15 rpm）與 CTC 結合，標記後的細胞再流過 Streptavidin 晶片被捕獲。同步新增 40 μm 過濾步驟、更新緩衝液配方（PBS + 2% BSA + 2 mM EDTA）。

---

## 1. 目的（Purpose）

本 SOP 定義從 PBMC 懸液（來自 PRE-004）中免疫捕獲 CTC 的標準操作流程，提供進入 IF 染色（ANA-004）的 CTC-loaded 裝置。

**捕獲策略（Antibody Pre-labeling in Suspension）**：
1. 三種生物素化抗體（Anti-EpCAM + Anti-HER2 + Anti-EGFR cocktail）在細胞懸液中與 CTC 表面抗原結合（RT 旋轉孵育 30 min）
2. 表面帶有生物素化抗體的細胞懸液，經 40 μm 過濾去除聚集塊後，流過 Streptavidin（SA）包覆的微流道裝置
3. 生物素化 CTC 透過 Biotin–Streptavidin 鍵結（Kd ≈ 10⁻¹⁵ M）固定在裝置表面
4. 無抗原標記的 CD45+ 淋巴球和單核球不被保留，隨洗滌緩衝液流出

> **與傳統晶片包覆法的差異**：懸液預標記讓抗體在 3D 溶液環境中充分接觸細胞，比抗體固定在 2D 平面上的靜態捕獲效率更高。

---

## 2. 適用範圍（Scope）

- 輸入：來自 PRE-004 的 PBMC 懸液（體積 ≈ 4.0 mL，以運行緩衝液 PBS + 2% BSA + 2 mM EDTA 重懸）
- 輸出：含 CTC 的捕獲裝置，移交 ANA-004 IF 染色
- 不適用於：直接全血輸入；已過窗口 B 等待時間的 PBMC 懸液

---

## 3. 職責（Responsibilities）

| 職責 | 人員 |
|------|------|
| 抗體孵育與捕獲操作 | 通過本步驟資格認證的技術員 |
| QC 對照品操作（陽性 / 陰性）| 同上 |
| 裝置 QC 目視確認 | 操作者本人 |
| 記錄審核 | Technical Supervisor |
| 異常決策（如流速異常、QC 失敗）| Technical Supervisor |

---

## 4. 安全（Safety）

- PBMC 懸液含人類細胞成分，視同血液性病原體，BSL-2 操作
- PPE：手套、防水實驗衣
- 抗體試劑（蛋白質）：一般化學廢棄處理；避免殘留在皮膚上
- 微流道裝置：若有尖銳邊緣，取用時戴厚手套
- 廢液（流過的細胞懸液）：含人類細胞成分，依生物危害廢棄物處理

---

## 5. 原理（Principle）

### 5.1 捕獲抗體策略

本平台採用三抗體 cocktail，覆蓋不同 EpCAM 表現量的 CTC：

| 抗體 | 靶標 | 功能 | 來源 |
|------|------|------|------|
| Biotinylated Anti-EpCAM | EpCAM | 主力捕獲：高表現於上皮型 CTC（MCF-7、SK-BR-3）| R&D Systems, BAF960 |
| Biotinylated Anti-HER2 | HER2/ErbB2 | 直接靶向：HER2+ CTC 的補強捕獲 | R&D Systems, BAF1129 |
| Biotinylated Anti-EGFR | EGFR/ErbB1 | 補捉：EpCAM-low / EMT 中間型 CTC | R&D Systems, BAF231 |

> **設計邏輯**：三抗體 cocktail 相較於單一 Anti-EpCAM，能補捉 EMT 過程中 EpCAM 下調但 EGFR 或 HER2 仍維持表現的 CTC，提高靈敏度（Exp 2 需驗證 EGFR 不增加 WBC 非特異結合）。

### 5.2 預標記捕獲機制

```
生物素化抗體 cocktail（20 μL）
        ↓ 加入 4 mL PBMC 懸液（各抗體終濃度 5 μg/mL）
在懸液中孵育（RT，30 min，10–15 rpm 旋轉）
        ↓ 抗體與 CTC 表面抗原（EpCAM / HER2 / EGFR）結合
生物素化 CTC（表面帶 Biotin-Ab）
        ↓ 40 μm 過濾（去除聚集塊）
以 Q_std = 1.5 mL/min 流過 Streptavidin 晶片
        ↓ Biotin-Streptavidin 鍵結（Kd ≈ 10⁻¹⁵ M）
CTC 被捕獲固定在裝置表面

CD45+ 淋巴球 / 單核球（無 EpCAM/HER2/EGFR）
→ 不被抗體標記 → 隨洗滌流出
```

---

## 6. 設備（Equipment）

| 設備 | 規格 | 用途 |
|------|------|------|
| 微流道/濾器捕獲裝置（SA 包覆）| 自建（依 ANA-002 規格）| CTC 捕獲基材 |
| 注射泵（Syringe Pump）| 精度 ±5% 流速 | 控制流速（Q_std = 1.5 mL/min, Q_wash = 2.0 mL/min）|
| 管架旋轉混合器（Tube Rotator / Rotisserie）| 10–15 rpm，可控速 | 抗體孵育期間持續翻轉細胞懸液 |
| 40 μm 細胞篩網（Cell Strainer）| Nylon，滅菌，15 mL 管配套 | 過濾細胞聚集塊，防止晶片堵塞 |
| 生物安全操作台（BSC）Class II | — | 所有開管操作 |
| 倒置顯微鏡 | 10×–20× | 裝置目視 QC |
| 計時器 | — | 孵育時間控制 |
| 4°C 冰箱 | — | 抗體試劑保存 |

---

## 7. 試劑與耗材（Reagents & Materials）

### 7.1 捕獲抗體 Cocktail

| 試劑 | Catalog # | 保存 | Cocktail 股濃度（目標）| 加入 4 mL 後終濃度 |
|------|-----------|------|----------------------|-------------------|
| Biotinylated Anti-Human EpCAM | R&D BAF960 | -20°C | ~1 mg/mL | 5 μg/mL |
| Biotinylated Anti-Human HER2 | R&D BAF1129 | -20°C | ~1 mg/mL | 5 μg/mL |
| Biotinylated Anti-Human EGFR | R&D BAF231 | -20°C | ~1 mg/mL | 5 μg/mL |

> **Cocktail 配製邏輯**：三種抗體等濃混合預配為 cocktail stock（各約 1 mg/mL），每次取 20 μL 加入 4 mL 懸液（1:200 稀釋），終濃度各 5 μg/mL。詳細批次配製與效期管理見 ANA-005（抗體管理 SOP）。

### 7.2 緩衝液與耗材

| 試劑 | 規格 / 配方 | 用途 |
|------|------------|------|
| 運行緩衝液（Running Buffer）| 1× PBS（無鈣鎂）+ 2% BSA + 2 mM EDTA，pH 7.4，0.22 μm 過濾，4°C 保存 | 細胞懸液基質（PRE-004 重懸用）、抗體孵育基質、晶片預濕、洗滌 |
| Streptavidin-coated 捕獲裝置 | 自建（依 ANA-002）| CTC 捕獲基材 |
| 40 μm 細胞篩網（Cell Strainer）| Nylon，滅菌，15 mL 管配套 | 捕獲前過濾 |
| 注射器 | 5 mL 或 10 mL，滅菌 | 細胞懸液上機 |

---

## 8. 操作步驟（Procedure）

> **流程概覽**：
> ```
> 8.0 SA 晶片確認（可與 8.1 平行）
>         ↓
> 8.1 抗體預孵育（30 min，RT，10–15 rpm）
>         ↓
> 8.2 40 μm 過濾
>         ↓
> 8.3 SA 晶片捕獲（Q_std = 1.5 mL/min）
>         ↓
> 8.4 洗滌（Q_wash = 2.0 mL/min × 5 mL × 3 次）
>         ↓
> 8.5 裝置目視 QC → 8.6 移交 ANA-004
> ```

---

### 8.0 捕獲裝置確認（SA 晶片）

> 可在接收 PBMC 懸液前或抗體孵育進行中同步完成。

1. 取出 Streptavidin-coated 捕獲裝置，確認 Lot # 在 ANA-002 有效名單內
2. 以運行緩衝液預濕晶片：以低流速（~0.5 mL/min）推入 1.0 mL，確認流道通暢、無氣泡、無漏液
3. 記錄裝置 Lot # 和預濕確認於 Form ANA-001-F1

---

### 8.1 抗體預孵育（Antibody Pre-labeling in Suspension）

> **時機**：收到 PRE-004 的 PBMC 懸液後立即開始。孵育 30 min 為此步驟的速率決定步驟。

4. 收到 PBMC 懸液，核對 Form PRE-004-F1：確認活性 ≥ 85%，窗口 B 時間符合規定
5. 確認懸液體積 ≈ 4.0 mL（以運行緩衝液 PBS + 2% BSA + 2 mM EDTA 重懸）；若不足，補至 4.0 mL
6. 從 -20°C 取出抗體 cocktail，冰上解凍（4°C），確認 Lot #
7. 取 **20 μL** 生物素化抗體 cocktail，加入 4.0 mL PBMC 懸液（各抗體終濃度：**5 μg/mL each**）
8. 以移液管輕柔混勻（吸放 5 次，勿震盪）
9. 置於旋轉混合器（Tube Rotator）：
   - 轉速：**10–15 rpm**（輕柔持續翻轉）
   - 溫度：**室溫（18–22°C）**
   - 時間：**30 分鐘**（全程保持轉動，細胞懸液不得靜置）
10. 孵育完成後立即進入步驟 8.2
11. 記錄孵育開始和完成時間於 Form ANA-001-F1

> **注意**：孵育後無需洗去游離抗體。游離抗體體積（20 μL / 4 mL）極小，對 SA 晶片的非特異性競爭影響可忽略。

---

### 8.2 40 μm 過濾（Cell Aggregate Removal）

> 去除孵育過程中形成的細胞聚集塊，防止堵塞微流道。

12. 將滅菌 40 μm 細胞篩網置於 15 mL 錐形管上
13. 緩慢將抗體標記後的 PBMC 懸液（4 mL）倒入篩網（可輕拍篩網邊緣，勿強力下壓）
14. 收集濾液至注射器，排除氣泡
15. 記錄過濾異常情況（如篩網阻塞）於 Form ANA-001-F1

---

### 8.3 SA 晶片捕獲（Biotin-CTC Capture on Streptavidin Chip）

> 生物素化 CTC 透過 Biotin-SA 鍵結固定在晶片表面；未標記的 CD45+ WBC 隨流出液去除。

16. 確認注射泵設定：
    - 流速：**Q_std = 1.5 mL/min**（允許範圍：1.35–1.65 mL/min，±10%）
    - 記錄設定值於 Form ANA-001-F1
17. 連接注射器至捕獲裝置入口，啟動泵
18. 以 Q_std = 1.5 mL/min 將懸液推過 SA 晶片，全程 RT
19. 記錄捕獲開始和完成時間
20. 收集流出液至廢液管，依生物危害廢棄物處理

**[重要]：QC 陽性對照品（每批次平行操作）**

每次正式樣本捕獲批次中，需同時執行 QC 陽性對照（獨立裝置）：
- 100 cells SK-BR-3 懸於 4.0 mL 運行緩衝液
- 加入同量抗體 cocktail（20 μL），同樣條件旋轉孵育 30 min
- 40 μm 過濾後，以 Q_std = 1.5 mL/min 流過另一片 SA 晶片
- IF 染色後計數，確認回收率 ≥ **[TBD]**%（依 Exp 3 結果設定）

**[重要]：QC 陰性對照品（每批次平行操作）**

- 4.0 mL 純運行緩衝液（無細胞），加入 20 μL cocktail，同樣旋轉孵育、過濾、晶片流過
- IF 染色後確認 DAPI+/CK+/CD45- 事件 ≤ **[TBD]**（依 Exp 2B Carryover 結果設定）

---

### 8.4 洗滌（Remove Unbound Cells）

21. PBMC 輸入完成後，立即換接運行緩衝液（PBS + 2% BSA + 2 mM EDTA）
22. 洗滌條件：
    - 流速：**Q_wash = 2.0 mL/min**（允許範圍：1.8–2.2 mL/min）
    - 每次體積：**5.0 mL**
    - 次數：**3 次**（總計 15 mL，自動化或手動執行）
23. 第 3 次洗滌後，洗出液目視確認接近澄清；若仍明顯混濁 → 記錄並加洗第 4 次
24. 最終留約 0.5 mL 緩衝液在裝置中保持濕潤

---

### 8.5 裝置目視 QC

25. 在顯微鏡下（10×–20× 倍率）快速確認裝置表面：
    - 有細胞附著（不可完全空白；空白 → 懷疑孵育、流速或裝置問題）
    - 無大量細胞聚集成團（若有 → 可能 PLT 殘留或洗滌不足）
    - 記錄目視結果於 Form ANA-001-F1
26. 確認裝置完整（無破損、無漏液痕跡）

---

### 8.6 移交 ANA-004

27. 填寫 Form ANA-001-F1 完成欄位（含操作者簽名、完成時間）
28. 將裝置直接移交 ANA-004 操作者，**不可乾燥**（保持緩衝液潤濕）
29. 記錄移交時間；從捕獲完成到 IF 染色開始 ≤ **30 分鐘**

---

## 9. 品質管制（Quality Control）

### 9.1 輸入 QC（孵育前）

| 檢查項目 | 接受標準 |
|---------|---------|
| PRE-004-F1 已完成且 QC 通過 | □ 確認 |
| PBMC 活性 | ≥ 85% |
| 窗口 B 時間（PRE-004 完成到孵育開始）| ≤ **[TBD]** 小時 |
| 捕獲裝置 Lot# 在 ANA-002 有效名單內 | □ 確認 |
| 抗體 Lot# 在 ANA-005 合格名單內 | □ 確認 |

### 9.2 操作過程 QC

| 檢查項目 | 接受標準 |
|---------|---------|
| 抗體孵育轉速 | 10–15 rpm，全程持續 |
| 孵育時間 | 30 ± 2 分鐘 |
| 捕獲流速（Q_std）| 1.5 mL/min ± 10%（1.35–1.65 mL/min）|
| 洗滌流速（Q_wash）| 2.0 mL/min ± 10%（1.8–2.2 mL/min）|
| 洗滌緩衝液 pH | **[TBD]**–**[TBD]**（Exp 5B 定義，預計 6.8–8.0）|

### 9.3 QC 對照品結果（每批次）

| 對照品 | 期望結果 | 驗收標準 |
|--------|---------|---------|
| SK-BR-3 陽性對照（100 cells，同批次孵育）| IF 染色後計數 | 回收率 ≥ **[TBD]**%（依 Exp 3 設定）|
| 運行緩衝液陰性對照（無細胞，同批次流程）| 無 CTC 事件 | ≤ **[TBD]** DAPI+/CK+/CD45- events（依 Exp 2B/Exp 6 設定）|

### 9.4 QC 失敗處理

| 失敗情況 | 處置 |
|---------|------|
| SK-BR-3 回收率 < 標準 | 停止批次；檢查抗體孵育（濃度、時間、轉速）、流速、PBMC 品質；通知 TS；依 QC-003 CAPA |
| 陰性對照出現 CTC 事件 | 懷疑 carryover；停止並調查；依 QC-003（參考 Exp 6 Carryover 結果）|
| 流速超出允許範圍 | 停止；校正注射泵；重新評估細胞懸液時效可否繼續 |
| 裝置目視無細胞附著 | 通知 TS；調查孵育或裝置問題；依 QC-003 |

---

## 10. 記錄（Documentation）

使用 **Form ANA-001-F1**（附於本 SOP 末）

---

## 11. 局限性（Limitations）

1. **間質型 CTC 捕獲效率較低**：高度 EMT（Vimentin+/EpCAM-/EGFR-）的 CTC 可能不被 cocktail 標記。本平台主要針對具有 EpCAM 或 HER2 表現的上皮型 CTC，間質型 CTC 的捕獲不在效能聲稱範圍內。
2. **PRE-004 前置步驟損失**：部分 CTC 在 PBMC 分離步驟中可能損失（見 Exp 3B）。總回收率 = PBMC 分離 recovery × 微流道捕獲效率。
3. **Lot-to-Lot 抗體差異**：不同批次 cocktail 效能可能有差異（目標批間 CV < 15%，依 Exp 1 驗證）。每次使用新 Lot 前需確認在 ANA-005 合格名單中。
4. **血小板殘留影響**：PRE-004 洗滌不足導致高 PLT 殘留，可能非特異性附著晶片或影響捕獲效率（詳見 Phase 3B-1）。

---

## 12. 參考文獻（References）

- R&D Systems Anti-EpCAM (BAF960) / Anti-HER2 (BAF1129) / Anti-EGFR (BAF231) 產品說明書
- PRE-SOP 驗證測試協議（P1-Test 1、Exp 1、Exp 2、Exp 3、Exp 3B、Exp 5、Exp 6）
- PRE-004（血液前處理 SOP）
- ANA-002（捕獲裝置 QC SOP）
- ANA-004（IF 染色 SOP）
- ANA-005（抗體管理 SOP）

---

## 13. 版本記錄（Revision History）

| 版本 | 日期 | 修改摘要 | 修改者 |
|------|------|---------|--------|
| Draft v1.0 | 2026-05-23 | 初稿建立；採晶片抗體預包覆法；主要參數標記為 [TBD] | — |
| Draft v1.1 | 2026-05-23 | **重大修訂**：捕獲機制改為懸液抗體預標記法（20 μL cocktail / 4 mL，RT 30 min，10–15 rpm）；新增 40 μm 過濾步驟；填入 Q_std = 1.5 mL/min、Q_wash = 2.0 mL/min × 5 mL × 3 次；更新緩衝液為 PBS + 2% BSA + 2 mM EDTA；移除晶片包覆/阻斷/PBS-T 步驟 | — |

---

## 附件：Form ANA-001-F1（CTC 捕獲記錄表）v1.1

**樣本與批次資訊**

| 欄位 | 填寫 |
|------|------|
| 樣本 ID | |
| 捕獲裝置 Lot # | |
| 裝置有效期確認（ANA-002 名單）| □ 在效期內 |
| 裝置預濕確認 | □ 通暢無氣泡 |
| Anti-EpCAM Lot # | |
| Anti-HER2 Lot # | |
| Anti-EGFR Lot # | |
| Cocktail 批次 / 配製日期 | |

**PBMC 接收確認**

| 欄位 | 填寫 |
|------|------|
| PRE-004-F1 QC 通過確認 | □ 是 |
| PBMC 活性（%）| |
| 懸液體積（mL）| |
| 窗口 B 時間（PRE-004 完成→孵育開始）| hr |
| 窗口 B 符合規定 | □ 是 □ 否（通知 TS）|

**抗體預孵育（8.1）**

| 欄位 | 填寫 |
|------|------|
| 抗體 Cocktail 加入量（μL）| 20 |
| 懸液體積（mL）| 4.0 |
| 各抗體終濃度確認 | □ 5 μg/mL each |
| 旋轉速度（rpm）| |
| 孵育開始時間 | |
| 孵育完成時間 | |
| 孵育時間（分鐘，目標 30 ± 2）| |

**40 μm 過濾（8.2）**

| 欄位 | 填寫 |
|------|------|
| 篩網批次 / Lot | |
| 過濾完成確認 | □ 是 |
| 過濾異常（如堵塞）| □ 無 □ 有（描述：）|

**SA 晶片捕獲（8.3）**

| 欄位 | 填寫 |
|------|------|
| 注射泵 ID | |
| 設定流速 Q_std（mL/min）| 1.5 |
| 實際流速確認（mL/min）| |
| 捕獲開始時間 | |
| 捕獲完成時間 | |

**洗滌（8.4）**

| 欄位 | 填寫 |
|------|------|
| 洗滌流速 Q_wash（mL/min）| 2.0 |
| 每次體積（mL）| 5.0 |
| 洗滌次數 | 3 |
| 洗滌緩衝液 pH | |
| 第 3 次洗出液外觀 | □ 澄清 □ 仍混濁（加洗第 4 次）|

**QC 對照品**（IF 染色後回填）

| 對照品 | 結果 | 通過標準 | 通過 |
|--------|------|---------|------|
| SK-BR-3 100 cells 陽性（同批次孵育）| 計數 = _____ cells | ≥ [TBD]% 回收率 | □ 是 □ 否 |
| 緩衝液陰性（同批次流程）| 事件 = _____ | ≤ [TBD] events | □ 是 □ 否 |

**裝置目視 QC（8.5）**

| 欄位 | 填寫 |
|------|------|
| 目視細胞附著確認 | □ 可見細胞 □ 無細胞（通知 TS）|
| 裝置完整性 | □ 完好 □ 異常（描述：）|

**移交 ANA-004（8.6）**

| 欄位 | 填寫 |
|------|------|
| 移交時間 | |
| 捕獲完成→IF 開始間隔（min）| |
| ANA-004 接收者簽名 | |

**操作者**

| 欄位 | 填寫 |
|------|------|
| 操作者姓名 / 簽名 | |
| 操作日期 | |
| Technical Supervisor 審核 | |
