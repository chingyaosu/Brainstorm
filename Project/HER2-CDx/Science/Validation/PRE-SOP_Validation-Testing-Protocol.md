# HER2-CTC-CDx 平台：SOP 前驗證測試完整協議
## Pre-SOP Validation Testing Protocol — Step-by-Step

**文件版本**：v1.3  
**日期**：2026-05-23（v1.3 更新：前處理確認為 Ficoll PBMC 分離；Phase 3-B 重設計為 PBMC-level 干擾測試；Phase 0.5 加入窗口 B；Exp 3 加入 Ficoll step recovery）  
**基礎文件**：HER2_CTC_CDx_RD_Plan.docx（含第二部分）  
**適用範圍**：進入正式臨床 SOP 前，所有必要的實驗室驗證工作

## 已確認設計決策（v1.2）

| 項目 | 決策 | 理由 |
|------|------|------|
| Capture Antibody Cocktail | **EpCAM + HER2 + EGFR**（三種）| EGFR 補捉 EpCAM-low 細胞；MUC1/CD49f/c-Met 暫不納入 |
| EGFR 使用理由 | 保留；需在 Exp 2 中驗證 WBC 背景 | EpCAM-low CTC 需 EGFR 補強捕獲率 |
| Spike-in 密度 | **2, 4, 6, 8, 10, 50, 100 cells/7.5 mL** | 低密度端細分（CDx 關鍵範圍） |
| **採血管** | **K2-EDTA 確認採用，Streck 不用** | EDTA 成本低、操作熟悉；需做 EDTA 在 RT + 4°C 的穩定性測試（T0–T96h） |
| HER2 vs 組織 IHC 橋接 | 本階段不納入，列為 Next Step；但概念保留在討論文件中 | 先建立平台分析性能 |
| 螢光 Panel | **DAPI / HER2-FITC / CK-PE / CD45-APC**（已確認）| 通道與螢光團固定；HER2 Direct vs Indirect 由 P1-Test 2b 決定 |
| MESF 校正 | **必須實施**，在 Phase 4 評分截斷值定義前完成 | HER2 評分截斷值以 MESF 絕對單位定義，防止長期漂移 |
| 精密度驗證標準 | **CLSI EP05-A3**（4 維度：批內/跨天/跨操作者/跨儀器/跨批次）| CLIA CAP 要求 |
| **前處理設計** | **全血 → Ficoll PBMC 分離 → CTC 捕獲**（非直接全血捕獲）| 移除血漿組分干擾（Hb/Bili/Lipemia 在 Ficoll 後幾乎不存在）；HIL 測試改為 PBMC-level 干擾；CTC 的 Ficoll step recovery 需單獨驗證 |

---

## 總覽：為什麼要做這些測試？

在 CLIA/CAP 認證實驗室對臨床樣本執行 HER2 CTC 檢測之前，必須證明：

1. **你用的材料是對的**（Cell line 身份正確、抗體有效）
2. **你的系統能抓到細胞**（捕獲效率與專一性）
3. **你的染色能區分 HER2+ 和 HER2-**（特異性與靈敏度）
4. **你的系統在不同條件下都穩定**（重複性、穩定性）
5. **你知道系統的極限在哪裡**（LOD、AMR、干擾物）

這些測試構成「Method Validation」，是 CLIA 42 CFR §493.1253 的要求，也是 CAP 檢查必看項目。

---

## 測試執行順序（必須依序進行）

```
Phase 0    Cell Line Qualification（STR / Mycoplasma / FACS / 活性）
    ↓
Phase 0.5  Pre-Analytical Stability（兩段時間窗口）
    ├── 窗口 A：全血等待時間（T0→T96h，RT + 4°C）→ 定義 Ficoll 前的最長等待時間
    └── 窗口 B：PBMC 懸液等待時間（T0→T8h，4°C）→ 定義 PBMC 分離後到捕獲的最長等待時間
    ↓
Phase 1    抗體最佳化
    ├── P1-Test 1：Capture antibody titration（EpCAM+HER2+EGFR）
    ├── P1-Test 2：Detection antibody（CK-PE、CD45-APC 稀釋度）
    ├── [Hybrid 策略架構確認]
    ├── P1-Test 2b：HER2-FITC Direct vs. Indirect
    └── P1-Test 3：Cocktail 相容性
    ↓
Phase 1.5  MESF Bead 螢光校正建立（Signal Standardization）★ 新增
    ├── FITC / PE / APC 三通道校正曲線建立
    ├── 每次運行前校正 SOP 建立
    └── HER2 評分截斷值鎖定至 MESF 單位（Phase 4 前完成）
    ↓
Phase 2    系統性能驗證
    ├── Exp 1：包覆飽和 + Lot-to-Lot
    ├── Exp 2：染色特異性 + WBC 排除
    ├── Exp 3：Spike-in 線性（2/4/6/8/10/50/100 cells）+ Ficoll step recovery 驗證
    ├── Exp 4：試劑與基材穩定性（同步 Phase 0.5，T0→T96h）
    ├── Exp 5：微流道穩健性（流速 ±20%、pH 公差）★ 新增
    └── Exp 6：Carryover 攜帶污染（10,000 cells → blank × 5）★ 新增
    ↓
Phase 3    分析驗證（CLIA 要求）
    ├── 3-A：精密度矩陣（CLSI EP05-A3：批內/跨天/跨操作者/跨儀器/跨批次）★ 擴充
    └── 3-B：PBMC-level 干擾物質（血小板殘留 / 死細胞比例 / 單核球比例 / RBC 殘留）★ 重設計（血漿 HIL 不適用）
    ↓
Phase 4    HER2 評分驗證
    ├── 評分截斷值定義（基於 MESF 絕對值）
    └── 判讀者間一致性（Kappa ≥ 0.80）
```

---

# PHASE 0：Cell Line Qualification（細胞株資格確認）

---

> Phase 0 完整內容維持原版（STR、Mycoplasma、FACS、活性確認），見下方各 P0-Test。

---

# PHASE 0.5：Pre-Analytical Stability Validation — K2-EDTA

> **採血管已確認：K2-EDTA（Streck 不採用）。**  
> 本 Phase 的任務是確認 EDTA 管在不同溫度和時間條件下，CTC 回收率與 HER2 評分分類的穩定性，並定義臨床 SOP 的採樣至處理時間窗口。

## 為什麼要做，而且必須做到 T96h？

EDTA 管在離體後面臨兩個降解壓力：
1. **白血球釋放蛋白酶（主要在 RT）**：Neutrophil degranulation 釋放 elastase、MMP，可降解 EpCAM 和 CK，導致 CTC 捕獲率下降，且 HER2 細胞外域也可能被 MMP 切割，造成 HER2 表現量低估
2. **4°C 儲存的副作用**：低溫抑制蛋白酶，延長 CTC 保存，但白血球形態改變（淋巴球縮水、血小板活化聚集），可能增加非特異性捕獲背景

**為什麼需要測到 T96h？** 臨床情境中，部分患者在外院採血後需要跨城市運輸（24–48 hr），偶有延誤到 72 hr。T96h 是理論極限，其結果直接決定 SOP 中的「樣本拒絕標準」（超過 X 小時的樣本不得執行檢測）。

**最關鍵的終點不是回收率，而是 HER2 評分分類的穩定性。** 一個 HER2 3+ 的患者，如果因為樣本延遲導致 HER2 訊號衰減被評為 2+，會直接影響是否使用 HER2 靶向治療的臨床決策。

---

## Tube-Test 1：EDTA 管 CTC 穩定性——時間點 × 溫度條件

**需要什麼**：
- K2-EDTA 採血管 7.5 mL × 20 管（2 溫度條件 × 5 時間點 × 2 重複）
- SK-BR-3（HER2 3+）：spike 100 cells/管，作為 HER2 穩定性主要測試細胞
- MDA-MB-231（HER2 0）：spike 100 cells/管，確認陰性樣本不會因時間延長出現假陽性
- 同一位健康捐血者同天採血（最小化供者間差異）
- 細胞計數確認：每次 spike 前後均計數，確保實際加入數準確

**實驗矩陣**：

| 條件 | 時間點 | 重複數 | Spike Cell Line | 管數 |
|------|--------|--------|----------------|------|
| RT（20–25°C）| T0（≤1 hr）| n=3 | SK-BR-3 + MDA-MB-231 各 100 cells | 6 管 |
| RT | T24h | n=3 | 同上 | 6 管 |
| RT | T48h | n=3 | 同上 | 6 管 |
| RT | T72h | n=3 | 同上 | 6 管 |
| RT | T96h | n=2（壓力測試）| 同上 | 4 管 |
| 4°C | T0（≤1 hr）| n=3 | SK-BR-3 + MDA-MB-231 各 100 cells | 6 管 |
| 4°C | T24h | n=3 | 同上 | 6 管 |
| 4°C | T48h | n=3 | 同上 | 6 管 |
| 4°C | T72h | n=3 | 同上 | 6 管 |
| 4°C | T96h | n=2 | 同上 | 4 管 |
| **合計** | | | | **52 管** |

> 實際可依資源縮減，最低要求：RT 條件 T0/T24/T48/T72（n=3 each）+ 4°C T0/T24/T48（n=3 each）= 36 管

**步驟**：

*採血當天（Day 0）*

1. 同一捐血者於靜坐狀態採血，所有管按順序一次採足（避免後採的管因捐血者狀態改變而不同）
2. 各管立即輕旋轉混勻 5 次（讓 EDTA 與血液充分混合）
3. **Spike**：
   - SK-BR-3 和 MDA-MB-231 各自準備 1000 cells/mL 懸液（活性 ≥ 90%，計數確認）
   - 每管加入 100 μL SK-BR-3（= 100 cells）+ 100 μL MDA-MB-231（= 100 cells）
   - 輕旋轉混勻 5 次，**不可震盪**
4. 分組靜置：
   - T0 組（n=3 RT + n=3 4°C）：立即進入步驟 7，目標在採血後 60 分鐘內完成捕獲
   - T24/48/72/96 組：依設定溫度放置，**不搖晃、平放或立放均可**
   - 4°C 組：放入 4°C 冰箱，避免結凍

*各時間點*

5. 到達時間點後，RT 組讓血液在 RT 回溫 15 分鐘再處理（避免溫差影響捕獲效率）；4°C 組無需回溫
6. 立即執行 CTC 捕獲（ANA-001）——從開始捕獲到完成 IF 染色的時間應維持一致（± 30 分鐘）
7. 執行 IF 染色（ANA-004）：DAPI / CK-PE / CD45-APC / HER2-FITC，使用標準流程
8. 影像分析：
   - 計數 CK⁺/CD45⁻/DAPI⁺ cells（= CTC 計數）
   - 測量每個 CTC 的 HER2 FITC MFI（轉換為 MESF 單位，若 Phase 1.5 已完成）
   - 對每個細胞進行 HER2 評分分類（0/1+/2+/3+）

**數據分析與指標**：

| 指標 | 計算方式 | 目標 |
|------|---------|------|
| 回收率（各時間點）| 回收 cells / 100 × 100% | T0 ≥ 65%；各時間點效能保留 ≥ 70% of T0 |
| HER2 MFI 保留率 | 各時間點 MFI / T0 MFI × 100% | ≥ 80% of T0 at T24h；≥ 70% at T48h |
| **HER2 評分分類 concordance** | SK-BR-3 在各時間點評分是否仍為 3+ | **100% concordance 直到定義的最長處理時間** |
| 4°C 優於 RT 的幅度 | 兩條件在 T48/72 的回收率差 | 預期 4°C 回收率高 10–20%（視蛋白酶活性） |

**結果決策**：

```
RT 條件下，HER2 評分 100% concordance 維持到哪個時間點？
    ├── T24h → SOP 規定：採血後 24 hr 內必須開始捕獲（若常溫運輸）
    ├── T48h → SOP 規定：可延長至 48 hr（但需記錄運輸溫度）
    └── < T24h → SOP 規定：採血後 8 hr 內必須處理；否則必須 4°C 儲存

4°C 條件下 concordance 維持更久？
    ├── YES → SOP 允許：若無法在時間窗口內處理，可 4°C 短暫儲存
    └── NO → 4°C 不提供額外保護（白血球形態改變造成干擾），禁止冷藏
```

