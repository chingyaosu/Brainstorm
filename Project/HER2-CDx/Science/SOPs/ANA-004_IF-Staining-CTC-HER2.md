# ANA-004：CTC HER2 免疫螢光染色操作規程
## Immunofluorescence Staining for HER2 on Circulating Tumor Cells

| 項目 | 內容 |
|------|------|
| **文件編號** | ANA-004 |
| **版本** | v1.1 |
| **生效日期** | __________ |
| **撰寫人** | __________ |
| **審查人** | __________ |
| **批准人（Lab Director）** | __________ |
| **下次審查日** | 生效日起 12 個月 |

---

## 1. 目的（Purpose）

建立標準化免疫螢光（IF）染色流程，用於識別循環腫瘤細胞（CTC）並評估其 HER2 蛋白表現狀態，適用於乳癌、胃癌/GEJ 及肺癌患者。

本 SOP 涵蓋兩個應用情境：
- **情境 A（In vitro 系統驗證）**：以已知 HER2 狀態之 cell line spiking 進行方法確效
- **情境 B（臨床樣本）**：對經 CTC 分離裝置（ANA-001）捕獲後的細胞進行染色

---

## 2. 適用範圍（Scope）

適用於：
- In vitro cell line spiking 驗證實驗（情境 A）
- 臨床全血樣本經微流道/濾器捕獲後的 CTC IF 染色（情境 B）

不適用於：
- 石蠟包埋組織切片（FFPE）
- 細胞塊（cell block）或細胞學塗片

---

## 3. 職責（Responsibilities）

| 角色 | 職責 |
|------|------|
| Laboratory Director | 核准本 SOP；審查每批 validation 數據 |
| Technical Supervisor | 試劑驗證（lot-to-lot）；人員能力評估 |
| Medical Laboratory Scientist（MLS） | 執行染色操作；完成 QC 記錄 |

---

## 4. 生物安全注意事項（Safety）

- 臨床血液樣本：BSL-2，需穿戴手套、實驗衣，操作於生物安全櫃（BSC）內
- Cell line（非臨床）：依細胞株風險評估，至少 BSL-1 操作
- 4% Paraformaldehyde（PFA）：具揮發性、毒性，操作須在通風櫥內進行
- 螢光試劑：避光保存與操作
- 廢液處理：依機構生物廢棄物規範

---

## 5. 方法原理（Principle）

採用多色免疫螢光染色（multiplexed IF），以四通道螢光抗體組合識別並分類捕獲細胞：

| Channel | 標記物 | 功能 | 螢光團（**已確認**）| 激發/發射（nm）|
|---------|--------|------|-------------------|--------------|
| Ch 1（UV） | **DAPI** | 核染色，辨識所有有核細胞 | **DAPI** | 358 / 461 |
| Ch 2（Green） | **HER2** | CDx 目標蛋白，評估 CTC HER2 表現 | **FITC** | 490 / 525 |
| Ch 3（Orange） | **Cytokeratin（Pan-CK）** | 上皮細胞標記，CTC 為 CK⁺ | **PE** | 496, 565 / 578 |
| Ch 4（Far-Red） | **CD45** | 白血球標記，CD45⁺ = 排除 | **APC** | 650 / 660 |

> **螢光組合已確認**：DAPI / HER2-FITC / CK-PE / CD45-APC。後續所有驗證實驗統一使用此四色 panel。

**CTC 定義**：DAPI⁺ / CK⁺ / CD45⁻，細胞直徑 > 4 μm（依影像分析設定）

**HER2 評分**：基於 Ch 2 螢光強度（MFI），相對於已知 HER2 狀態 cell line 對照組，採半定量分級 0 / 1+ / 2+ / 3+（截斷值定義詳見 ANA-010 及 Phase 4 驗證）

---

### 5.1 偵測策略：直接螢光標記 vs. 二級抗體放大

> **本節為 SOP 關鍵設計決策，最終選擇須依 P1-Test 2b 驗證結果填入。**

本平台使用**螢光顯微鏡**作為最終偵測儀器，偵測策略有兩種：

**策略 A：Direct（直接螢光標記一級抗體）**
- 一級抗體本身帶螢光基團（如 anti-HER2-FITC 直接標記）
- 流程：固定 → 阻斷 → 直接標記一級抗體混合液孵育 → DAPI → 影像
- 優點：步驟少（省去二級抗體步驟）、背景低、Multiplex 設計簡單（無物種交叉反應風險）
- 缺點：每支抗體須購買 conjugated 版本（成本較高）；訊號強度受限於單一螢光分子數

