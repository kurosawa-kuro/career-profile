# Kubernetes ベースの技術スタック一覧 — ML / MLOps 分離版

本ドキュメントは、黒澤俊文様が保有する技術スタックを **Kubernetes** を基盤としたレイヤー構造に基づき整理したものです。**機械学習 (ML) と MLOps** を独立したセクションとして切り出し、職務経歴書や案件提案時の技術アピール資料としてそのままご利用いただけるよう構成しています。追加・修正のご要望があればお気軽にお知らせください。

---

## 1. スタックシナジー

基盤に **Kubernetes** を据え、以下のコンポーネントを統合した **クラウドネイティブアーキテクチャ** を構築：

* **コンテナオーケストレーション**: Kubernetes (EKS / kind)
* **データ基盤**: DWH (Snowflake / Redshift)
* **MLOps**: 機械学習パイプライン & サービング
* **アプリケーション**: イベント駆動型マイクロサービス (Spring Boot)

## 2. 技術スタック詳細

### 2.1 インフラストラクチャ層

#### 2.1.1 コンテナ & オーケストレーション
* **Kubernetes** (EKS / kind)
* Helm / Kustomize / Argo CD / Operator SDK
* Docker / Docker Compose

#### 2.1.2 インフラストラクチャ as Code
* Terraform / Ansible
* OS : Linux (Ubuntu • CentOS) / Windows OS (開発 / 利用環境)

#### 2.1.3 クラウド & サービス（AWS）
* コンテナ: EKS / ECS (Fargate)
* ストレージ: S3 / EBS
* ネットワーク: VPC / ELB / Route 53
* セキュリティ: IAM / KMS / Cognito
* モニタリング: CloudWatch Logs

### 2.2 アプリケーション層

#### 2.2.1 バックエンド
* Spring Boot (Java)
* Gin (Go)
* Express / Nest.js (TypeScript)
* Laravel (PHP) / Ruby on Rails / Scala (Play Framework)

#### 2.2.2 フロントエンド & BFF
* Next.js / React / Tailwind CSS / **Zustand**
* Next.js API Route (BFF)

#### 2.2.3 メッセージング
* **Kafka**
* **RabbitMQ**

### 2.3 データ層

#### 2.3.1 データプラットフォーム
* データウェアハウス: Snowflake / Redshift
* データレイク: S3 / Glue / Athena
* 分析エンジン: DuckDB
* ワークフロー: **dbt** / **Airflow(研究、学習中)**
* データベース: PostgreSQL (主要) / MySQL / Redis

#### 2.3.2 データパイプライン
* ETL/ELT: Glue / **dbt** / DuckDB
* ストリーミング: Kinesis Data Firehose
* 可視化: QuickSight

### 2.4 オブザーバビリティ層

#### 2.4.1 モニタリング & ロギング
* メトリクス: Prometheus / Grafana
* ログ: Loki / **Fluent Bit** / Fluentd
* トレース: Tempo / OpenTelemetry

#### 2.4.2 テスト & CI/CD
* CI/CD: GitHub Actions / Jenkins / CircleCI
* テスト: JUnit / Jest / **Supertest** / React Testing Library / Playwright / RTL

### 2.5 機械学習 & MLOps

#### 2.5.1 機械学習 (ML)
| カテゴリ       | ツール / ライブラリ                                          |
| ---------- | ---------------------------------------------------- |
| **主要言語**   | Python                                               |
| **ライブラリ**  | scikit‑learn / TensorFlow / XGBoost / pandas / NumPy |
| **モデリング**  | LightGBM / CatBoost (補完)                             |
| **モデル最適化** | **ONNX** 変換 & Go バインディング                             |
| **開発環境**   | JupyterLab / VS Code (Remote SSH) / Docker Compose   |

#### 2.5.2 MLOps (パイプライン & サービング) 研究、学習中
| カテゴリ                    | ツール / サービス                                                            |
| ----------------------- | --------------------------------------------------------------------- |
| **パイプライン Orchestrator** | **Airflow** / Argo Workflows                                          |
| **モデル管理**               | MLflow (*検証*) / ONNX Registry (S3 or MinIO)                           |
| **サービング**               | KServe / TensorFlow Serving / FastAPI (Go 組込 ONNX)                    |
| **オーケストレーション**          | Kubernetes (EKS / kind) + GitOps (Argo CD)                            |
| **監視・メトリクス**            | Prometheus + Grafana (モデルメトリクス) / Loki (ログ) / Tempo (トレース)            |
| **CI/CD**               | GitHub Actions (テスト & ビルド) → Argo CD (デプロイ)                           |
| **セキュリティ & ガバナンス**      | Terraform (IaC) / IAM Roles for Service Accounts (IRSA) / S3 バケットポリシー |

---

> **ご活用ください** : 各レイヤー／分野を必要に応じてカスタマイズし、案件ごとの技術要件に合わせたアピール資料としてご利用いただけます。追加のツールやフレームワークを追記する場合はお気軽にお知らせください。