**SOP 輸出**：Phase 0.5 結果直接決定 PRE-001（採血 SOP）中的：
- 最長允許採樣到處理時間（Sample-to-Processing Time Limit）
- 允許儲存溫度（RT only / RT + 4°C 備用）
- 樣本拒絕標準（Rejection Criteria）

---

## Tube-Test 2：WBC 形態與 CD45 訊號穩定性（附加）

**目的**：確認 EDTA 管在不同時間點，WBC 形態改變不會增加 CD45⁺ debris 的非特異捕獲，從而維持 CTC 定義的純淨度

**步驟**：
1. 取同批次 unspiked EDTA 血液，各時間點（T0/T24/T48/T72 hr，RT 和 4°C 各一組）取 100 μL
2. 做 Wright-Giemsa 血塗片，光學顯微鏡觀察 WBC 完整性（有無大量破碎、核碎片）
3. 取 unspiked 血液各時間點執行完整捕獲流程（不 spike 細胞），執行 DAPI/CD45 IF 染色
4. 計數捕獲裝置上的 CD45⁺/DAPI⁺ 事件數（白血球 breakthrough）

**接受標準**：各時間點 WBC breakthrough ≤ 5 events / 7.5 mL（維持 Exp 2 的背景標準）

---

---

## Tube-Test 3：PBMC 懸液穩定性（窗口 B——Ficoll 後到捕獲前）

> **為什麼需要第二段時間窗口？** Ficoll 分離完成後，PBMC 懸液並不一定立即進入捕獲流程——實際操作中可能因儀器排程或人力安排而等待數小時。PBMC 懸液在管外以 RPMI 或 PBS 懸浮時，失去血液中的天然穩定環境（無血清、無緩衝 CO₂），死細胞比例會隨時間上升，且 CTC 可能因為缺乏細胞外基質支撐而改變表面標記表現。

**測試設計**：

| 條件 | 等待時間 | 溫度 | 重複數 |
|------|---------|------|--------|
| 窗口 B T0 | 立即（< 30 min）| 4°C | n=3 |
| 窗口 B T2h | 等待 2 小時 | 4°C | n=3 |
| 窗口 B T4h | 等待 4 小時 | 4°C | n=3 |
| 窗口 B T8h | 等待 8 小時 | 4°C | n=2 |

> 測試只做 4°C（PBMC 懸液不應在 RT 等待），T8h 為壓力測試上限。

**步驟**：

1. 採集健康捐血者 K2-EDTA 全血，各時間點條件各準備 1 管（7.5 mL）
2. 各管 spike SK-BR-3 100 cells（spike 在 Ficoll 前，模擬真實流程）
3. 依 PRE-004 執行 Ficoll 密度梯度分離，收集 PBMC 層（界面白膜層）
4. 在 PBS 或 RPMI 中重懸 PBMC，計算體積（維持一致的細胞濃度）
5. 各組依設定時間置於 4°C，到達時間點後立即執行 CTC 捕獲（ANA-001）
6. IF 染色（ANA-004），影像分析，計數 CTC

**數據分析與指標**：

| 指標 | 計算方式 | 目標 |
|------|---------|------|
| 回收率（各時間點）| 回收 cells / 100 × 100% | T2h ≥ 90% of T0；T4h ≥ 80% of T0 |
| 死細胞比例（Trypan Blue）| 在重懸後和捕獲前各計數一次 | 捕獲前死細胞 ≤ 15% |
| HER2 MFI 保留率 | 各時間點 MESF_HER2 / T0 × 100% | ≥ 85% of T0 直到定義的最長等待時間 |

**結果決策**：

```
PBMC 懸液 HER2 分類 concordance 維持到哪個時間點？
    ├── T4h → SOP 規定：Ficoll 後 4 小時內必須開始捕獲
    └── T2h → SOP 規定：Ficoll 後 2 小時內必須開始捕獲（若 T4h 失敗）
```

**SOP 輸出**：結果寫入 PRE-004（血液前處理 SOP）的「Ficoll 後樣本處理時間限制」欄位。

---

*Phase 0.5 完成後，所有後續實驗統一使用 K2-EDTA 管，遵守 Phase 0.5 定義的兩段時間窗口（窗口 A：全血等待時間；窗口 B：PBMC 等待時間）。*

---

## 為什麼要做？

你的所有驗證實驗都依賴 cell line 來模擬 CTC。如果 cell line 身份錯誤（交叉污染是業界常見問題）、有 Mycoplasma 污染、或是表現型因傳代過多而改變，你的驗證數據就沒有意義。這是所有後續實驗的地基。

---

## P0-Test 1：STR（Short Tandem Repeat）基因型鑑定

**目的**：確認每一株 cell line 的身份，排除交叉污染  
**時機**：每批新購入 cell line 使用前；每 6 個月複查一次  
**需要什麼**：
- ATCC Mycoplasma and Cell Line Authentication Service 或第三方（如 Genetica）
- 細胞 DNA 提取套件
- 送外驗服務（推薦）或院內 STR 設備

**步驟**：
1. 培養目標 cell line 至 70–80% confluency（建議 T-25 flask）
2. 用 PBS 洗滌 2 次，加 Trypsin-EDTA（0.25%）3–5 分鐘讓細胞脫附
3. 加完全培養液中止消化，300 × g 離心 5 分鐘
4. 棄上清，PBS 洗 1 次，重新離心
5. 用 DNA 提取套件（如 Qiagen DNeasy）提取 genomic DNA
6. 測定 DNA 濃度（NanoDrop），調至 20–50 ng/μL
7. 送 STR profiling 服務（附上 cell line 名稱與 ATCC 編號）
8. 收到結果後，與 ATCC STR 資料庫比對，相似度 ≥ 80% 為通過

**驗收標準**：STR profile 與 ATCC 資料庫匹配度 **≥ 80%**  
**記錄**：保存 STR 報告原件於細胞株資料夾；記錄於 Cell Line Master Log

---

## P0-Test 2：Mycoplasma 污染檢測

**目的**：Mycoplasma 污染會改變細胞表面標記表現，干擾 CTC 捕獲與染色結果  
**時機**：每批新購入時；每月例行檢查  
**需要什麼**：
- PCR-based Mycoplasma Detection Kit（如 LookOut Mycoplasma PCR Detection Kit, Sigma）
- 或 MycoAlert Luminescence-based assay（Lonza）—更快速

**步驟（PCR 法）**：
1. 收集細胞培養上清液 1 mL（不含 Trypsin，直接從培養瓶取）
2. 300 × g 離心 5 分鐘，取上清轉移至新管（避免帶入細胞碎片）
3. 依 kit 說明進行 DNA 提取或直接用上清作為模板
4. 配製 PCR 反應液（依 kit 提供的 primer 和條件）
5. 執行 PCR（通常 35 cycles）
6. 瓊脂糖膠電泳分析（1.5% gel，100V，30 分鐘）
7. 對照陽性控制（kit 提供）和陰性控制（無模板）

**步驟（MycoAlert 法，較快）**：
1. 收集細胞培養上清 100 μL
2. 加入 MycoAlert Reagent，室溫孵育 5 分鐘
3. 讀取 Luminescence（讀值 A）
4. 加入 MycoAlert Substrate，室溫孵育 10 分鐘
5. 再次讀取（讀值 B）
6. 計算 B/A 比值：< 1.0 = 陰性；≥ 1.2 = 陽性；1.0–1.2 = 重新測試

**驗收標準**：結果為陰性  
**若失敗**：立即隔離該細胞株，不可用於實驗；可嘗試 Mycoplasma 清除試劑後重新測試，或丟棄

---

## P0-Test 3：Flow Cytometry 表面標記定量（Antibody Binding Capacity）

**目的**：確認每株 cell line 的 EpCAM、CK、HER2、CD45、Vimentin 表現量符合預期，並建立「基線數值」作為後續 lot-to-lot 比較標準  
**時機**：每批 cell line 建立時；高傳代數（每 10 passages）複查  
**需要什麼**：
- Flow Cytometer（4-color 以上）
- Anti-EpCAM-APC、Anti-CK-FITC（或 PE）、Anti-HER2-PE、Anti-CD45-APC、Anti-Vimentin-FITC
- 各自的 Isotype control
- PBS + 1% BSA（FACS buffer）
- 96-well round-bottom plate（建議）

**步驟**：
1. **細胞準備**：培養至 70-80% confluency，Trypsin 處理後收集細胞，300 × g 5 min 離心，PBS 洗 1 次，計數
2. **分裝**：每個 antibody condition 需 1–5 × 10⁵ cells，分裝到 1.5 mL 管或 96-well plate
3. **Fc blocking**（減少非特異性結合）：加入 Human BD Fc Block，4°C 10 分鐘
4. **一級抗體孵育**：直接標記抗體加入（依建議劑量），4°C 避光 20–30 分鐘
5. **洗滌**：加 200 μL FACS buffer，400 × g 5 分鐘離心，棄上清，重複 2 次
6. **若需要穿透（CK/Vimentin 為細胞內標記）**：
   - 先固定：4% PFA，RT 15 分鐘
   - 洗滌 2 次
   - 穿透：Saponin-based permeabilization buffer，RT 10 分鐘
   - 加入 anti-CK 或 anti-Vimentin，RT 避光 20 分鐘
   - 洗滌 2 次
7. **重懸**：用 200–300 μL FACS buffer 重懸細胞
8. **上機分析**：至少記錄 5,000 個 events；設定 live gate（排除死細胞）
9. **計算 MFI**（Median Fluorescence Intensity）和陽性細胞百分比

**預期結果（對照文件中的 Expression Profile）**：

| Cell Line | EpCAM | CK | HER2 | CD45 | Vimentin |
|-----------|-------|-----|------|------|----------|
| MCF-7 | ≥ 90%+ | ≥ 90%+ | 10–30%+ | < 5% | 低 |
| SK-BR-3 | 60–80%+ | ≥ 90%+ | **≥ 90%+（強）** | < 5% | 低 |
| HCT116 | 40–70%+ | 50–80%+ | 10–40%+ | < 5% | 中 |
| MDA-MB-231 | < 20%+ | 30–60%+ | **< 10%（弱）** | < 5% | ≥ 70%+ |
| Jurkat/K-562 | < 5% | < 5% | < 5% | **≥ 95%+** | 中 |

**驗收標準**：各指標符合上表範圍，且 SK-BR-3 HER2 MFI / MDA-MB-231 HER2 MFI **比值 ≥ 5**  
**記錄**：保存 flow data（.fcs 檔）；記錄 MFI 和 % positive 於 Cell Line Qualification Log

---

## P0-Test 4：活性確認（Viability & Passage Control）

**目的**：死細胞會造成非特異性抗體結合，干擾所有實驗結果  
**時機**：每次實驗使用前  
**方法**：

**Trypan Blue 排除法（快速）**：
1. 取 10 μL 細胞懸液 + 10 μL 0.4% Trypan Blue，輕輕混勻，靜置 1 分鐘
2. 取 10 μL 加入 hemocytometer
3. 計數：透明（活）= 活細胞；藍色（染色）= 死細胞
4. 活性 = 活細胞數 / 總細胞數 × 100%

**AO/PI 法（若有螢光顯微鏡）**：
1. 取 10 μL 細胞 + 10 μL AO/PI 工作液
2. 螢光顯微鏡觀察：綠色螢光 = 活細胞；紅色 = 死細胞
3. 計算比例

**驗收標準**：活性 **≥ 90%**，傳代數 **≤ 20**  
**若失敗**：使用較早傳代的凍存庫存；記錄傳代數於 Cell Line Master Log

---

# PHASE 1：抗體最佳化（Antibody Optimization）

## 為什麼要做？

抗體的工作濃度不是照廠商說明書就好，必須在你自己的系統（你的基材、你的血液樣本、你的顯微鏡）中驗證最佳濃度。濃度太高 → 背景噪訊高；太低 → 訊號弱、靈敏度差。