**策略 B：Indirect（未標記一級抗體 + 螢光二級抗體放大）**
- 一級抗體（unconjugated）結合目標 → 螢光標記二級抗體再結合一級抗體（1 個一級抗體可結合多個二級 → 訊號放大 3–10 倍）
- 流程：固定 → 阻斷 → 一級抗體孵育 → 洗滌 → 二級抗體孵育 → DAPI → 影像
- 優點：訊號放大，對 HER2 低表現（1+/2+）的 CTC 偵測靈敏度更高；一級抗體選擇彈性大
- 缺點：步驟多；Multiplex 設計限制——**三支偵測一級抗體（HER2、CK、CD45）必須來自不同物種**，否則二級抗體交叉反應

**物種衝突風險（Indirect 策略必須確認）**：

| 抗體 | 常見 Clone | 常見來源物種 | 衝突警示 |
|------|-----------|------------|---------|
| Anti-CK（AE1/AE3） | AE1/AE3 | **Mouse IgG1** | ⚠️ 若 CD45 或 HER2 也是 Mouse，則衝突 |
| Anti-CD45 | 2B11+PD7/26 | **Mouse IgG1** | ⚠️ 與 CK 同種 → 二級抗體無法區分 |
| Anti-HER2（CB11） | CB11 | **Rabbit IgG** | ✅ 與上兩者物種不同，可用兔源二級抗體 |

> **⚠️ 注意**：Anti-CK（AE1/AE3）和 Anti-CD45（2B11）都是 Mouse IgG1，若同時用 Indirect，鼠源二級抗體會同時染這兩個目標，**無法區分通道**。
>
> **解決方案選項**：
> 1. CK 改用直接標記（Direct）的 anti-CK-PE；CD45 也改用 Direct anti-CD45-APC；僅 HER2 用 Indirect 放大（**混合策略，最實用**）
> 2. 將 CD45 換成 Rabbit clone（如部分廠商提供的 rabbit anti-CD45），使三者都來自不同物種
> 3. 全部改用 Direct（最簡單，但 HER2 低表現可能訊號不足）
> 4. 順序染色（Sequential Staining）——先染 HER2，洗淨，再染 CK/CD45——但大幅增加操作時間和步驟，不建議常規使用

**目前推薦方向（待 P1-Test 2b 驗證）**：

```
推薦策略：混合法（Hybrid）
  - HER2：Indirect（二級抗體放大）→ 最大化低表現細胞的偵測靈敏度
  - Pan-CK：Direct conjugated（anti-CK-PE 或等效）→ 避免與 CD45 鼠源衝突
  - CD45：Direct conjugated（anti-CD45-APC 或等效）→ 避免衝突且足夠靈敏
  - DAPI：直接加入（無抗體問題）
```

**最終選擇**：依 P1-Test 2b 數據，由 Technical Supervisor 決定，記錄於本 SOP 第 7 節及修訂記錄。

---

## 6. 設備（Equipment）

| 設備 | 規格要求 | 校正頻率 |
|------|---------|---------|
| 螢光倒置顯微鏡 | 4 通道（DAPI / FITC / TRITC / Cy5）或等效 | 每次使用前確認 |
| 影像擷取系統 | 詳見 ANA-007/008 | — |
| 離心機 | 可達 300–500 × g | 每年校正 |
| 生物安全櫃 | Class II Type A2 | 每年認證 |
| 加濕培養箱 | 37°C, 5% CO₂（cell line 培養用） | 每日記錄溫度 |
| 計時器、移液器（校正中） | — | 每年校正 |
| 水浴槽（若需 37°C 孵育） | ±1°C 精度 | — |

---

## 7. 試劑與材料（Reagents & Materials）

### 7.1 固定與穿透

| 試劑 | 濃度 / 規格 | 儲存 | 備註 |
|------|------------|------|------|
| Paraformaldehyde（PFA） | 4% in PBS | 4°C，避光 | 現配或分裝凍存（-20°C） |
| PBS（磷酸鹽緩衝液） | pH 7.4 | RT | 無 Ca²⁺/Mg²⁺ |
| Triton X-100 | 0.1% in PBS | RT | 細胞內 CK 染色需穿透 |

### 7.2 阻斷（Blocking）

| 試劑 | 濃度 | 儲存 |
|------|------|------|
| Normal Goat Serum 或 Normal Donkey Serum | 5–10% in PBS | 4°C |
| BSA | 1% in PBS（替代方案） | 4°C |

### 7.3 一級抗體（Primary Antibodies）

> **偵測策略確認前（P1-Test 2b 完成前），下表為候選選項。最終選定後，刪去未採用的列並更新版本。**

**偵測抗體（IF Staining Detection Panel）——螢光通道已確認**：

