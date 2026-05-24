# HER2-CDx — CTC-Based HER2 LDT

## 一句話定位
建立 CTC（循環腫瘤細胞）HER2 檢測 LDT，在自建 CLIA/CAP 認證實驗室中，對乳癌、胃癌、肺癌患者進行 HER2 狀態評估。

## 技術架構
```
全血採集
    ↓
CTC 分離（自建微流道 / 濾器法）
    ↓
IF 染色（DAPI + CK + CD45 + HER2）
    ↓
影像擷取（螢光顯微鏡 / 自動掃描儀）
    ↓
影像分析 + HER2 評分
    ↓
臨床報告
```

## 法規框架
- **分類**：LDT（Laboratory Developed Test）
- **認證目標**：CLIA Certificate of Compliance + CAP Accreditation
- **CAP 檢查項目**：COM（All Common）+ 可能 CYG（若做 FISH）+ 客製化 checklist
- **FDA**：LDT 目前仍在 CLIA 框架下（2024 FDA LDT Final Rule 需持續追蹤）

## 適應症
| 癌種 | 主要用途 | 參考指引 |
|------|---------|---------|
| 乳癌 | HER2+ 監測、療效追蹤 | ASCO/CAP 2018 HER2 Guideline |
| 胃癌 / GEJ | HER2+ 篩選（Trastuzumab 適用） | ToGA trial + ASCO/CAP |
| 肺癌 | HER2 exon 20 / amplification | NCCN NSCLC Guidelines |

## SOP 文件清單（目標）
→ 詳見 `Science/SOP-Framework.md`

## 現有資源
- [x] 微流道 / 濾器 CTC 捕獲技術
- [x] Anti-HER2 抗體（IF 用）
- [ ] 影像分析 pipeline（待建立）
- [ ] Method Validation 數據
- [ ] CLIA 申請

## 資料夾結構
```
HER2-CDx/
├── README.md
├── Science/
│   ├── SOP-Framework.md      ← SOP 清單與架構
│   ├── SOPs/                 ← 各份 SOP 正文
│   └── Validation/           ← Method validation 計畫與數據
├── Regulatory/
│   ├── CLIA-Application/     ← CLIA 申請文件
│   ├── CAP-Checklist/        ← CAP self-inspection checklist
│   └── FDA-LDT/              ← FDA LDT Final Rule 追蹤
├── Market/
└── Business/
```