---

## P1-Test 1：Capture 抗體 Titration（包覆最佳化）

**目的**：找到 capture antibody cocktail（EpCAM + HER2 + EGFR）的最佳包覆濃度，達到最大捕獲效率且 lot-to-lot CV < 15%

**參考文件**：R&D Plan Experiment 1——測試 1、5、10 μg/mL

**需要什麼**：
- Biotinylated anti-EpCAM（R&D BAF960）
- Biotinylated anti-HER2（R&D BAF1129）
- Biotinylated anti-EGFR（R&D BAF231）
- Streptavidin-coated substrate（你的微流道/濾器/chip）
- PBS with 1% BSA（阻斷用）
- MCF-7 + SK-BR-3 cells（spiking 測試用）
- 健康捐血者 EDTA 全血

**步驟**：

*第一步：製備抗體包覆基材*

1. 在 PBS 中配製 biotinylated antibody cocktail 工作液，分別準備 3 種濃度：
   - C1：EpCAM 1 μg/mL + HER2 1 μg/mL + EGFR 1 μg/mL
   - C2：EpCAM 5 μg/mL + HER2 5 μg/mL + EGFR 5 μg/mL
   - C3：EpCAM 10 μg/mL + HER2 10 μg/mL + EGFR 10 μg/mL
2. 將各濃度 antibody 液加至 streptavidin 基材上（依你的裝置規格決定體積和孵育時間，通常 RT 1 小時或 4°C 過夜）
3. 用 PBS-T（0.05% Tween-20）洗滌 3 次，去除未結合抗體
4. 加入 Blocking solution（PBS + 1% BSA）RT 阻斷 30 分鐘
5. PBS 洗 2 次

*第二步：Spike-in 測試*

6. 準備 MCF-7 和 SK-BR-3 細胞懸液（確認活性 ≥ 90%，計數準確）
7. 配製 100 cells / 7.5 mL 全血的 spike（計算方式：取計數後細胞懸液，稀釋至約 13 cells/mL，取 7.5 mL 加入採血管，輕輕旋轉混勻）
8. 立即將 spiked 血液加入包覆好的捕獲裝置，依 ANA-001 流程執行捕獲
9. 捕獲後，依 ANA-004 IF 染色流程執行（包含 DAPI/CK/CD45/HER2）
10. 影像分析：計數 CK+/CD45-/DAPI+ 的細胞數（= 回收到的 CTC）

*第三步：數據分析*

11. 計算各濃度的回收率：回收率 = 計數到的 cells / spiked cells × 100%
12. 繪製「回收率 vs. 包覆濃度」曲線，找飽和平台
13. 計算每個濃度的 CV（3 重複）：CV = SD / mean × 100%
14. 選擇：在達到飽和平台且 CV < 15% 的最低濃度 = 最佳化濃度

**驗收標準**：
- Lot-to-lot CV < **15%**
- 在最佳濃度下，MCF-7 回收率 ≥ **70%**，SK-BR-3 回收率 ≥ **60%**

**注意**：若三個濃度都未達飽和，加測 20 μg/mL；若 1 μg/mL 已飽和，往下加測 0.5 μg/mL

---

## P1-Test 2：Detection 抗體 IF 染色最佳化（Antibody Titration for Staining Panel）

**目的**：找到最佳的 IF 染色抗體稀釋度，使得 Signal-to-Noise Ratio（SNR）最大化

**需要什麼**：
- Anti-HER2（用於 IF，須確認與 capture antibody 為不同 epitope）
- Anti-Pan-CK（AE1/AE3 或 CAM5.2）
- Anti-CD45
- 以上各自的螢光二抗（或直接標記一抗）
- DAPI
- SK-BR-3（HER2+++）、MDA-MB-231（HER2-）、Jurkat（CD45+）
- 標準蓋玻片或你的捕獲裝置

**步驟**：

*利用直接染色法（不跑捕獲，加快優化速度）*

1. **準備各 cell line**：培養至 70-80% confluency，Trypsin 收集，計數，調至 5 × 10⁴ cells/mL
2. **製備染色對照陣列**：在每個 well/蓋玻片上加 10⁴ cells，離心沉降或 Cytospin
3. **固定**：4% PFA，RT 15 分鐘，PBS 洗 3 次
4. **穿透**：0.1% Triton X-100 in PBS，RT 10 分鐘，PBS 洗 3 次
5. **阻斷**：5% Normal Serum（與二抗物種一致），RT 30 分鐘
6. **一抗稀釋梯度配製**：

   以 Anti-HER2 為例，準備：
   - 1:50、1:100、1:200、1:500、1:1000 in 1% BSA/PBS
   
   同樣操作：Anti-CK（AE1/AE3）、Anti-CD45

7. **一抗孵育**：各稀釋度各一個 replicate，4°C 過夜（或 RT 1 小時）
8. **PBS 洗 3 次**（每次 5 分鐘）
9. **二抗孵育**：按廠商推薦稀釋（通常 1:500–1:1000），RT 避光 45 分鐘
10. **PBS 洗 3 次**（避光）
11. **DAPI**：300 nM，RT 5 分鐘
12. **PBS 洗 2 次**，封片
13. **影像分析**：

    對每個稀釋度測量：
    - **Signal**：CK+/HER2+ cells 的平均螢光強度（MFI）
    - **Background**：相同通道在 CD45+ Jurkat cells 上的 MFI（不應有 CK/HER2 訊號）
    - **SNR** = Signal MFI / Background MFI

14. **選擇最佳稀釋度**：SNR 最高且訊號在線性範圍內的稀釋度

**驗收標準**：
- **HER2（SK-BR-3 vs MDA-MB-231）**：SNR ≥ **5**（SK-BR-3 HER2 MFI / MDA-MB-231 HER2 MFI）
- **CK**：CK+ cells ≥ 90% 陽性率（SK-BR-3、MCF-7、HCT116），Jurkat CK < 5%
- **CD45**：Jurkat ≥ 95% CD45+，SK-BR-3/MCF-7 CD45 < 5%

---

## 偵測策略架構：Hybrid 混合策略（Platform-Level Decision）

> **本節為平台層級的設計決策，優先於所有 P1-Test 執行。所有後續抗體最佳化測試（P1-Test 2、2b、3）均在此架構下進行。**

---

### 確認的 Panel 架構

| Channel | 標的 | 螢光團 | 策略 | 理由 | 狀態 |
|---------|------|--------|------|------|------|
| Ch 1（UV） | 細胞核（DAPI）| DAPI | 直接加入（非抗體）| — | ✅ 確認 |
| Ch 2（Green）| **HER2** | **FITC** | **待定（Direct 或 Indirect）** | FITC 通道自體螢光高，低表現細胞訊號可能不足，需測試才能決定 | ⬜ P1-Test 2b 決定 |
| Ch 3（Orange）| **Pan-CK** | **PE** | **Direct conjugated** | CK clone（AE1/AE3）為 Mouse IgG1，與 CD45 同種；若用 Indirect，鼠源二級抗體無法區分 CK 和 CD45 通道 | ✅ 確認 |
| Ch 4（Far-Red）| **CD45** | **APC** | **Direct conjugated** | 同上；APC 通道背景最低，Direct 訊號足夠 | ✅ 確認 |

---

### 策略設計原則

**為什麼 CK 和 CD45 必須用 Direct？**

Anti-CK（AE1/AE3）和 Anti-CD45（2B11+PD7/26）都是 **Mouse IgG1**。若同時採用 Indirect 策略，加入鼠源二級抗體（anti-mouse IgG）時，它會同時結合兩支一級抗體，無法分辨 Ch 3（CK-PE）和 Ch 4（CD45-APC），導致雙通道交叉染色，CTC 定義（CK⁺/CD45⁻）完全失效。Direct conjugated 是唯一可行解。

**為什麼 HER2 留待測試？**

HER2 評分是 CDx 的核心判讀目標，特別是 1+/2+ 低表現細胞的識別決定了臨床靈敏度。FITC 通道在 488nm 激發，細胞自體螢光最強，背景噪訊比 PE/APC 高。若 Direct（Anti-HER2-FITC）的 Signal-to-Noise Ratio 足以區分 1+ 和 0，則優先採用（步驟簡單、可重複性高）；若不足，則採用 Indirect（anti-HER2 unconjugated + anti-rabbit-FITC 二級），在同一 FITC 通道得到 3–10× 訊號放大。

---

### Hybrid 策略的兩種最終形態

**形態 1：若 P1-Test 2b → Direct 通過**

```
DAPI                        直接加入
Anti-HER2-FITC              Direct conjugated（一步）
Anti-CK-PE                  Direct conjugated
Anti-CD45-APC               Direct conjugated
────────────────────────────────────────────
一級抗體混合液（4 成分）→ 一次孵育 → 洗滌 → DAPI → 封片
共 N 個步驟：最簡化版本
```

**形態 2：若 P1-Test 2b → Indirect 必要**

```
DAPI                        直接加入
Anti-HER2（unconjugated）   一級抗體（Rabbit）
Anti-CK-PE                  Direct conjugated（混入一級抗體液）
Anti-CD45-APC               Direct conjugated（混入一級抗體液）
    ↓ 洗滌
Anti-rabbit-FITC            二級抗體（只針對 HER2）
    ↓ 洗滌
DAPI → 封片
────────────────────────────────────────────
分兩步孵育，CK 和 CD45 在第一步完成，HER2 需等二級抗體步驟
```

> 兩種形態的螢光通道分配（DAPI / FITC / PE / APC）完全相同，影像分析 pipeline 不需改動。

---

### P1-Test 2b 是本架構的唯一待決測試

CK 和 CD45 已確認策略，不需額外比較測試。**P1-Test 2b 是整個 Hybrid 策略中唯一尚未決定的分支**，其結果直接寫入 ANA-004 SOP Section 7.3、7.4、9.4、9.6，鎖定最終操作流程。

---

## P1-Test 2b：HER2-FITC 偵測策略——Direct vs. Indirect 比較測試

### 背景與問題定義

**已確認**：螢光 panel 為 DAPI / HER2-**FITC** / CK-**PE** / CD45-**APC**

**已確認**：CK-PE 和 CD45-APC 均採 **Direct conjugated**（兩者 clone 均為 Mouse IgG1，若用二級抗體會交叉反應，Direct 是唯一合理選擇）

**待測試**：HER2-FITC 要用哪種形式？

| 策略 | 操作 | FITC 通道來源 |
|------|------|--------------|
| **A：Direct** | Anti-HER2-FITC 直接加入（一步完成）| Anti-HER2 抗體本身帶 FITC |
| **B：Indirect** | Anti-HER2（unconjugated）→ Anti-rabbit-FITC 二級抗體（多個二級結合一個一級，訊號放大）| Anti-rabbit-FITC 二級抗體 |

**測試核心問題**：你的螢光顯微鏡在 FITC 通道，Direct 策略能否區分 HER2 1+（MCF-7）和 HER2 0（MDA-MB-231）？

- 若 **Direct 的 SNR 足夠** → 採用 Direct，步驟少，背景低，操作更簡單
- 若 **Direct 訊號太弱**，HER2 1+/2+ 淹沒在背景裡 → 採用 Indirect，用二級抗體在 FITC 通道放大訊號

### 為什麼 FITC 通道特別需要測試？

FITC 是光穩定性較低的螢光團（容易淬滅），且組織/細胞的自體螢光（autofluorescence）在 488nm 激發時最強，背景噪訊比 PE 和 APC 通道更高。HER2 low-expression 細胞的訊號本來就弱，加上 FITC 的背景問題，Direct 的 SNR 可能不夠。這個測試的答案會決定你的 SOP 複雜度。

### 測試步驟

**材料**：
- SK-BR-3（HER2 3+，強陽性）
- MCF-7（HER2 1+，弱陽性）——**最關鍵的判別點**
- MDA-MB-231（HER2 0，陰性背景）
- Anti-HER2-FITC（Direct 用，購買已標記版本）
- Anti-HER2 unconjugated（Rabbit IgG，Indirect 用）
- Anti-Rabbit IgG-FITC（Indirect 用二級抗體）
- Anti-CK-PE（Direct，全程使用）
- Anti-CD45-APC（Direct，全程使用）
- DAPI