| 標的 | 螢光團 | 形式（**待測試決定**）| Clone（候選）| 稀釋度（待驗證）| 儲存 |
|------|--------|---------------------|-------------|----------------|------|
| **HER2** | **FITC** | ⬜ **Direct（Anti-HER2-FITC）** OR **Indirect（Anti-HER2 unconjugated + Anti-rabbit-FITC 二級）** → **由 P1-Test 2b 決定** | CB11 / SP3 / 4B5 | 待定 | 4°C 避光 |
| **Pan-CK** | **PE** | **Direct conjugated**（Anti-CK-PE） | AE1/AE3 | 依廠商，P1-Test 2 驗證 | 4°C 避光 |
| **CD45** | **APC** | **Direct conjugated**（Anti-CD45-APC） | 2B11+PD7/26 或等效 | 依廠商，P1-Test 2 驗證 | 4°C 避光 |

> **CK-PE 和 CD45-APC 採 Direct 的原因**：兩者常見 clone（AE1/AE3 和 2B11）均為 Mouse IgG1，若同時用二級抗體放大，鼠源二級抗體無法區分兩者，PE 和 APC 通道會交叉染色。Direct conjugated 完全避開此問題，且 CK 和 CD45 的訊號強度通常足夠，不需放大。

> **HER2-FITC 的策略選擇取決於**：在你的顯微鏡系統下，Anti-HER2-FITC 直接標記能否有效區分 HER2 1+ 和 HER2 0 的 CTC？若 SNR 不足，改用 Indirect（unconjugated Anti-HER2 + Anti-rabbit-FITC 二級）放大訊號。兩者使用的**螢光通道相同（FITC/Ch 2）**，不影響 panel 設計。

> **一級抗體稀釋度**：須於每批新 Lot 進行 titration 驗證（P1-Test 2 及 LAB-005）

### 7.4 二級抗體（Secondary Antibody，僅當 HER2 採用 Indirect 策略時使用）

> **P1-Test 2b 完成前，本節為條件性使用。若 HER2 最終確認採 Direct（Anti-HER2-FITC），本節整節跳過。**

| 試劑 | 標靶物種 | 螢光團 | 通道 | 工作稀釋度（待驗證）| 儲存 |
|------|---------|--------|------|-------------------|------|
| Anti-Rabbit IgG（H+L）-FITC | Rabbit | **FITC** | Ch 2（Green）| 1:500–1:1000 | 4°C 避光 |

> CK（PE）和 CD45（APC）均採 Direct conjugated，**不需要任何二級抗體**，交叉反應風險為零。

### 7.5 核染色

| 試劑 | 工作濃度 | 儲存 |
|------|---------|------|
| DAPI | 300 nM in PBS（或 0.1 μg/mL） | -20°C 原液，4°C 工作液（1 週內） |

### 7.6 其他耗材

- 封片液（Fluoromount-G 或等效，含抗淬滅）
- 蓋玻片（#1.5，適合高數值孔徑物鏡）
- 載玻片（若 filter-based 方法：polycarbonate membrane 固定）
- 濕盒（孵育用）

---

## 8. 情境 A：In Vitro Cell Line 系統驗證

> **用途**：在進入臨床樣本前，以已知 HER2 狀態的細胞株確認整個染色系統（抗體特異性、染色條件、影像判讀）運作正常。

### 8.1 建議 Cell Line 組合

| Cell Line | 癌種 | HER2 IHC 等效 | 用途 |
|-----------|------|--------------|------|
| **SK-BR-3** | 乳癌 | 3+（強陽性） | 強陽性對照 |
| **BT-474** | 乳癌 | 3+（強陽性） | 備用陽性 |
| **NCI-N87** | 胃癌 | 3+（強陽性） | 胃癌陽性對照 |
| **ZR-75-30** | 乳癌 | 2+（中等） | 中等表現 |
| **MCF-7** | 乳癌 | 1+（弱/低） | 弱陽性參考 |
| **MDA-MB-231** | 乳癌 | 0（陰性） | 陰性對照 |
| **Jurkat** | T cell 白血病 | N/A | CD45⁺ 陰性對照（排除 CK⁻/CD45⁺）|

> 最低需求：SK-BR-3（強陽性）+ MDA-MB-231（陰性）+ Jurkat（CD45 對照）

### 8.2 Cell Line 培養與準備

1. 依各 cell line 培養說明，在 5% CO₂、37°C 培養至 70–80% confluency
2. 用 PBS 洗滌培養瓶 2 次，去除血清
3. 加 Trypsin-EDTA（0.25%）輕搖至細胞脫附（3–5 min，37°C）
4. 加等體積完全培養液中止消化，收集至 15 mL 離心管
5. 300 × g，5 min，室溫離心，棄上清
6. 用 PBS 重懸，計數（hemocytometer 或自動計數儀）
7. 調整濃度至 **1 × 10⁶ cells/mL** in PBS

