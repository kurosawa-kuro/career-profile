# 職務経歴書 / Résumé – **黒澤 俊文**

- **生年月日** : 1981-02-02(45 歳)
- **居住地** : 札幌(フルリモートのみ可)
- **GitHub** : <https://github.com/kurosawa-kuro>
- **Qiita** : <https://qiita.com/kurosawa_kuro>

---

## 💡 Summary

データサイエンティストが作ったモデルを本番で回し続けるための基盤を、**データ基盤・学習パイプライン・サービング・監視・再学習ループまで一人で設計・実装・運用できる ML プラットフォームエンジニア**。モデリング自体も LightGBM / LambdaRank による学習型リランカーの実装・評価経験あり。

- **10+ yrs** : 要件整理から設計・実装・運用・自動化までを一人称で完遂
- **核となる強み** : モデルのパフォーマンス向上以外の全レイヤーを一人で一気通貫で組める力。Port/Adapter 分離による技術差し替え容易性と、学習/推論の特徴量一致を静的検知する feature parity テストの設計が得意
- **直近の取り組み** : 大手製造業向け GCP ベース MLOps パイプライン強化・評価基盤構築をチームリーダーとして推進。並行して BigQuery-first MLOps、Vertex AI Feature Store、Elasticsearch ハイブリッド検索 + 学習型リランカーの個人検証環境を構築

---

## 🧪 Personal Projects / Technical Validation

案件での意思決定と技術検証を加速させるため、自前の検証環境を整備している。いずれも Port/Adapter 分離により技術要素の差し替えが容易で、評価指標によって「変えて壊れたか」を即座に判定できる。

### bq-first: BigQuery-first MLOps + Vertex Feature Store パイプライン (2026)

> GCP 上で学習 → サービング → 監視 → 自動再学習まで閉じたループを一人で設計・実装。BigQuery / Dataform を offline feature source とし、Vertex AI Feature Store / Feature Group に特徴量を集約することで、学習時特徴量と推論時特徴量の一貫性を担保

**構成**

- BigQuery / Dataform (特徴量マート) → Vertex AI Feature Store / Feature Group → Cloud Run Jobs (training) → GCS artifact → Cloud Run Service (FastAPI serving) → Pub/Sub → BQ Subscription (予測ログ) → Scheduled Query (skew 検知) → Eventarc 経由の自動再学習

**技術的ハイライト**

- Terraform を 4 モジュール (`iam` / `data` / `runtime` / `monitoring`) に分割し、全リソースを IaC で管理
- GitHub Actions と Workload Identity Federation (WIF) による鍵レスデプロイ
- Port/Adapter 分離により ML ロジックを GCP SDK 非依存に保ち、テスト容易性を担保
- BigQuery / Dataform で生成した特徴量を Vertex AI Feature Store / Feature Group に連携し、学習時特徴量と推論時特徴量の一貫性を担保
- Feature parity テストで Dataform SQL ↔ Python ↔ schema.py ↔ BigQuery RECORD 型 ↔ Feature Store schema の一致を静的検知
- 全 130 テスト PASS、ローカル smoke test により GCP 無しでもパイプライン全体を検証可能

**主要技術**: GCP (BigQuery, Vertex AI Feature Store, Vertex AI Feature Group, Cloud Run Service/Jobs, Pub/Sub, Eventarc, Cloud Scheduler, Artifact Registry, Secret Manager) / Terraform / Dataform / LightGBM / FastAPI / Pydantic / uv workspace / GitHub Actions

---

### study-llm-reranking: Elasticsearch ハイブリッド検索 + 学習型リランカー (2026)

> Elasticsearch による BM25 / analyzer ベースの候補検索、multilingual-e5 による意味検索、LightGBM LambdaRank による再ランキングを組み合わせた本番寄りの二段構成検索基盤

**構成**