**每組樣本**：3 株 cell line × 2 策略 × n=3 重複 = 18 個染色樣本

**步驟 1–3：共用前處理（兩種策略相同）**

1. 各 cell line 培養至 70–80% confluency，Trypsin 收集，計數，活性確認 ≥ 90%
2. 每組取 1–5 × 10⁴ cells，沉降至蓋玻片（poly-L-lysine 包覆）或直接塗佈
3. 固定：4% PFA，RT 15 分鐘；PBS 洗 3 次（5 分鐘/次）
4. 穿透：0.1% Triton X-100，RT 10 分鐘；PBS 洗 3 次
5. 阻斷：5% Normal Goat Serum in PBS，RT 30 分鐘

**步驟 4A：策略 A（Direct Anti-HER2-FITC）**

6A. 配製一級抗體混合液：
    - Anti-HER2-FITC（工作濃度，依廠商建議）
    - Anti-CK-PE（工作濃度）
    - Anti-CD45-APC（工作濃度）
    - 稀釋於 1% BSA/PBS，共 100 μL/樣本
7A. 加至細胞，4°C 過夜（或 RT 1.5 小時），避光
8A. PBS 洗 3 次，避光
9A. 加 DAPI（300 nM），RT 5 分鐘
10A. PBS 洗 2 次，封片 → 進入影像分析

**步驟 4B：策略 B（Indirect Anti-HER2 + Anti-rabbit-FITC）**

6B. 配製一級抗體混合液：
    - Anti-HER2 unconjugated（Rabbit，工作濃度）
    - Anti-CK-PE（工作濃度）
    - Anti-CD45-APC（工作濃度）
    - 稀釋於 1% BSA/PBS，共 100 μL/樣本
7B. 加至細胞，4°C 過夜，避光
8B. PBS 洗 3 次，避光
9B. 配製二級抗體液：Anti-Rabbit IgG-FITC（1:500–1:1000），100 μL/樣本
10B. 加至細胞，RT 避光 45 分鐘
11B. PBS 洗 3 次，避光
12B. 加 DAPI（300 nM），RT 5 分鐘
13B. PBS 洗 2 次，封片 → 進入影像分析

**影像擷取（兩組策略用完全相同設定）**：
- 固定曝光時間（不可 auto-expose）
- 固定增益（Gain）
- 固定物鏡（建議 40× 或 63×）
- 每個樣本拍攝 ≥ 10 個視野，選取含細胞的區域

**數據分析**：

對每個細胞測量 FITC channel MFI（排除 DAPI- 的死細胞），計算：

| 指標 | 計算方式 | 策略 A 目標 | 策略 B 目標 |
|------|---------|------------|------------|
| SNR（高表現）| SK-BR-3 MFI ÷ MDA-MB-231 MFI | ≥ 5 | ≥ 8 |
| 低表現辨別力 | MCF-7 MFI vs MDA-MB-231 MFI（獨立樣本 t-test）| p < 0.05（**關鍵**）| p < 0.01 |
| 背景（二抗空白）| 僅加二級抗體的 MDA-MB-231 MFI | N/A | ≤ 陰性 MFI 的 15% |
| 重複性 | FITC MFI 的 CV（n=3）| ≤ 15% | ≤ 15% |

**決策樹**：

```
策略 A（Direct Anti-HER2-FITC）測試：
MCF-7（1+）vs MDA-MB-231（0）, p < 0.05 且 SNR(3+ vs 0) ≥ 5？
    │
    ├── YES → 採用 Direct（策略 A）
    │         ✓ 更簡單、步驟少、背景低
    │         ✓ 在 SOP 中刪去二級抗體步驟（Section 9.6）
    │
    └── NO  → 採用 Indirect（策略 B）
              ✓ 二級抗體在 FITC 通道放大 HER2 訊號
              ✓ CK-PE 和 CD45-APC 仍為 Direct（不受影響）
              ✓ 在 SOP 中保留 Section 9.6（Anti-rabbit-FITC 二級抗體）
```

**結果記錄**：完成後填入 Form P1-Test-2b，附影像截圖和統計數據，Technical Supervisor 簽核，更新 ANA-004 SOP Section 7.3–7.4 和 Section 9.4–9.6

---

## P1-Test 3：Multiple antibody cocktail 混合相容性確認

**目的**：確認同時加入 3 種 capture antibody 不會相互干擾（競爭結合 streptavidin、空間位阻）

**步驟**：
1. 設計 4 組實驗：
   - 組 A：只有 anti-EpCAM（1 μg/mL，最佳化後濃度）
   - 組 B：只有 anti-HER2（1 μg/mL）
   - 組 C：只有 anti-EGFR（1 μg/mL）
   - 組 D：三者 cocktail（各 1 μg/mL，或最佳化濃度）
2. 各組分別包覆捕獲裝置（依 P1-Test 1 步驟）
3. 用 SK-BR-3（高 HER2/中 EpCAM）和 MDA-MB-231（低 EpCAM/EpCAM-）spike 測試
4. 比較各組回收率
5. 若 cocktail 組（D）的回收率 ≥ 單一抗體組的最高回收率 = 無干擾，可用 cocktail

**驗收標準**：cocktail 組回收率不低於最佳單一抗體組的 **85%**

---

# PHASE 1.5：MESF Bead 螢光校正建立（Signal Standardization Infrastructure）★ 新增

> **執行時機**：Phase 1 全部抗體最佳化完成（最佳稀釋度已確認）且 P1-Test 2b 決策後，Phase 2 Exp 3 Spike-in 線性測試前。MESF 校正建立後，所有後續 MFI 數據均須轉換為 MESF 單位報告。

## 為什麼要做 MESF 校正？

傳統 IF 影像分析記錄的是「灰度值（Gray Value）」或「任意螢光單位（Arbitrary Fluorescence Unit, AFU）」，數值受以下因素影響，每次測量結果不可直接比較：

| 影響因素 | 造成的問題 |
|---------|-----------|
| 顯微鏡光源強度衰退 | 同樣細胞，6 個月後 MFI 變低 |
| CCD/CMOS 感測器增益設定 | 不同人設定不同，數值無法比較 |
| 物鏡批次差異 | 不同台顯微鏡拍出不同 AFU |
| 濾光片老化 | 透射率隨時間改變 |
| 抗體批次螢光 F/P ratio 差異 | 新批次 FITC 標記數量不同，同一細胞 MFI 可能差 20–30% |

**MESF（Molecules of Equivalent Soluble Fluorochrome）** 是以「相當於多少個游離螢光團分子的訊號」來表達螢光量，是與儀器設定無關的絕對物理單位。透過 MESF 校準珠（含已知 MESF 值的離散螢光強度等級），可建立 AFU → MESF 的線性轉換方程式。

**對 HER2 CDx 的意義**：
- HER2 評分截斷值（0 vs 1+ vs 2+ vs 3+）以 MESF 單位定義，不會因換台顯微鏡或更換抗體批次而漂移
- 跨時間（年度校正）、跨儀器（雙儀器系統）、跨批次（季度試劑更換）的數據可直接比較
- 這是 CLIA/CAP 長期 QC 管控的基礎，Phase 4 HER2 評分截斷值定義的前提

---

## Ph1.5-Test 1：MESF 校正曲線建立（FITC / PE / APC 三通道）

**需要什麼**：
- **MESF 校準珠**（以下三通道需分別購買，或選購多通道版本）：
  - FITC 通道：Quantum FITC MESF Kit（Bangs Laboratories, catalog #FCSC-905）
  - PE 通道：Quantum PE MESF Kit（Bangs Laboratories, catalog #FCSC-908）
  - APC 通道：Quantum APC MESF Kit（Bangs Laboratories, catalog #FCSC-911）
  - 替代選項：Ultra Rainbow Calibration Particles（Spherotech, URCP-100-2H）——多通道一管校正，較經濟
- 螢光顯微鏡（你的主要偵測系統，若有 ≥ 2 台均需測試）
- 影像分析軟體（ImageJ、CellProfiler 或專用軟體）
- Excel 或 Python（計算線性迴歸用）

> **重要**：不同廠牌的 MESF 珠使用不同基準定義，整個平台生命週期須購買相同廠牌以確保長期可比性。

**步驟（以 FITC 通道為例，PE 和 APC 步驟相同，僅換對應珠和濾光片）**：

*試驗前準備*

1. 從冰箱取出 MESF 珠，在 RT 平衡 15 分鐘
2. 依 kit 說明以 1:100 或 1:1000 稀釋至 PBS 中（依珠子濃度而定）
3. **充分震盪再稀釋**（珠子容易沉澱）
4. 取 5–10 μL 稀釋液滴在蓋玻片上，立即封片（或使用液態 chamber 進行活態測量）

*影像擷取（關鍵：所有設定必須固定並記錄）*

5. **在擷取前固定以下所有參數**，記錄於 Form Ph1.5-F1：
   - 物鏡倍率（建議 40×）
   - 曝光時間（Exposure time）：設定為整個 Phase 驗證期間的「標準曝光值」
   - 增益（Gain）
   - 濾光片組合（Filter cube 編號）
   - 光源強度百分比
6. 拍攝包含所有 MESF 強度等級的珠子群（校準珠組通常含 5–6 個不同 MESF level）
7. 每台顯微鏡拍攝 ≥ 5 個視野，每個視野確保各 MESF level 均有 ≥ 20 個珠子

*數據分析——建立校正方程式*

8. 在影像分析軟體中，對每個 MESF level 的珠群畫 ROI，計算平均 MFI（Mean Intensity）
9. 建立數據表：

   | MESF Level | 廠商標定 MESF 值（X）| 測量 MFI（Y）|
   |-----------|---------------------|-------------|
   | Level 1（最暗）| X₁（廠商提供）| Y₁（儀器讀值）|
   | Level 2 | X₂ | Y₂ |
   | Level 3 | X₃ | Y₃ |
   | Level 4 | X₄ | Y₄ |
   | Level 5（最亮）| X₅ | Y₅ |

10. 以廠商 MESF 值（X）為橫軸、儀器 MFI（Y）為縱軸，執行**線性迴歸**：
    - 方程式：`Y = a × X + b`（a = 斜率，b = 截距）
    - 計算 R²
11. 反解得到 **MESF 轉換公式**：`MESF = (MFI − b) / a`
12. 對 PE 和 APC 通道重複步驟 5–11，得到三個通道各自的校正方程式

**驗收標準（每通道）**：

| 指標 | 要求 |
|------|------|
| 線性 R² | **≥ 0.99** |
| 最低 MESF level 偵測 CV | ≤ 10%（n ≥ 20 珠）|
| 各 MESF level MFI within-day CV | ≤ 10% |

---

## Ph1.5-Test 2：跨儀器 MESF 一致性驗證（若有 ≥ 2 台顯微鏡）

**目的**：確認兩台儀器在各自 MESF 校正後，報告相同細胞的 MESF 值一致（< 5% 差異）

**步驟**：
1. 同一天，同一操作者，在兩台顯微鏡各自執行 Ph1.5-Test 1（各建立自己的校正方程式）
2. 準備 3 批 SK-BR-3 細胞（同一 passage，同一 IF 染色批次）
3. 將同一批 IF 製片分別放到兩台儀器上測量（固定設定）
4. 各儀器用自身校正方程式將 MFI 轉換為 MESF
5. 比較兩台儀器的 SK-BR-3 HER2 FITC MESF 值

**驗收標準**：兩台儀器對相同製片的 HER2 MESF 差異 **< 5%**（CV < 5%）

---

## Ph1.5-Test 3：週期性校正維護計畫

| 頻率 | 動作 | 三通道 |
|------|------|--------|
| **每批次運行前** | 用 Level 3 中間點 MESF 珠做單點確認：MFI 需在校正方程式 ±10% 範圍內 | FITC / PE / APC |
| **每週一次** | 完整 5-level 校正曲線，更新 a 和 b 值 | 同上 |
| **每次換抗體批次後** | 立即做完整 MESF 校正 + P0-Test 3 FACS 確認 | 更換通道對應 |
| **每次儀器維修或燈泡更換後** | 立即做完整 MESF 校正，確認斜率 a 漂移 < 15% | 三通道 |