### 8.3 Spiking 實驗設計（全流程驗證）

**目的**：模擬臨床 CTC，將已知數量 cell line 加入健康人全血中，跑完整個捕獲+染色流程

| 樣本 | 血液來源 | 加入細胞 | 預期結果 |
|------|---------|---------|---------|
| S1 | 健康人 7.5 mL EDTA 血 | SK-BR-3：100 cells | CTC 可見，HER2⁺⁺⁺ |
| S2 | 健康人 7.5 mL EDTA 血 | MDA-MB-231：100 cells | CTC 可見，HER2⁻ |
| S3 | 健康人 7.5 mL EDTA 血 | SK-BR-3 + MDA-MB-231：各 50 cells | 可區分兩群 |
| NEG | 健康人 7.5 mL EDTA 血 | 不加細胞 | 無 CK⁺/CD45⁻ 細胞 |

> **Spike 方法**：取計數後細胞懸液，稀釋至目標數量後，用 pipette 直接加入採血管，輕旋轉混勻，立即進行 ANA-001 CTC 分離流程

### 8.4 直接染色（不跑捕獲流程，用於抗體條件最佳化）

當需要單獨優化抗體稀釋度或染色條件，可跳過捕獲步驟：

1. 取細胞懸液（1–5 × 10⁴ cells）離心至蓋玻片，或塗至 poly-L-lysine 塗佈之蓋玻片
2. 空氣乾燥 10–15 min，或低速離心（Cytospin）
3. 直接從步驟 9.1（固定）開始執行 IF 染色

---

## 9. 染色操作流程（Staining Procedure）

> 適用情境 A（直接染色）及情境 B（臨床捕獲後）

### 9.1 固定（Fixation）

1. 確認捕獲裝置（filter/slide）或蓋玻片上有細胞
2. 加入 **4% PFA in PBS**，覆蓋細胞，室溫（RT）靜置 **15 分鐘**
3. 吸去 PFA，用 **PBS 洗滌 3 次**，每次 5 分鐘（輕柔移液，避免細胞脫落）

> ⚠️ PFA 操作於通風櫥內進行；廢液收集至標示容器

### 9.2 穿透（Permeabilization）

（用於細胞內 Cytokeratin 染色，若使用細胞外域抗體可省略）

4. 加入 **0.1% Triton X-100 in PBS**，RT 靜置 **10 分鐘**
5. PBS 洗滌 **3 次**，每次 5 分鐘

### 9.3 阻斷（Blocking）

6. 依 HER2 偵測策略選擇阻斷血清：

   | HER2 策略 | 阻斷血清 | 理由 |
   |-----------|---------|------|
   | **Indirect**（Anti-rabbit-FITC 二級）| **5% Normal Goat Serum in PBS** | Goat anti-rabbit 二級抗體的宿主物種為山羊，阻斷用 goat serum 可飽和非特異性結合位 |
   | **Direct**（Anti-HER2-FITC 直標）| 5% Normal Goat Serum 或 1% BSA in PBS | 無二級抗體，兩者均可 |

7. RT 靜置 **30 分鐘**，置於濕盒中
8. **不需洗滌**，直接吸去阻斷液（殘留少量不影響後續步驟）

### 9.4 一級抗體孵育（Primary Antibody Incubation）

> **本步驟依第 5.1 節確定的偵測策略執行。推薦策略：HER2 Indirect + CK Direct + CD45 Direct（混合策略）。**

**[混合策略 / Hybrid Strategy]**

9. 配製一級抗體混合液（含 3 種抗體，依 9.5 節）：
   - Anti-HER2（unconjugated Rabbit，工作濃度）
   - Anti-CK-PE（direct conjugated，工作濃度）
   - Anti-CD45-APC（direct conjugated，工作濃度）
10. 將抗體液均勻滴至細胞上，確保完全覆蓋（不留乾燥死角）
11. 置於濕盒，**4°C 過夜（16–18 小時）**

    > 若時間限制改用室溫，則 RT 孵育 **1.5–2 小時**（Direct conjugated 在 RT 下效果通常接近過夜；但 HER2 Indirect 若抗原表位稀少，建議維持過夜以確保靈敏度）

12. 取出，放置 RT 回溫 **15 分鐘**（避免溫差造成細胞脫落）
13. PBS 洗滌 **3 次**，每次 **5 分鐘**（輕輕移液，不可直接沖在細胞上）