- Elasticsearch (BM25 / analyzer / synonym による全文検索で候補 100 件取得) → multilingual-e5-large (クエリ埋め込みと物件埋め込みの cosine 類似度) → LightGBM (LambdaRank) による再ランキング
- feedback ログ (click / favorite / inquiry) から学習データを自動生成 → NDCG@10 / MAP / Recall@20 でオフライン評価 → 閾値判定で自動採用/非採用 → 週次再学習の自動実行

**技術的ハイライト**

- Clean Architecture (inbound/outbound Port + UseCase + Domain) による責務分離。Elasticsearch / embedding model / reranker を adapter 単位で差し替え可能な構成を設計
- Elasticsearch の index mapping / analyzer / synonym / scoring を調整し、BM25 候補検索と embedding 類似度、LightGBM LambdaRank の三層で検索品質を改善
- PostgreSQL 10 テーブル (properties / search_logs / property_features / property_embeddings / ranking_compare_logs / offline_eval_reports / kpi_daily_stats / model_adoption_decisions 等) で、検索〜行動ログ〜評価指標〜採用判定までをデータモデルとして閉じさせた設計
- Redis キャッシュのフォールバック方針 (障害時に API を落とさない) をテストで担保
- 日次 (index 同期・特徴量更新・KPI 集計) / 週次 (評価・採用判定・再学習) のバッチを Make ターゲットで整備

**主要技術**: FastAPI / Elasticsearch / multilingual-e5-large / LightGBM (LambdaRank) / PostgreSQL / Redis / Docker Compose / pytest

---

**この 2 つの検証環境が持つ意味**

「どこが本質的に難しく、どこがパターン化できる作業か」を解像度高く語れる状態を維持している。案件で新技術の導入検証依頼があった際、評価指標付きの自前リポジトリで差し替え検証できるため、サイクルタイムを短く保てる。

---

## 🛠 Tech Stack

| 分野 | 主要ツール・サービス |
|---|---|
| **ML / MLOps** | LightGBM (LambdaRank 含む) / scikit-learn / PyTorch / TensorFlow / MLflow / Kubeflow / KServe / Vertex AI Pipelines / Vertex AI Feature Store / W&B / Great Expectations / multilingual-e5 / ONNX Runtime |
| **Data Engineering** | BigQuery / Dataform / Snowflake / Redshift / Airflow / dbt / Athena / Glue / Firehose / Elasticsearch |
| **Cloud Infrastructure** | GCP (Cloud Run Service/Jobs, Vertex AI, BigQuery, Pub/Sub, Eventarc, Cloud Scheduler, Artifact Registry, Secret Manager, VPC) / AWS (EKS, Lambda, ECS, Fargate, IAM, S3, CloudFront, ALB, Cognito, CodePipeline) / Azure |
| **IaC & Automation** | Terraform / Ansible / CloudFormation / AWS CDK / Workload Identity Federation |
| **Container Orchestration** | EKS / Helm / Argo CD / Kustomize / Operator SDK / kubeadm / kind / git-sync |
| **Database** | PostgreSQL / MySQL / Redis / CloudNativePG |
| **Monitoring & Incident** | Cloud Monitoring (log-based metrics / alert policies) / Prometheus / Grafana / Loki / Tempo / PagerDuty |
| **Backend** | Python (FastAPI, Pydantic, uv, SQLAlchemy) / Go (Gin) / TypeScript (Express, NestJS) / Java (Spring Boot, Micronaut) / Ruby on Rails |
| **Frontend** | TypeScript (React, Next.js, Nuxt) / Tailwind CSS / MSW |
| **Testing & CI/CD** | GitHub Actions (composite actions, WIF) / Playwright / Jest / pytest / TestContainers / LocalStack |
| **GPU Computing** | NVIDIA Device Plugin / TensorRT / Kubernetes GPU Scheduling |
| **Blockchain** | Solidity / Hyperledger Fabric |
| **Dev Tools** | Docker / GitHub / GitLab / Ubuntu (WSL) / Makefile / Doppler |