**長期 QC 控制圖**：
- Y 軸：每週 MESF 校正的斜率 a（FITC / PE / APC 各一張 Levey-Jennings chart）
- 警告線：±2 SD；控制線：±3 SD
- 連續 3 點同向漂移或超出 ±2 SD → 觸發重新校正

---

## Ph1.5 完成確認清單

完成 Phase 1.5 後須確認以下全部項目，才可進入 Phase 2 Exp 3 Spike-in 線性測試：

- [ ] FITC 通道 MESF 方程式（a, b, R²）已建立並記錄於 Form Ph1.5-F1
- [ ] PE 通道 MESF 方程式已建立並記錄
- [ ] APC 通道 MESF 方程式已建立並記錄
- [ ] 若有雙儀器：跨儀器 MESF 一致性 < 5%（Ph1.5-Test 2 通過）
- [ ] 每批次運行的單點 MESF 確認流程已寫入 QC-001（日常 QC SOP）
- [ ] 週期校正計畫已寫入 LAB-004（儀器管理 SOP）

> Phase 4 HER2 評分截斷值定義（P4-Test 1）必須在此 MESF 基礎建立後進行。所有截斷值以 MESF 單位表達（例如：HER2 3+ ≥ X MESF_FITC，2+ ≥ Y MESF_FITC），確保截斷值不隨時間或儀器漂移。

---

# PHASE 2：系統性能驗證（Platform Performance Validation）

以下四個實驗直接對應 R&D Plan 中的 Experiment 1–4，但補充完整步驟。

---

## Exp 1：抗體包覆飽和度與 Lot-to-Lot 一致性

**（注意：此 Exp 是 Phase 1 的延伸，重點在 lot-to-lot 比較）**

**目的**：確認不同批次（Lot）的 biotinylated capture antibody 在相同包覆濃度下，表現一致

**步驟**：
1. 購入至少 2 個不同 Lot 的各 capture antibody
2. 依 P1-Test 1 的最佳化濃度分別包覆裝置（Lot A 和 Lot B 各 n=3）
3. 各用 100 cells SK-BR-3 spike-in 到 7.5 mL 血液，執行完整 pipeline
4. 比較 Lot A 和 Lot B 的平均回收率

**驗收標準**：Lot-to-Lot 回收率差異 **< 15%**（不同 Lot 間的 CV < 15%）

---

## Exp 2：染色特異性與白血球排除驗證

**目的**：確認 IF panel 不會把白血球（WBC）誤判為 CTC（假陽性來源）

**實驗 2A：WBC 純培養染色**

1. 培養 Jurkat 或 K-562（CD45+ 白血球 model cell line）
2. 調整至 1 × 10⁶ cells/mL，取 100 μL（= 10⁵ cells）加至蓋玻片或捕獲裝置
3. 依標準 IF 流程染色（固定/穿透/阻斷/一抗/二抗/DAPI）
4. 影像分析：

   **預期**：
   - DAPI+（有核）：≥ 99%
   - CD45+：≥ 95%
   - CK+：< 5%（若 > 5%，需重新優化阻斷條件或換抗體）
   - HER2+：< 5%

5. 驗收標準：**CD45⁺ ≥ 95%，CK⁺ < 5%，HER2⁺ < 5%**

**實驗 2B：未加細胞的健康血液（Unspiked Blood）**

1. 取健康捐血者全血 7.5 mL（EDTA），**不加任何 cell line**
2. 執行完整 pipeline（捕獲 → IF 染色）
3. 影像分析：計數所有 CK+/CD45-/DAPI+ 事件

   **預期**：正常情況下，健康人血液中 CTC 極少，此為「系統背景值」

4. 驗收標準：**CK⁺/CD45⁻ 事件 < 5 per 7.5 mL blood**（參考 CellSearch 系統標準）

**實驗 2C：二級抗體空白對照**

1. 取 SK-BR-3 在蓋玻片上固定
2. **跳過一級抗體**，直接加二級抗體、DAPI
3. 所有通道影像分析

   **預期**：所有螢光通道訊號 ≤ 背景 + 2 SD（相較於完全省略抗體的細胞）

---

## Exp 3：線性與回收率 Spike-in 實驗（AMR & LOD 建立）

**目的**：建立 Analytical Measurement Range（AMR），確認系統能在 1–500 cells/7.5 mL 範圍內線性地回收細胞；找出 Limit of Detection（LOD）

**這是最重要的驗證實驗，是 CLIA 法規核心要求之一**

**需要什麼**：
- 4 種 cell line：MCF-7、SK-BR-3、HCT116、MDA-MB-231（各自代表不同 EMT 程度）
- 健康捐血者 EDTA 全血（同一個人，同一天採血，減少批次差異）
- 精確細胞計數設備（hemocytometer + Trypan Blue；或 LUNA-FL 自動計數儀）

**步驟**：

*細胞懸液準備（Spike 母液）*

1. 培養 4 株 cell line 至 70-80% confluency，確認活性 ≥ 90%
2. Trypsin 收集，PBS 洗 2 次
3. 計數：使用 hemocytometer，每個 cell line 計數 2 次（取平均），確認計數重複性
4. 調整至 **1000 cells / mL**（母液 stock）
5. 系列稀釋至下表各濃度：

   | Spike Level | Target cells in 7.5 mL | 稀釋至（cells/mL）| 取血量 | 重複數 |
   |------------|----------------------|-----------------|--------|--------|
   | **L1** | **2 cells** | 0.267 cells/mL | 7.5 mL | **n = 10**（Poisson 統計需求）|
   | **L2** | **4 cells** | 0.533 cells/mL | 7.5 mL | n = 5 |
   | **L3** | **6 cells** | 0.800 cells/mL | 7.5 mL | n = 5 |
   | **L4** | **8 cells** | 1.067 cells/mL | 7.5 mL | n = 5 |
   | **L5** | **10 cells** | 1.333 cells/mL | 7.5 mL | n = 3 |
   | **L6** | **50 cells** | 6.667 cells/mL | 7.5 mL | n = 3 |
   | **L7** | **100 cells** | 13.33 cells/mL | 7.5 mL | n = 3 |

   > **設計理由**：L1–L5（2–10 cells）是 CDx 臨床最關鍵的範圍，低密度細分可精確定義 LOD 和 LOQ。L6–L7（50/100 cells）用於確認線性上限。L1 因 Poisson 分布（平均值小時，每管實際 cell 數隨機波動），需 n=10 才能得到統計上有意義的 LOD 估計。

   **Spike 濃度稀釋方法（精確操作）**：
   - 母液：準備 1000 cells/mL 細胞懸液（計數確認後稀釋）
   - 工作液：從母液系列稀釋至各目標濃度
   - 最低濃度（L1，0.267 cells/mL）：需先稀釋至 10 cells/mL，再取 200 μL 稀釋至 7.5 mL — 或使用有限稀釋法（limiting dilution）逐步確認
   - **每次 spike 後必須用同批次剩餘細胞懸液做計數確認**（驗證加入的實際細胞數）

*Spike 操作（Spike 在 Ficoll 前——模擬真實臨床情境）*

> **Spike 時機說明**：Spike 必須在 Ficoll 分離前加入全血，以模擬 CTC 存在於全血中的真實狀態（不同密度的 CTC 在 Ficoll 層分佈特性各異，若 Spike 在 Ficoll 後則無法捕捉此步驟的損失）。

6. 採集健康捐血者 7.5 mL K2-EDTA 全血
7. 將計算好的細胞體積（通常 10–100 μL）直接加入採血管底部，蓋好
8. **輕輕旋轉混勻 5–10 次**（不可震盪，避免細胞破裂）
9. 室溫靜置 5 分鐘

*Ficoll PBMC 分離*

10. 依 PRE-004 標準流程執行 Ficoll 密度梯度分離（例如 Ficoll-Paque PLUS, 密度 1.077 g/mL）：
    a. 將 7.5 mL spiked 全血小心鋪於等體積 Ficoll 上方（不可混合）
    b. 400 × g，RT，30 分鐘，無加速/無剎車（Brake = 0）
    c. 吸取界面白膜層（PBMC 層，含 CTC）
    d. PBS 洗滌 2 次（300 × g，10 分鐘），去除殘餘 Ficoll 和血小板
    e. 計算回收體積，重懸於適當體積 PBS 或 RPMI
11. **立即計數** PBMC 懸液中的細胞密度和活性（作為「Ficoll 後輸入量」基準）
12. 在 **Ficoll 完成後 2 小時內**開始執行捕獲流程（依窗口 B SOP 要求）

*捕獲與染色*

13. 依 ANA-001（CTC 捕獲 SOP）執行（輸入為 PBMC 懸液，非全血）
14. 依 ANA-004（IF 染色 SOP）執行（DAPI/CK/CD45/HER2）
15. 影像分析：計數所有 DAPI+/CK+/CD45- cells

*數據計算*

16. **總回收率** = 最終計數到的 cells / 最初 spiked cells × 100%
17. **CV（每個 Spike level）** = SD / mean × 100%（n=3 重複）
18. **線性分析**：以 spiked cells 為 X 軸，recovered cells 為 Y 軸，線性迴歸
    - 計算 R²（相關係數）
    - 計算斜率（slope）
19. **LOD 計算**：在 n=10 重複中，≥ 8 次能回收到 ≥ 1 cell 的最低 Spike level

---

### Exp 3B：Ficoll Step Recovery 子實驗（步驟回收率分析）

**目的**：將「Ficoll 分離損失」和「微流道捕獲損失」分開量化，確認兩個步驟各自的瓶頸

**為什麼要分開測？**

總回收率 = Ficoll 回收率 × 微流道捕獲效率

如果總回收率低，你需要知道問題出在哪個步驟才能針對性改善。某些 CTC（特別是間質型、EpCAM-low 的 MDA-MB-231）密度接近 RBC（1.08–1.10 g/mL），可能沉入 Ficoll 下層，根本不在 PBMC 白膜層中。

**設計**：使用 SK-BR-3 和 MDA-MB-231 各 100 cells，3 組比較：

| 組別 | Spike 時機 | 測量目標 |
|------|-----------|---------|
| 組 A（對照）| Spike before Ficoll → Ficoll → CTC 捕獲 | 總回收率 |
| 組 B | Spike after Ficoll → CTC 捕獲（跳過 Ficoll 步驟）| 微流道捕獲效率（單獨）|
| 組 C（計算）| A / B | Ficoll step recovery = 總回收率 / 微流道捕獲效率 |

**步驟**：
1. 準備同批次 SK-BR-3 和 MDA-MB-231 懸液（活性 ≥ 90%，計數確認）
2. **組 A**：Spike 100 cells 入 7.5 mL 全血 → Ficoll 分離 → 收集 PBMC 層 → CTC 捕獲 → 計數（n=5）
3. **組 B**：取空白 7.5 mL 全血做 Ficoll 分離 → 收集 PBMC 層 → **此時** Spike 100 cells 入 PBMC 懸液 → CTC 捕獲 → 計數（n=5）
4. 計算各組回收率，以 B 除 A 得到 Ficoll step recovery

**驗收標準**：

| Cell Line | Ficoll Step Recovery | 說明 |
|-----------|---------------------|------|
| SK-BR-3（高上皮，密度接近 lymphocyte）| **≥ 70%** | 上皮型 CTC 應在白膜層 |
| MCF-7（高上皮）| **≥ 70%** | 同上 |
| MDA-MB-231（高間質，密度接近 RBC）| **≥ 30%**（觀察值）| 間質型 CTC 可能部分沉入 Ficoll 下層；此為系統限制，需在 LOD/LOQ 和 Limitations 中說明 |

> 若 MDA-MB-231 的 Ficoll step recovery 過低（< 30%），這是技術平台的固有限制，不影響 HER2+ 上皮型 CTC（SK-BR-3/MCF-7）的臨床應用，但需在 SOP「局限性」章節中明確說明：**本平台對高度間質型（Vimentin+/EpCAM-）CTC 的捕獲效率較低**。