**[若採用全 Direct 策略（備選）]**：步驟 9–13 相同，但抗體混合液改為三支全都是 direct conjugated，步驟 9.6（二級抗體）可完全跳過。

### 9.5 一級抗體配製（Antibody Cocktail Preparation）

**每批染色前現配，不可提前超過 2 小時配製。配製完成後置於冰上或 4°C 保存，避光。**

**情境 1：HER2 Indirect 策略（P1-Test 2b 結果 → SNR 不足時採用）**

| 成分 | 工作濃度 | 體積（100 μL/樣本）| 備註 |
|------|---------|-----------------|------|
| Anti-HER2（unconjugated Rabbit IgG）| 待定（P1-Test 2b）| X μL | 4°C 過夜孵育 |
| Anti-CK-PE（direct conjugated）| 待定（P1-Test 2 驗證後填入）| X μL | 避光 |
| Anti-CD45-APC（direct conjugated）| 待定（P1-Test 2 驗證後填入）| X μL | 避光 |
| 1% BSA in PBS | — | 補至 100 μL | 稀釋液 |

→ 孵育後須進行 Section 9.6（Anti-rabbit-FITC 二級抗體步驟）

**情境 2：HER2 Direct 策略（P1-Test 2b 結果 → SNR 足夠時採用）**

| 成分 | 工作濃度 | 體積（100 μL/樣本）| 備註 |
|------|---------|-----------------|------|
| Anti-HER2-FITC（direct conjugated）| 待定（P1-Test 2b）| X μL | 避光 |
| Anti-CK-PE（direct conjugated）| 待定（P1-Test 2 驗證後填入）| X μL | 避光 |
| Anti-CD45-APC（direct conjugated）| 待定（P1-Test 2 驗證後填入）| X μL | 避光 |
| 1% BSA in PBS | — | 補至 100 μL | 稀釋液 |

→ 孵育後**跳過** Section 9.6，直接進 Section 9.7（DAPI）

> **記錄**：配製時記錄各抗體 Lot#、稀釋度、配製時間及採用策略（Direct/Indirect）於 **Form ANA-004-F1**

### 9.6 二級抗體孵育（Secondary Antibody for HER2 Indirect Amplification）

> **本步驟僅限 HER2 Indirect 策略時執行。若 HER2 改用 Direct conjugated，跳至 9.7。**

14. 配製二級抗體工作液：
    - **Anti-Rabbit IgG（H+L）-FITC**
    - 稀釋度：1:500–1:1000（依 P1-Test 2b 最佳化結果）
    - 稀釋液：1% BSA in PBS
    - 每樣本 100 μL
15. 滴至細胞上，置於濕盒，**RT 避光靜置 45 分鐘**
16. PBS 洗滌 **3 次**，每次 **5 分鐘**，**全程避光**
    > ⚠️ 步驟 14 起所有操作全程避光

> **注意**：步驟 14 開始後，所有後續操作均須避光（包括洗滌、DAPI、封片）。建議關燈或用鋁箔覆蓋樣本。

> **Cross-reactivity 確認**：若懷疑二級抗體非特異性結合，以「無一級抗體的二級抗體空白對照」監控（QC-002）

### 9.7 DAPI 核染色

17. 加入 **300 nM DAPI**（或依廠商建議），RT 靜置 **5 分鐘**，**避光**
18. PBS 洗滌 **2 次**，每次 5 分鐘

### 9.8 封片（Mounting）

19. 吸乾多餘液體（勿完全乾燥；細胞周圍留少量 PBS 保持濕潤）
20. 加一小滴封片液（Fluoromount-G 或等效，含抗淬滅成分）
21. 輕蓋蓋玻片（#1.5），從一側緩慢放下，避免氣泡
22. 室溫暗處靜置 **至少 1 小時**（或 4°C 過夜）待封片液固化
23. 邊緣用指甲油封邊（推薦），防止蓋玻片移動及樣本乾燥

> 若使用 filter-based 捕獲裝置：依裝置廠商指示進行對應固定與封片步驟

### 9.9 影像擷取

→ 依 **ANA-007**（顯微鏡操作）及 **ANA-008**（影像擷取參數）執行

---

## 10. 品質管制（Quality Control）

### 10.1 每批次必須設立的對照組

| 對照組 | 內容 | 預期結果 | 若失敗 |
|--------|------|---------|--------|
| **陽性對照（HER2⁺⁺⁺）** | SK-BR-3 cells | HER2 通道強螢光、CK⁺、CD45⁻ | 停止批次，排查抗體或步驟 |
| **陰性對照（HER2⁻）** | MDA-MB-231 cells | CK⁺、CD45⁻，HER2 通道無訊號 | 停止批次，疑交叉染色 |
| **CD45 對照** | Jurkat cells | CD45⁺、DAPI⁺、CK⁻ | 確認白血球排除功能正常 |
| **二次抗體空白對照** | 只加二級抗體，不加一級 | 所有通道無訊號 | 疑非特異性結合，重新阻斷 |