---

## 📜 Certifications

| 年 | 資格 | ステータス |
|---|---|---|
| 2026 | GCP Professional Machine Learning Engineer | 学習中 (直近取得予定) |
| 2025 | HashiCorp Terraform Associate | 学習中 |
| 既取得 | AWS Solutions Architect Associate | 取得済 |
| 既取得 | OSS-DB Silver | 取得済 |

---

## 🧑‍💻 Professional Experience

### 2026-04 – 現在 | フリーランス (チームリーダー)

**大手製造業向け MLOps パイプライン強化・評価基盤構築**

GCP ベースの MLOps パイプラインにおける学習・サービング・監視・再学習ループの強化と、オフライン評価基盤の構築をチームリーダーとして推進。

- Cloud Run / Vertex AI を中心とした学習・推論基盤の改善
- BigQuery / Vertex AI Feature Store を前提とした特徴量管理・再学習パイプラインの設計検証
- Terraform による IaC 整備とデプロイフローの改善
- PagerDuty 連携を含む監視・アラート基盤の設計

**主要技術**: GCP / Python / Terraform / Cloud Run / Vertex AI / Vertex AI Feature Store / BigQuery / PagerDuty

---

### 2025-04 – 2025-12 | フリーランス

**大手 SIer・某省庁向けブロックチェーントレーサビリティシステム PoC**

Hyperledger Fabric ベースのトレーサビリティ基盤 PoC を担当。バックエンド API からインフラまで一人称で実装。

**主要技術**: TypeScript / Next.js / Java (Spring Boot) / AWS / Terraform / Kubernetes / EKS / ActiveMQ

---

### 2025-01 – 2025-03 | 個人開発

**データドリブン EC サービスの PoC**

CloudWatch → Firehose → Glue → Athena → QuickSight のデータパイプラインを構築し、Snowflake への移行を検証。

**主要技術**: TypeScript / Next.js / Go / Rust / AWS CDK / Terraform / Snowflake

---

### 2023-05 – 2024-12 | Wamazing (正社員・バックエンド)

**複数案件のフルスタック担当**

Next.js + Rails / NestJS の複数案件を一人でフルスタック担当。大規模な状態管理リファクタリングを実施。

**主要技術**: TypeScript / Ruby on Rails / NestJS / AWS / Heroku

---

### 2023-02 – 2023-04 | フリーランス

**メタバース系ブロックチェーンゲーム企業のインフラ & DevOps 移行**

VPC / EC2 / FastAPI 環境を Jenkins + Ansible で自動化。

**主要技術**: Python / FastAPI / Jenkins / AWS

---

### 2021-07 – 2022-10 | リモート会議アプリ (受託)

**マイクロサービスの設計・実装**

React + Express のマイクロサービス構成、MySQL バックエンド。予約機能・古データ自動削除を実装し **月間障害ゼロ** を達成。

**主要技術**: TypeScript / React / MySQL / Azure

---

### 2018-07 – 2020-12 | ブロックチェーン企業 (正社員・テックリード)

**ハイブリッド暗号資産ウォレット**

Solidity + Scala + iOS/Android 連携のウォレット基盤をテックリードとして設計・実装。

**主要技術**: Solidity / Scala / Swift / AWS

---

### 2016-11 – 2018-06 | JapanTaxi

**iOS アプリの MVVM 化・社内統合管理システム開発**

**主要技術**: Swift / Ruby on Rails

---

## 🗣 Public Activities

- **Qiita** : 技術記事 100 本超、Udemy インタビュー掲載

---

## 🔗 Links

- Zine Interview : <https://zine.qiita.com/interview/interview_udemy_20170906/>
- Udemy Data Science : <https://zine.qiita.com/products/udemy-datascience/>

<img width="1739" height="755" alt="image" src="https://github.com/user-attachments/assets/1d7e9216-4b3d-4b4f-a9ae-348755a896d9" />