**驗收標準（依 cell line 特性分層）**：

| Cell Line | EMT 程度 | 回收率目標 | CV 上限 | 說明 |
|-----------|---------|----------|--------|------|
| MCF-7 | 高上皮 | **≥ 70%**（目標 80–95%） | ≤ 15% | 系統上限基準 |
| SK-BR-3 | 中上皮/高 HER2 | ≥ 65% | ≤ 15% | CDx 核心 target |
| HCT116 | 中間型（EMT） | **45–70%** | ≤ 20% | 線性基準 |
| MDA-MB-231 | 高間質 | **20–45%** | ≤ 25% | 系統下限/技術邊界 |

線性：**R² ≥ 0.95，Slope 0.8–1.2**（所有 cell line 中，MCF-7 和 SK-BR-3 最重要）

**LOD 計算（基於 Poisson 統計）**：
- LOD 定義為：在 n=10 重複中，**≥ 8 次（80%）能回收到 ≥ 1 cell** 的最低 spike level
- 從 L1（2 cells）開始確認，若 L1 未達標（< 8/10），LOD = L2（4 cells），依此類推
- 目標 LOD ≤ **4 cells / 7.5 mL blood**（臨床意義上，CTC < 5/7.5 mL 為低密度患者）

**LOQ（Limit of Quantification）**：
- LOQ 定義為：回收率 CV ≤ 20% 的最低 spike level
- 通常 LOQ > LOD，可能落在 L3–L4（6–8 cells）

---

## Exp 4：試劑與基材穩定性測試

**目的**：確認 capture antibody 和 streptavidin 基材在不同儲存條件下的有效期

**儲存條件**：
- 條件 A：-20°C（建議儲存條件）
- 條件 B：4°C（冰箱短期）
- 條件 C：室溫 25°C（加速降解測試）

**時間點**：Day 0、7、14、30、60、90

**步驟**：

1. **Day 0 基準值**：取部分 capture antibody 和 streptavidin 基材，立即執行標準 Spike-in 測試（SK-BR-3 100 cells/7.5 mL，n=3），記錄回收率作為 T0 基準
2. **分裝儲存**：將同批次 capture antibody 分成三份，分別放置 -20°C、4°C、RT
3. **各時間點測試**：在 Day 7、14、30、60、90，從各儲存條件取出 antibody，執行相同 Spike-in 測試
4. **計算效能保留率**：效能 % = (各時間點回收率 / Day 0 回收率) × 100%
5. **繪製穩定性曲線**：時間 vs. 效能保留率（三個條件三條線）
6. **定義 Shelf Life**：找到效能保留率首次低於 90% 的時間點，前一個時間點定義為有效期

**驗收標準**：各儲存條件下，效能保留率 **≥ 90%（相對 Day 0）** 在指定有效期內

**預期結果**：-20°C 最佳（> 90 天），4°C 次之（30–60 天），RT 最差（< 14 天）

---

## Exp 5：微流道穩健性測試（Microfluidic Robustness Testing）★ 新增

> **設計依據**：文件第二部分「Gaps & Supplemental Designs」補充實驗。目的是量化捕獲裝置對操作參數變動的容忍度，為 ANA-001 SOP 提供「操作窗口（Operational Window）」定義的實驗依據。

### 為什麼要做穩健性測試？

ANA-001 SOP 規定的「標準」流速和緩衝液 pH 值，在實際操作中難以每次精確複製：操作者施加壓力輕重不同、注射泵年久誤差、緩衝液 pH 因儲存條件漂移等。穩健性測試回答：**「如果某個參數在規格範圍內變動，捕獲效率會下降多少？」** 答案直接定義 ANA-001 SOP 的「允許操作公差」欄位，和 QC-001 的失效觸發條件。

---

### Exp 5A：流速容忍度（Flow Rate Robustness）

**測試條件**：

| 條件代號 | 流速設定 | 說明 |
|---------|---------|------|
| Q_−20% | 標準流速 × 0.80 | 慢速端極限 |
| Q_−10% | 標準流速 × 0.90 | 慢速容差 |
| **Q_std** | **標準流速（ANA-001 規格值）** | **對照組** |
| Q_+10% | 標準流速 × 1.10 | 快速容差 |
| Q_+20% | 標準流速 × 1.20 | 快速端極限 |

> 標準流速絕對值（μL/min 或 mL/hr）在 ANA-001 SOP 定義後填入本表。

**材料**：
- SK-BR-3（HER2 3+，高 EpCAM）和 MCF-7（HER2 1+，高 EpCAM）各自測試——代表不同黏附動力學
- 健康捐血者 K2-EDTA 全血，7.5 mL / 條件
- Spike 100 cells / 7.5 mL（計數 CV < 5%）
- 精密注射泵（Syringe pump）或壓力控制器，精度 ±5% 流速

**步驟**：
1. 準備 5 個流速條件 × 2 株 cell line × n=3 重複 = 30 個捕獲裝置
2. 各裝置均依 P1-Test 1 最佳化的濃度包覆（標準條件）
3. 各條件下，以指定流速將 7.5 mL spiked 血液通過捕獲裝置
4. **洗滌條件保持標準**（體積和流速不變，只改變捕獲步驟的流速）
5. 依 ANA-004 IF 染色，影像分析計數 CTC（DAPI+/CK+/CD45-）

**數據分析**：
- 各條件回收率 = recovered / spiked × 100%
- 相對回收率（%Retention）= 各條件回收率 / Q_std 回收率 × 100%
- 繪製「流速偏差 vs. %Retention」折線圖（SK-BR-3 和 MCF-7 各一條線）

**驗收標準**：

| 條件 | 相對回收率（vs. Q_std）|
|------|----------------------|
| Q_−20% | **≥ 90%** |
| Q_−10% | **≥ 95%** |
| Q_+10% | **≥ 95%** |
| Q_+20% | **≥ 90%** |

> 若任何條件未達標，縮小 SOP 的允許流速範圍，直至所有測試條件均 ≥ 90%。

**SOP 輸出**：結果定義 ANA-001 SOP 的「允許流速範圍」，寫入操作規格表（Specification Table）。

---

### Exp 5B：緩衝液 pH 容忍度（Wash Buffer pH Robustness）

**測試邏輯**：洗滌緩衝液 pH 影響 biotin-streptavidin 鍵結穩定性和細胞表面蛋白完整性。pH 過低（< 7.0）削弱捕獲鍵結；過高（> 8.0）可能破壞細胞膜。

**測試條件**：

| 條件 | pH | 說明 |
|------|-----|------|
| pH 6.8 | 6.8 | 酸性端 |
| pH 7.2 | 7.2 | 正常 PBS 偏低 |
| **pH 7.4** | **7.4** | **標準 PBS（對照組）** |
| pH 7.6 | 7.6 | 微鹼 |
| pH 8.0 | 8.0 | 鹼性端 |

**製備**：以 1 M HCl 或 1 M NaOH 調整 PBS，每批用校正 pH meter 確認（精度 ±0.05）

**步驟**：
1. 各 pH 條件 Spike SK-BR-3 100 cells / 7.5 mL，n=3
2. 捕獲步驟使用 Q_std；洗滌緩衝液換成各測試 pH 液
3. IF 染色，計數 CTC
4. 同時記錄 HER2 FITC MFI（確認 pH 未影響染色效果）
5. 計算相對回收率（%Retention vs. pH 7.4）

**驗收標準**：

| 條件 | 相對回收率 | HER2 MFI 保留（vs. pH 7.4）|
|------|----------|-----------------------------|
| pH 6.8 | **≥ 90%** | **≥ 85%** |
| pH 7.2 | **≥ 95%** | **≥ 90%** |
| pH 7.6 | **≥ 95%** | **≥ 90%** |
| pH 8.0 | **≥ 90%** | **≥ 85%** |

**SOP 輸出**：定義 ANA-001 SOP 的「洗滌緩衝液 pH 允許範圍」（例如 pH 7.0–8.0 均可，視結果而定）。

---

## Exp 6：Carryover 攜帶污染驗證（Carryover Validation）★ 新增

> **設計依據**：文件第二部分「Gaps & Supplemental Designs」補充實驗。CLIA/CAP 要求 LDT 必須評估交叉污染風險。CTC 計數中，哪怕 1 個 carryover cell 都可能把陰性結果誤判為陽性，對臨床決策影響極大。

### 為什麼 Carryover 對 CTC 特別重要？

**Carryover 計算公式**（CLSI EP7 定義）：
`Carryover（%）= （空白測試的回收值 − 空白背景值）/ 高濃度測試值 × 100%`

CTC 計數的特殊性：目標值為 **0%（任何殘留細胞均不可接受）**。CTC ≥ 1 cell = 陽性，因此即使 1 個 carryover cell 在下一份樣本中出現，就是臨床假陽性。

---

### Exp 6A：高密度到陰性樣本 Carryover（主要測試）

**測試設計**：

```
Run 1（高密度）：MCF-7 10,000 cells / 7.5 mL blood
    → 捕獲 + 標準洗滌（ANA-001）+ IF 染色（記錄基準回收值）
Run 2（空白）：0 cells / 7.5 mL blood → 同裝置（若可重複用）或換新裝置 → 計數殘留
Run 3（空白）：同上
Run 4（空白）：同上
Run 5（空白）：同上
Run 6（空白）：同上
```

> 選用 MCF-7（高 EpCAM，強黏附力）作為「最壞情境」cell line

**步驟**：
1. 準備 MCF-7 懸液 10,000 cells / 7.5 mL 全血，確認活性 ≥ 90%，spike 後輕旋混勻
2. **Run 1**：執行完整捕獲（ANA-001，含所有標準洗滌步驟）→ IF 染色 → 計數（= 基準值）
3. **若裝置為一次性**：換同批包覆的新裝置，對 Run 2–6 各次執行未 spike 的健康血液（7.5 mL）
   **若裝置可重複清洗**：用同一裝置依 ANA-001 清洗 SOP 清洗後，執行 Run 2–6
4. **Run 2–6**：每次加入 7.5 mL 未 spike 健康血液，執行完整捕獲 + 洗滌 + IF 染色 + 計數
5. 每次記錄裝置狀態（目視是否有殘留，洗出液是否清透）

**驗收標準**：

| 要求 | 目標值 |
|------|--------|
| Run 2–6 全部 CTC 計數（DAPI+/CK+/CD45-）| **0 cells（每次）** |
| Carryover % | **= 0%** |

**失敗處理（偵測到 carryover cells）**：

```
偵測到殘留細胞？
    ├── 1–2 次 Run 有殘留 → 增加洗滌步驟（次數或體積），重新測試
    ├── 連續多次殘留 → 裝置設計吸附過強 → 修改 ANA-001 洗滌條件（換高鹽洗滌液）
    └── 修改後仍失敗 → 重新評估裝置設計（材料/表面處理）
```

---

### Exp 6B：裝置製造背景驗證（Device Background，適用一次性裝置）

**目的**：確認全新捕獲裝置本身不含 CTC 形態的背景物（排除製造污染）

**步驟**：
1. 隨機取 5 個全新捕獲裝置（**不包覆任何抗體**）
2. 通入 7.5 mL 正常健康血液（未 spike）
3. 執行標準洗滌 + IF 染色
4. 影像分析：計數 DAPI+/CK+/CD45- 事件

**驗收標準**：0 events（與 Exp 2B unspiked blood 背景水準相同）

---

# PHASE 3：分析驗證（Analytical Validation for CLIA）

以下測試針對 CLIA 42 CFR §493.1253 的「non-waived test」要求，即所有 LDT 必須完成的項目。

---

## Phase 3-A：精密度矩陣（Precision Matrix — CLSI EP05-A3 完整版）★ 擴充

> **版本升級說明**：v1.2 依 CLSI EP05-A3 完整標準擴充為 5 維度矩陣（批內 / 批間 / 操作者間 / 儀器間 / 批次間），符合 CLIA 42 CFR §493.1253 和 CAP MIC.22640 的進階要求。