### 10.2 QC 接受標準（暫定，待 validation 數據定案）

| 指標 | 接受標準 |
|------|---------|
| SK-BR-3 HER2 平均螢光強度（MFI） | ≥ ______（待定） |
| MDA-MB-231 HER2 MFI | ≤ SK-BR-3 MFI 的 20%（待定） |
| 二次抗體空白 | 所有通道訊號 ≤ 背景 + 2 SD |
| CTC 捕獲率（情境 A spiking） | 詳見 VAL-006 |

> **QC 記錄**：完成 Form ANA-004-F1，附影像截圖，Technical Supervisor 每週 review

### 10.3 QC 失敗處理

→ 依 **QC-003**（QC 失效與矯正措施）執行
→ 臨床樣本結果**不得發出**直到 QC 通過並完成矯正記錄

---

## 11. In Vitro 系統驗證接受標準

執行 **情境 A**（Cell Line Spiking）後，須達到以下所有標準，方可進展至臨床樣本：

| 驗證項目 | 接受標準 |
|---------|---------|
| 1. HER2 辨別力 | SK-BR-3 vs MDA-MB-231 之 HER2 MFI 比值 ≥ 5 |
| 2. CK 特異性 | ≥ 95% CK⁺ 細胞來自上皮 cell line（非 Jurkat） |
| 3. CD45 排除效率 | Jurkat cells：≥ 95% 為 CD45⁺ |
| 4. CTC 定義一致性 | 兩位操作者獨立計數，計數差異 ≤ 20% |
| 5. 負對照整潔度 | 無細胞 spiking 的血液樣本：CK⁺/CD45⁻ 事件 ≤ 5/樣本 |
| 6. 重複性（初步） | 同批次 3 重複，CTC 計數 CV ≤ 25% |

> 達到以上標準後，由 Lab Director 簽核，記錄於 **VAL-001（驗證計畫）**，方可進行臨床樣本測試

---

## 12. 結果記錄（Documentation）

每次染色須完成：
- **Form ANA-004-F1**：染色批次記錄（試劑 Lot#、操作人、日期時間、QC 結果）
- **Form ANA-004-F2**：Cell Line Spiking 紀錄表（情境 A 用）
- 原始影像檔：存入指定伺服器目錄，依樣本 ID 命名，**不得覆蓋**

---

## 13. 疑難排解（Troubleshooting）

| 問題 | 可能原因 | 處理方式 |
|------|---------|---------|
| **HER2 通道無訊號（SK-BR-3 對照也無）** | 抗體失效 / 稀釋錯誤 / 孵育溫度過高 | 確認抗體 Lot#、稀釋度；用已知有效批次重跑對照；確認冰箱溫度記錄 |
| **HER2 背景過高（MDA-MB-231 也有訊號）** | 阻斷不足 / 抗體濃度過高 / 二級抗體非特異結合 | 延長阻斷時間至 60 分鐘；降低一級抗體稀釋度；確認二級抗體空白對照；加入 Anti-mouse IgG 預吸附步驟 |
| **CK 通道無訊號** | 穿透不足（CK 為胞內蛋白）/ PE 淬滅 | 延長 Triton X-100 穿透至 15 分鐘；確認 CK-PE 試劑未淬滅（避光保存確認）；換新批次試劑 |
| **CD45 和 CK 訊號互相出現在對方通道** | 濾光片（Filter）設定錯誤 / 光譜重疊（Spectral bleedthrough）| 確認顯微鏡各通道濾光片設定（見 ANA-007）；若有光譜重疊，進行 spectral unmixing 或調整曝光參數 |
| **DAPI 染色不均，部分細胞核未染色** | DAPI 工作液過期 / 洗滌過度 | 更換 DAPI 工作液（現配）；減少洗滌次數或縮短時間 |
| **細胞大量脫落（影像中細胞數極少）** | 固定不足 / 洗滌太激烈 / 蓋玻片 poly-L-lysine 不夠 | 確認 PFA 濃度（新配）；洗滌改用側面輕柔加液；重新包覆 poly-L-lysine 蓋玻片 |
| **全視野背景螢光過高（自體螢光）** | 固定過久（PFA 交聯增加自體螢光）/ 血液樣本紅血球干擾 | 縮短 PFA 固定時間至 10 分鐘；加入 Glycine 淬滅（100 mM，PBS，RT 5 分鐘）；確認 RBC 已充分去除 |
| **影像失焦 / 多焦面不清楚** | 封片液未固化 / 蓋玻片滑動 | 等待封片液完全固化後再進行影像擷取；確認指甲油封邊已完成 |
| **批次間 SK-BR-3 MFI 差異 > 20%** | 不同傳代細胞 HER2 表現漂移 / 抗體不同 Lot | 確認 cell line 傳代數（≤ 20）；進行 FACS 確認 HER2 表現量；執行新 Lot 抗體驗證 |

