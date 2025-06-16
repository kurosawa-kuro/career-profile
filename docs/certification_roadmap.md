# 外資系 IT 転職に向けた資格・プロジェクト学習ロードマップ

**（2025年7月スタート版 — CKAD 取得済み想定）**

---

## 0. 前提の更新

|項目|内容|
|---|---|
|開始時期|**2025年7月**|
|既取得資格|**CKAD-JP（2025-06 取得済）**|
|週間学習時間|平日 3 h ×5 ＋ 週末 8 h ×2 ＝ **31 h / 週**|
|CKS の扱い|志望ポジションで **必須ではない** ため “Nice-to-Have” として優先度を下げる|

---

## 1. 年間優先度（2025 H2〜2026 H1）

| 優先度 | 資格／プロジェクト                                    | 目標取得時期     | 概算学習時間  | 転職優位性のポイント                                   |
| :-: | -------------------------------------------- | ---------- | ------- | -------------------------------------------- |
| 🥇1 | **CKA-JP**                                   | 2025-08    | 40–60 h | Snowflake・dbt を本番運用する **Kubernetes基盤理解** を証明 |
| 🥇2 | **Terraform Associate**                      | 2025-09    | 25–30 h | IaC で Snowflake / EKS / GCP 環境を **再現可能** にする |
| 🥈3 | **SnowPro Core**                             | 2025-10    | 30–35 h | Snowflake 基礎＋DWH 設計力を公式化                     |
| 🥈4 | **dbt Certified Developer**                  | 2025-10    | 7–10 h  | ELT と CI/CD パイプラインを短期で実装可                    |
|  5  | **SnowPro Advanced: Data Engineer**          | 2025-12    | 45–55 h | タスク／ストリーミング／Secure Data Sharing 等の実務力        |
|  6  | **MLOps 認定**（例: Databricks Data/ML Engineer） | 2026-02    | 25–35 h | Snowflake＋MLflow 連携で **Data-to-AI** を一気通貫    |
|  ◯  | **CKS-JP**（任意）                               | 2026-Q2 以降 | 40–50 h | セキュリティ特化。**採用要件外なら後回し**                      |

> **CKS を外しても** Snowflake／dbt／IaC／MLOps を網羅すればデータエンジニア職での訴求力は十分。  
> ただし将来セキュア設計をリードしたい場合は 2026 Q2 以降で追加取得を検討。

---

## 2. 2025 H2–2026 H1 タイムライン（詳細）

|期間|学習テーマ & アウトプット|学習 Tips / 重点行動|
|---|---|---|
|**7 – 8 月**|**CKA 学習 → 合格** - killer.sh 模擬 2 周回 - etcd/RBAC/バックアップ&リストア - Argo CD で GitOps 体験リポ|_操作高速化_：alias / snippet を整理_学習負荷分散_：朝 CLI 練習、夜 模試復習|
|**9 月**|**Terraform Associate** - AWS / GCP 両クラウドで VPC + EKS/Terraform Cloud - GitHub Actions で `plan → apply` 自動化|コードレビュー習慣：PR に `tflint`,`checkov` を組み込み品質担保|
|**10 月 前半**|**SnowPro Core 学習 → 試験** - Warehouses, Time-Travel, Secure View - スキーマ設計を Qiita or Zenn で記事化|**ハンズオン優先**：自由トライアルで 1 TB 分クエリ実行し性能把握|
|**10 月 後半**|**dbt Cert** + **パイプライン実装** - Snowflake に公開データをロード - dbt Cloud + GitHub CI でモデル自動テスト|dbt の **ref()/source()** 適切配置で DAG 見える化|
|**11 – 12 月**|**SnowPro Advanced: Data Engineer** - Snowpipe / Streams & Tasks / Snowpark - デモ構成を GitHub `demo-snow-de` へ公開|Snowpark Python UDF で変換＋ETL コスト検証しポートフォリオに記録|
|**2026 1 – 2 月**|**MLOps 認定学習＋PoC** - Databricks Delta → Snowflake 外部テーブル連携 - MLflow で実験 → モデル Register → Snowpark へ Serve|MLOps 設計図を Notion にまとめ、**転職面談のネタ資料**に|
|**2026 3 月以降**|**余力あれば CKS** （OPA / mTLS / Kyverno / Falco）|CKS が _求人要件_になった場合のみ前倒し|

---

## 3. スキルシナジーマップ（更新版）

```
                +-------------+         学習済み
                |  Snowflake  |◀─────────┐
                +------+------┘          │  ELT / CI/CD
                       ▲                 │
                       │ dbt             ▼
  +---------+     +----+----+      +-----------+
  |  k8s    |────▶|  IaC    |─────▶| MLOps     |
  +---------+     +---------+      +-----------+
   ▲  (CKA)        (Terraform)       (Databricks / MLflow)
   │
   │ optional
   ▼
  CKS (任意)
```

- **中心は Snowflake**：データウェアハウスの専門性を示す
    
- **周辺は即戦力スキル**：dbt で変換自動化／IaC で再現性／MLOps で分析循環
    
- **CKS は輪の外側**：求人要件次第で追加
    

---

## 4. 直近 90 日アクションプラン（2025-07～09）

|週|目標|具体タスク|成果物|
|---|---|---|---|
|7月 1-2 週|CKA 範囲把握|killer.sh #1 模試 → スコア分析|弱点メモ（Notion）|
|7月 3-4 週|CKA 認証 & トラブルシュート|etcd backup/restore 演習|GitHub Gist：手順|
|8月 1-2 週|CKA 受験 → 合格|killer.sh #2 ／模試|合格証 ＋ 合格記|
|8月 3-4 週|Terraform 基礎|AWS VPC + EKS サンプル|`iac-eks-basic` Repo|
|9月 1-2 週|Terraform CI/CD|GitHub Actions で plan/apply|`terraform-githubaction` Repo|
|9月 3-4 週|Terraform Associate 試験|模試 → 合格|合格証 ／ 学習ノート|

---

## 5. ポートフォリオ運用指針

- **GitHub**：プロジェクトごとに `demo-*` リポジトリ。必ず _Readme にアーキ図＋前提＋CI/CD 手順_ を記述
    
- **Notion**：資格バッジ・模試スコア推移・課題メモをタイムライン形式で管理
    
- **LinkedIn**：資格取得・主要 PoC 完了ごとに英語ポスト（社名タグ付け）で可視性向上
    

---

### Legend

- 🥇 = 最優先（直接的な転職優位性）
    
- 🥈 = 次優先（差別化要素）
    
- ◯ = 任意（求人条件次第で追加）
    

_Last updated: 2025-06-15 → 2025-07-01_