### 為什麼要做 5 維度精密度測試？

| 變異維度 | 定義 | 為什麼重要 |
|---------|------|----------|
| 批內重複性（Within-run）| 同天、同人、同機器 × n=10 | 方法本身的隨機誤差 |
| 批間重複性（Between-day）| 連續 5 天 × 每天 2 replicate | 日常試劑消耗的影響 |
| 操作者間（Between-operator）| ≥ 3 個技術員各自操作 | 人員操作差異 |
| 儀器間（Between-instrument）| ≥ 2 台顯微鏡系統 | 設備差異（若有多台）|
| 批次間（Between-lot）| ≥ 3 批 capture antibody + chip | 試劑採購批次差異 |

**Spike Level 設計（3 個密度）**：

| Level | Spike 密度 | 主要 Cell Line | 理由 |
|-------|-----------|--------------|------|
| **Low（L）** | 10 cells / 7.5 mL | SK-BR-3 + MCF-7 | 臨床最重要範圍下限，CV 最嚴苛 |
| **Mid（M）** | 50 cells / 7.5 mL | SK-BR-3 | 標準 QC 密度 |
| **High（H）** | 100 cells / 7.5 mL | SK-BR-3 | 系統上限，CV 應最低 |

---

### 維度 1：批內重複性（Within-Run Repeatability）

**設計**：同一天、同一操作者（最有經驗的技術員 A）、同一台儀器

**步驟**：
1. 在同一天準備 Low / Mid / High 三個 Spike Level，各 n=10 重複
2. 10 個重複管依序執行：Spike → 捕獲（ANA-001）→ IF 染色（ANA-004）→ 影像分析
3. 記錄每管的 CTC 計數和 HER2 MFI（轉換為 MESF 單位）
4. 計算各 Level 的 Mean、SD、CV

**驗收標準（Within-Run CV）**：

| Level | Cell Line | CV 上限 |
|-------|----------|--------|
| Low（10 cells）| SK-BR-3 | **≤ 15%** |
| Low（10 cells）| MCF-7 | **≤ 15%** |
| Mid（50 cells）| SK-BR-3 | **≤ 12%** |
| High（100 cells）| SK-BR-3 | **≤ 10%** |

---

### 維度 2：批間重複性（Between-Day / Between-Run）

**設計**：連續 5 天 × 每天 2 replicate × 3 Spike Level

**步驟**：
1. 連續 5 個工作日，每天執行 2 組 spike-in 測試（各 Level）
2. 使用同一批 capture antibody 和 chip（與 Between-lot 測試分開執行）
3. 固定同一操作者（技術員 A，排除操作者間差異）
4. 計算 Within-Day CV（n=2）和 Between-Day CV（n=5 天）
5. 以 ANOVA 分解各來源的變異

**驗收標準**：

| Level | Within-Day CV | Between-Day CV | Total CV |
|-------|-------------|--------------|--------|
| Low（10 cells）| ≤ 15% | ≤ 15% | **≤ 20%** |
| Mid（50 cells）| ≤ 12% | ≤ 12% | **≤ 15%** |
| High（100 cells）| ≤ 10% | ≤ 10% | **≤ 12%** |

---

### 維度 3：操作者間重複性（Between-Operator）

**設計**：3 個技術員（A / B / C）各自獨立操作，不互相溝通

**前提**：所有技術員均已完成 LAB-002 規定的訓練和資格考核

**步驟**：
1. 技術員 A、B、C 各自獨立執行（同一天或連續 3 天）：
   - Spike（10 / 50 / 100 cells）× n=3 重複
   - 完整捕獲 + IF 染色流程 + 影像分析
2. 操作期間不得互相討論；儀器設定預先固定（技術員不得調整）
3. 計算操作者間 CV

**驗收標準（Between-Operator CV）**：

| Level | CV 上限 |
|-------|--------|
| Low（10 cells）| **≤ 20%** |
| Mid（50 cells）| **≤ 15%** |
| High（100 cells）| **≤ 12%** |

---

### 維度 4：儀器間重複性（Between-Instrument）— 適用若有 ≥ 2 台顯微鏡

**設計**：相同 MESF 校正後，同一 IF 製片在兩台儀器上分別測量

**步驟**：
1. 技術員 A 製備 Spike-in 製片（10 / 50 / 100 cells，n=5 重複）
2. 每張製片在儀器 1（主要儀器）和儀器 2（備用儀器）各自掃描（固定設定）
3. 兩台儀器均需有最新 MESF 校正方程式（Ph1.5-Test 2 已驗證 < 5% 差異）
4. 比較兩台儀器的 CTC 計數和 HER2 MESF 值

**驗收標準**：

| 指標 | 要求 |
|------|------|
| CTC 計數 Between-Instrument CV | **≤ 10%** |
| HER2 MESF Between-Instrument CV | **≤ 5%**（由 Ph1.5-Test 2 保證）|

> 若目前只有一台顯微鏡，此維度暫緩，待第二台到位後補測，並於 Validation Report「Limitations」章節說明。

---

### 維度 5：批次間重複性（Between-Lot）

**設計**：3 批次 Capture Antibody cocktail + 3 批次 Chip 的組合測試

**步驟**：
1. 準備 3 個不同 Lot 的 capture antibody cocktail 和 3 批 chip
2. 9 種組合（3 Ab lots × 3 chip lots），同一天、同一操作者，各執行 SK-BR-3 100 cells spike-in（n=3）
3. 計算各組合回收率，以 ANOVA 分析 Lot 主效應和交互作用

**驗收標準**：

| 指標 | 要求 |
|------|------|
| Between-Lot CV（Antibody）| **≤ 15%** |
| Between-Lot CV（Chip）| **≤ 15%** |
| Antibody × Chip 交互作用 | 無顯著交互作用（p > 0.05）|

---

### 精密度數據匯總表（CLSI EP05-A3 格式）

所有維度完成後，填入以下匯總表（每個 Spike Level 各填一份）：

| 變異來源 | 方差（Variance）| SD | CV |
|---------|----------------|----|----|
| Within-Run | | | |
| Between-Day | | | |
| Between-Operator | | | |
| Between-Instrument | | | |
| Between-Lot | | | |
| **Total** | | | **最終報告值** |

> Total CV 即 Method Validation Report 中報告的精密度數值，需符合各 Level 的驗收標準。

**數據記錄**：使用 CLSI EP05-A3 推薦的數據表格，全部原始數據保存於 Validation Data Folder。

---

## Phase 3-B：PBMC-Level 干擾物質測試（重設計版）★ v1.3

> **設計說明**：本平台在 CTC 捕獲前先執行 Ficoll 密度梯度分離，PBMC 懸液中已去除絕大部分血漿組分（Hb、Bili、Lipemia 等）。因此，傳統 HIL（Hemolysis/Icterus/Lipemia）干擾在此平台幾乎不適用，改為測試 **PBMC 懸液中存在的細胞層級干擾因素**。
>
> **不需要測試的項目**：Hemolysis（Hb）、Bilirubin、Lipemia（三者均在 Ficoll 分離後的血漿廢棄層，不進入 PBMC 捕獲流程）。

**PBMC-level 干擾測試總覽**：

| 干擾物 | 測試重點 | 臨床情境 |
|--------|---------|---------|
| **血小板殘留（Platelet contamination）** | Ficoll 分離後 PLT 殘留量對 CTC 捕獲和染色的影響 | PLT 不完全去除（常見）；高 PLT 計數患者 |
| **死細胞比例（Dead cell / debris）** | 高比例死細胞對背景和 CTC 辨識的影響 | 樣本延遲處理；凍融損傷 |
| **RBC 殘留（Incomplete Ficoll separation）** | 少量 RBC 殘留是否增加 FITC 通道自體螢光 | 嚴重溶血導致 Ficoll 分層不清；RBC 碎片混入白膜層 |
| **高單核球比例（Monocyte load）** | 高單核球樣本中 CD45 背景是否升高 | 感染、類固醇使用、某些血液腫瘤 |

---

### Exp 3B-1：血小板殘留干擾（Platelet Contamination）

**背景**：Ficoll 分離後，血小板（PLT，密度 ~1.058 g/mL）大部分懸浮在上層血漿中被吸除，但 PLT 容易聚集或附著在 PBMC 上，殘留在白膜層。大量 PLT 可能：
- 物理阻塞微流道孔隙
- PLT 表面的 EpCAM 同型蛋白（E-cadherin-like）非特異性被 capture antibody 捕獲
- 增加 HER2 染色背景（部分活化血小板有 HER2 相關蛋白質）

**測試設計**：製備不同 PLT 殘留量的 PBMC 懸液

| 條件 | 目標 PLT 殘留（per mL PBMC 懸液）| 製備方式 |
|------|--------------------------------|---------|
| 對照 | < 10,000 PLT/mL（充分洗滌）| 標準 PBS 洗滌 × 3 |
| 低殘留 | ~100,000 PLT/mL | 洗滌 × 1 |
| 高殘留 | ~500,000 PLT/mL | 不洗滌 |

**步驟**：
1. 各條件 PBMC 懸液各 Spike SK-BR-3 100 cells（n=3）
2. 執行 CTC 捕獲（ANA-001）→ IF 染色（ANA-004）→ 影像分析
3. 記錄：CTC 回收率、DAPI-/CK-/CD45- 顆粒（PLT 形成的背景顆粒數）、是否有微流道堵塞
4. 用 PLT 計數試劑（如 Sysmex 或 CBC）確認各條件實際 PLT 濃度

**驗收標準**：

| 指標 | 要求 |
|------|------|
| CTC 回收率（高殘留 vs. 對照）| 差異 **< 15%** |
| 背景顆粒計數（非 CTC 事件）| **≤ 5 events / 視野**（不干擾計數判讀）|
| 微流道堵塞事件 | **0 次**（在測試條件範圍內）|

**SOP 輸出**：定義 PRE-004 的「PBMC 洗滌次數規格」（如「PBS 洗滌 × 2 次，確保 PLT < 50,000/mL」）。

---

### Exp 3B-2：死細胞比例干擾（Dead Cell / Debris Interference）

**背景**：高比例死細胞和細胞碎片會：
- 非特異性吸附抗體（Fc receptor 在死細胞上暴露），增加 CK 和 HER2 假陽性背景
- 死細胞形態改變，可能被影像分析誤計為 DAPI+/CK+/CD45- 事件

**測試設計**：

| 條件 | 目標死細胞比例 | 製備方式 |
|------|------------|---------|
| 對照 | < 5% | 正常 PBMC，立即處理 |
| 中等 | 15–20% | 正常 PBMC，4°C 放置 6 小時 |
| 高 | 30–40% | PBMC 在 42°C 水浴 30 分鐘（熱誘導細胞死亡）|

**步驟**：
1. 各條件 Spike SK-BR-3 100 cells（n=3）
2. 完整 pipeline → 影像分析
3. 記錄：CTC 回收率、DAPI+/CK+/CD45- 背景事件數（疑似 false positive）、背景 HER2 FITC MFI

**驗收標準**：

| 條件 | CTC 回收率保留 | False Positive 背景事件 |
|------|------------|----------------------|
| 中等（15–20% 死細胞）| **≥ 85% of 對照** | **≤ 2 extra events / 7.5 mL** |
| 高（30–40% 死細胞）| 觀察記錄 | 觀察記錄 |

**SOP 輸出**：定義 PRE-004 的「PBMC 死細胞上限」；若死細胞 > 20% 需於報告備注（加入 QC-001 每批次 Trypan Blue 確認步驟）。

---

### Exp 3B-3：RBC 殘留干擾（Incomplete Ficoll Separation）

**背景**：在特殊情況下（嚴重溶血、黏稠血液、Ficoll 操作錯誤），PBMC 層可能混入少量 RBC 或 RBC 碎片，增加 FITC 通道的自體螢光（Hb 在 488nm 有吸收和散射）。

**測試設計**：將不同比例的 RBC 重新加入 PBMC 懸液（模擬不完全分離）：