---

## 14. 限制（Limitations）

- 本方法為 LDT，尚未取得 FDA clearance
- CK 陽性不等同 CTC；最終 CTC 定義須結合形態學判讀（ANA-009）
- 固定後細胞無法再做核酸分析（若後續需要 RNA，需調整固定方案）
- HER2 IF 評分與組織 IHC 評分不可直接對等（需臨床相關性研究）
- EpCAM-low 或 Epithelial-Mesenchymal Transition（EMT）細胞可能低表現 CK，導致 CTC 低估

---

## 14. 參考文獻（References）

1. Allard WJ, et al. *Tumor Cells Circulate in the Peripheral Blood of All Major Carcinomas but not in Healthy Subjects or Patients With Nonmalignant Diseases.* Clin Cancer Res. 2004.
2. ASCO/CAP HER2 Testing Guideline Update. *J Clin Oncol.* 2018.
3. CLSI EP12-A2: *User Protocol for Evaluation of Qualitative Test Performance.* 2nd ed.
4. CLSI QMS02: *Quality Management System: Development and Management of Laboratory Documents.* 6th ed.
5. Janni W, et al. *Pooled Analysis of the Prognostic Relevance of Circulating Tumor Cells in Primary Breast Cancer.* Clin Cancer Res. 2016.

---

## 15. 修訂記錄（Revision History）

| 版本 | 日期 | 修訂內容 | 修訂人 |
|------|------|---------|--------|
| v1.0 | 2026-05-23 | 初版建立 | __________ |
| v1.1 | 2026-05-23 | 確認螢光 panel（DAPI/FITC/PE/APC）；加入 Hybrid 策略架構；修正二級抗體螢光團標示 | __________ |
| v1.2 | 2026-05-23 | 修正步驟編號；補充 Blocking serum 依策略選擇；補充 Direct/Indirect 兩情境抗體配製表；加入 Troubleshooting section；建立 Form F1、F2 及流程圖 | __________ |

---

## 附件（Appendices）

---

### Form ANA-004-F1：IF 染色批次記錄表
*每次染色操作必須完整填寫，Technical Supervisor 每週審核簽字*

```
文件編號：ANA-004-F1                    批次編號：______________
日期：______________                    操作人員：______________
樣本類型：□ Cell Line（情境A）  □ 臨床樣本（情境B）

─── 樣本資訊 ───────────────────────────────────────────────
樣本 ID：_______________________________________________
採血管類型：□ EDTA  □ Streck  □ 其他：_________________
採血時間：______________  捕獲完成時間：______________
捕獲裝置批號：________________

─── 試劑記錄 ───────────────────────────────────────────────
試劑                    廠牌/Lot#              稀釋度       效期
4% PFA                  ________________       N/A         __________
Anti-HER2               ________________       1:_____     __________
  □ Unconjugated（Indirect）  □ FITC conjugated（Direct）
Anti-CK-PE              ________________       1:_____     __________
Anti-CD45-APC           ________________       1:_____     __________
Anti-Rabbit-FITC（若用）________________       1:_____     __________
DAPI                    ________________       300 nM      __________
封片液                  ________________       N/A         __________

HER2 偵測策略：□ Direct（Anti-HER2-FITC）  □ Indirect（Anti-HER2 + Anti-rabbit-FITC）

─── 步驟時間記錄 ────────────────────────────────────────────
固定（4% PFA）：開始 ________  結束 ________（目標 15 min）
穿透（Triton X-100）：開始 ______  結束 ______（目標 10 min）
阻斷（Normal Goat Serum）：開始 ______  結束 ______（目標 30 min）
一級抗體孵育：開始 ________  結束 ________（□ 4°C 過夜  □ RT ___hr）
二級抗體孵育（若用）：開始 ______  結束 ______（目標 45 min，RT）
DAPI：開始 ________  結束 ________（目標 5 min）

─── QC 對照組結果 ───────────────────────────────────────────
對照組              預期結果              實際結果            Pass/Fail
SK-BR-3（HER2 3+） HER2 MFI ≥ ___（待定）MFI = _________    □ P  □ F
MDA-MB-231（HER2 0）HER2 MFI ≤ ___       MFI = _________    □ P  □ F
Jurkat（CD45+）    CD45+ ≥ 95%，CK < 5%  CD45 = __% CK = _% □ P  □ F
二級抗體空白對照   所有通道 ≤ 背景+2SD   _________________   □ P  □ F

整體 QC 判定：□ PASS（可繼續影像分析）  □ FAIL（停止，執行 QC-003）

─── 影像儲存 ────────────────────────────────────────────────
影像檔路徑：_________________________________________________
檔案命名格式：[樣本ID]_[日期]_[操作人縮寫]_[Ch1-4]

─── 簽核 ────────────────────────────────────────────────────
操作人簽名：________________  日期：______________
Technical Supervisor 審核：________________  日期：______________
```

---

### Form ANA-004-F2：Cell Line Spiking 紀錄表
*情境 A（In vitro 系統驗證）專用*

```
文件編號：ANA-004-F2                    實驗日期：______________
操作人員：______________               實驗目的：______________

─── 細胞準備記錄 ────────────────────────────────────────────
Cell Line      傳代數   活性（%）   計數方法       計數結果（cells/mL）
SK-BR-3        P____    _____       □ Hemocytometer  ________________
MCF-7          P____    _____       □ LUNA-FL        ________________
MDA-MB-231     P____    _____       □ 其他：______   ________________
Jurkat         P____    _____                        ________________
HCT116         P____    _____                        ________________

細胞活性是否 ≥ 90%？□ 是  □ 否（若否，停止實驗，記錄原因：____________）
傳代數是否 ≤ 20？  □ 是  □ 否（若否，停止實驗）

─── Spiking 設計 ────────────────────────────────────────────
血液來源捐贈者 ID：______________  採血時間：______________
採血管類型：□ EDTA  □ Streck

樣本     Cell Line      目標細胞數   實際加入體積   估算實際加入數
S1       SK-BR-3        _____ cells   _____ μL      ≈ _____ cells
S2       MDA-MB-231     _____ cells   _____ μL      ≈ _____ cells
S3       SK-BR-3        _____ cells   _____ μL      ≈ _____ cells
         MDA-MB-231     _____ cells   _____ μL      ≈ _____ cells
NEG      無細胞         —             —              —

Spike 完成時間：______________
CTC 捕獲開始時間：______________（應在 Spike 後 60 分鐘內）

─── IF 染色結果 ──────────────────────────────────────────────
（染色批次記錄見 Form ANA-004-F1，批次編號：____________）

─── 影像分析結果 ────────────────────────────────────────────
樣本    計數者 A（cells）  計數者 B（cells）  平均    差異%    Pass（≤20%）
S1      _____________     _____________    _____   _____    □ P  □ F
S2      _____________     _____________    _____   _____    □ P  □ F
S3 CK+HER2+ _________    _____________    _____   _____    □ P  □ F
S3 CK+HER2- _________    _____________    _____   _____    □ P  □ F
NEG     _____________     _____________    _____   —        □（≤5 events）

HER2 MFI 記錄：
SK-BR-3 MFI（Ch2-FITC）：__________
MDA-MB-231 MFI（Ch2-FITC）：__________
SNR（SK-BR-3/MDA-MB-231）：__________（目標 ≥ 5）

─── 系統驗證判定 ────────────────────────────────────────────
□ 所有 Section 11 驗收標準通過 → Lab Director 簽核後可進入臨床樣本
□ 部分未通過 → 記錄原因，執行 CAPA

Lab Director 簽名：________________  日期：______________
```

---

### 附圖 1：Cell Line HER2 IF 表現參考影像
*(待補充：SK-BR-3 / MCF-7 / MDA-MB-231 的 DAPI / HER2-FITC / CK-PE / CD45-APC 疊圖)*

### 附圖 2：染色流程圖（Decision Tree）

```
固定（4% PFA, 15min）
    ↓
穿透（0.1% Triton X-100, 10min）
    ↓
阻斷（5% Normal Goat Serum, 30min）
    ↓
一級抗體混合液（4°C 過夜）
Anti-HER2 [Direct-FITC 或 unconjugated] + Anti-CK-PE + Anti-CD45-APC
    ↓ 洗滌 ×3
    ├── [HER2 Indirect] → Anti-rabbit-FITC 二級抗體（RT, 45min）→ 洗滌 ×3
    └── [HER2 Direct]   → 直接進下一步
    ↓
DAPI（300nM, 5min）
    ↓ 洗滌 ×2
封片 → 影像擷取（ANA-007/008）→ 影像分析（ANA-009/010）
```