| 條件 | RBC 殘留（per mL PBMC 懸液）| 說明 |
|------|---------------------------|------|
| 對照 | 0（充分分離）| 正常操作 |
| 低殘留 | ~5 × 10⁴ RBC/mL | 輕度不完全分離 |
| 高殘留 | ~5 × 10⁵ RBC/mL | 明顯 RBC 污染（顯示為淡紅色懸液）|

**步驟**：
1. 各條件 Spike SK-BR-3 100 cells（n=3）
2. 完整 pipeline → 記錄 CTC 回收率 + FITC 通道背景 MFI

**驗收標準**：低殘留條件：FITC 背景增加 **≤ 15%**；回收率保留 **≥ 90%**

**SOP 輸出**：PRE-004 加入「若 PBMC 懸液目視呈粉紅色（RBC 殘留）需重新離心洗滌後才可進入捕獲流程」的操作規定。

---

### Exp 3B-4：高單核球比例干擾（High Monocyte Load）

**背景**：感染患者或使用類固醇治療的患者，PBMC 中單核球（Monocyte）比例可能顯著升高（正常 5–10%，可升至 30–40%）。單核球：
- 高表現 CD14、CD16（但 CD45 也陽性）→ 應被 CD45+ 排除
- 高度吞噬活性（phagocytosis），可能吞入抗體或螢光顆粒，形成假性 CK 或 HER2 訊號
- 部分 monocyte-derived 細胞（如 MDSCs）可能表現 EpCAM，被 capture antibody 非特異性捕獲

**測試設計**：用 elutriation 或抗體磁珠分選方式，製備高比例 monocyte PBMC 懸液（50–60% monocyte），與正常 PBMC（5–10% monocyte）比較

**步驟**：
1. 各條件 Spike SK-BR-3 100 cells（n=3）
2. 完整 pipeline → 計數 CTC + 計數 DAPI+/CK+/CD45- 背景事件

**驗收標準**：高單核球條件的 false positive 背景事件 **≤ 5 events / 7.5 mL**；CTC 回收率差異 **< 15%**

---

### Phase 3-B 驗收總表（SOP 輸出彙整）

| 干擾物 | 安全閾值 | SOP 行動 |
|--------|---------|---------|
| PLT 殘留 < 100,000/mL | 回收率差異 < 15%，無堵塞 | 接受；PRE-004 規定洗滌次數 |
| PLT 殘留 > 500,000/mL | 可能堵塞或干擾 | PRE-004 加強洗滌規格 |
| 死細胞 ≤ 20% | 回收率保留 ≥ 85%，背景 ≤ 2 events | 接受；附報告備注 |
| 死細胞 > 20% | 背景可能升高 | PRE-004 加入 Trypan Blue QC；報告加警語 |
| RBC 殘留（低）| FITC 背景增加 ≤ 15% | 接受 |
| RBC 殘留（目視粉紅色）| 可能影響 FITC 通道 | PRE-004 加「目視確認透明懸液」規定 |
| 高單核球（< 40%）| False positive ≤ 5 events | 接受 |

---

# PHASE 4：HER2 評分驗證

## 為什麼特別重要？

這是 CDx 的核心——你必須能夠可靠地區分 HER2 0 / 1+ / 2+ / 3+，因為這個結果直接影響患者是否接受 HER2 靶向療法。評分標準必須：
1. 與組織 IHC 有相關性（雖然不需完全等同）
2. 不同人判讀的結果要一致

---

## P4-Test 1：HER2 IF 評分截斷值定義（MESF 單位）

> **前提**：Phase 1.5 MESF 校正必須已完成，三通道（FITC/PE/APC）校正方程式均通過驗收（R² ≥ 0.99）。本測試所有 MFI 數值須先透過 Ph1.5 校正方程式轉換為 MESF 單位後再定義截斷值。

**目的**：定義 IF 染色 HER2 FITC 通道的螢光強度，以 **MESF（絕對物理單位）** 表達對應 IHC 0/1+/2+/3+ 的分類截斷值，確保截斷值不隨時間、儀器或抗體批次漂移

**步驟**：

1. 準備已知 HER2 IHC status 的 reference cell lines：
   - IHC 3+：SK-BR-3、BT-474
   - IHC 2+：ZR-75-30（若有）
   - IHC 1+：MCF-7（低表現，最重要的辨別關鍵）
   - IHC 0：MDA-MB-231

2. 每株 cell line 準備 3 批次（不同天），各做 IF 染色（標準化條件）

3. 影像分析：對每個細胞測量 HER2 FITC 通道 MFI，**立即套用 Ph1.5 校正方程式轉換為 MESF 值**：
   `MESF_HER2 = (MFI_FITC − b_FITC) / a_FITC`

4. 繪製各 cell line 的 MESF_HER2 分布箱型圖（Boxplot）

5. 以 ROC 分析定義截斷值（以 MESF 單位表達）：
   - 截斷值 A（0 vs 1+ 界線）：MDA-MB-231 MESF_HER2 的 95th percentile
   - 截斷值 B（1+ vs 2+ 界線）：待定，依分布和 ROC 分析而定
   - 截斷值 C（2+ vs 3+ 界線）：SK-BR-3 MESF_HER2 的 10th percentile

6. 驗證截斷值：用未參與定義的 cell line（如 HCC1954 HER2++）測試截斷值是否正確分類

7. 將最終確認的 MESF 截斷值寫入 ANA-010（HER2 評分 SOP）和 POST-001（結果判讀 SOP）

---

## P4-Test 2：判讀者間一致性（Inter-Rater Reliability）

**目的**：確認不同操作者看同一張 IF 影像，HER2 評分結果一致

**步驟**：
1. 製備 20–30 張 IF 影像（含已知 HER2 分組的 cell line spike-in，由研究助理打亂順序不告知分組）
2. 2 個以上有資格的操作者獨立評分（不可互相討論）
3. 計算 Cohen's Kappa 係數

**驗收標準**：Kappa ≥ 0.80（幾乎完全一致）

---

# 測試執行時間表（建議，v1.2 更新版）

| 週次 | 工作項目 | 備注 |
|------|---------|------|
| Week 1–2 | Phase 0：Cell Line STR、Mycoplasma、FACS 表型確認、Viability | 所有 5 株 cell line（MCF-7、SK-BR-3、HCT116、MDA-MB-231、Jurkat）|
| Week 2（同步）| Phase 0.5：EDTA 穩定性開始（T0 → T24 → T48）| 注意 Day 0 採血時序對齊 |
| Week 3 | Phase 0.5：T72h 和 T96h 完成，數據分析，定義處理時間窗口 | 結果寫入 PRE-001 SOP 草稿 |
| Week 3–4 | Phase 1：P1-Test 1（Capture 抗體 Titration）+ P1-Test 2（Detection 抗體稀釋度）| |
| Week 5 | Phase 1：P1-Test 2b（HER2-FITC Direct vs. Indirect）+ P1-Test 3（Cocktail 相容性）| 2b 結果決定 ANA-004 Section 9.4–9.6 |
| **Week 5–6** | **Phase 1.5：MESF Bead 校正建立（FITC/PE/APC 三通道）** | **★ 新增；必須在 Exp 3 前完成** |
| Week 6–7 | Phase 2：Exp 1（包覆飽和 + Lot-to-Lot）+ Exp 2（WBC 排除）| |
| Week 8–9 | Phase 2：Exp 3（Spike-in 線性 2–100 cells，建立 LOD/LOQ）| L1（2 cells）需 n=10，勞力密集 |
| **Week 9–10** | **Phase 2：Exp 5A（流速容忍度）+ Exp 5B（pH 容忍度）** | **★ 新增；可與 Exp 3 尾端並行** |
| **Week 10** | **Phase 2：Exp 6（Carryover 驗證）** | **★ 新增；相對較快，3–5 天完成** |
| Week 10 | Phase 2：Exp 4 開始（試劑穩定性 Day 0 基準）| |
| Week 11–12 | Phase 3-A：精密度矩陣（維度 1–3：Within-run / Between-day / Between-operator）| 技術員 A/B/C 輪流操作 |
| Week 12–13 | Phase 3-A：維度 4–5（儀器間 / 批次間）| 若只有一台儀器，維度 4 暫緩 |
| Week 13–14 | Phase 3-B：HIL 干擾物質（Hb / Bili / Lipemia）| 三類干擾物可並行製備，各自測試 |
| Week 15 | Phase 4：P4-Test 1（HER2 MESF 截斷值定義）| 依 Phase 1.5 MESF 校正完成為前提 |
| Week 15–16 | Phase 4：P4-Test 2（判讀者間一致性，Kappa 計算）| 需 ≥ 2 位合格判讀者 |
| Week 10–22（持續）| Phase 2 Exp 4：試劑穩定性（Day 7, 14, 30, 60, 90 持續測試）| 背景進行，不佔主線工作 |
| Week 16 | 整合所有 Phase 數據，撰寫 Method Validation Report（草稿）| |
| Week 17–18 | Lab Director 審核、簽署 Validation Report | |
| 審核通過後 | 啟動正式 SOP，進入臨床樣本測試 | |

> **總估計時程**：約 18–20 週（4.5–5 個月），含 Exp 4 的持續監測期。若缺乏雙儀器，可縮短 1–2 週。Exp 5/6 是新增的穩健性測試，規模相對較小，不影響主線進度。

---

# 待討論事項（與 R&D Plan 的差異或需確認的問題）

1. **Capture Antibody Cocktail：已確認使用 EpCAM + HER2 + EGFR 三種**
   - MUC1、CD49f、c-Met 暫不納入
   - EGFR 保留理由：補捉 EpCAM-low CTC（EMT 程度高的細胞）
   - EGFR 在部分嗜中性白血球上有表現 → 須在 Exp 2 中特別測試：加入 EGFR 前後的 WBC 非特異捕獲背景是否增加

2. **Spike-in Levels：已更新為 2 / 4 / 6 / 8 / 10 / 50 / 100 cells / 7.5 mL**
   - 低密度端（2–10）細分，為 CDx 臨床最重要的範圍
   - L1（2 cells）需 n=10，其他 n=3–5
   - 目標 LOD ≤ 4 cells / 7.5 mL

3. **HER2 IF vs 組織 IHC 橋接研究：本階段不做，但必須納入討論與規劃**
   - 本平台以**螢光顯微鏡**偵測 CTC 上的 HER2 蛋白，與組織切片 IHC（DAB 顯色）是完全不同的偵測系統
   - IF 的評分依據是螢光強度（MFI），IHC 的評分依據是 DAB 染色深度——兩者單位不同，不可直接換算
   - **為什麼必須規劃橋接**：CDx 的臨床意義建立在「IF HER2 陽性 = 患者適合接受 HER2 靶向治療」，這個連結需要用已知 IHC 狀態的患者樣本來驗證（同一患者，同時做組織 IHC 和血液 CTC HER2 IF）
   - **當前階段任務**：先建立 IF 平台的分析性能（LOD/精密度/評分截斷值），使橋接研究有可靠的基準可比較
   - **Next Step 規劃**：收集 20–30 名已知組織 HER2 IHC status 的患者（各 IHC 0/1+/2+/3+ 分組），同步抽血做 CTC HER2 IF，計算兩者的 concordance（一致率）和 ROC 曲線

4. **採血管：已確認使用 K2-EDTA，Streck 不採用**
   - 決策依據：EDTA 成本低、操作熟悉；Phase 0.5 將在 K2-EDTA 條件下執行完整穩定性驗證（T0–T96h，RT + 4°C）
   - Phase 0.5 結果決定 PRE-001 SOP 的最長處理時間窗口和拒絕標準
   - 後續所有驗證實驗統一使用 K2-EDTA 管

---

*文件版本 v1.3 | 2026-05-23 | 前處理設計確認為全血 → Ficoll PBMC 分離 → CTC 捕獲；Phase 3-B 由傳統 HIL 重設計為 PBMC-level 干擾測試（PLT/死細胞/RBC 殘留/單核球）；Phase 0.5 加入窗口 B（PBMC 懸液穩定性）；Exp 3 加入 Ficoll step recovery 子實驗*
