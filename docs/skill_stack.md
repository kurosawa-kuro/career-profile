# 技術スタック一覧（レイヤー別） — ML / MLOps 分離版

本ドキュメントは、黒澤俊文様が保有する技術スタックをレイヤー構造に基づき整理したものです。**機械学習 (ML) と MLOps** を独立したセクションとして切り出し、職務経歴書や案件提案時の技術アピール資料としてそのままご利用いただけるよう構成しています。追加・修正のご要望があればお気軽にお知らせください。

---

## 4. 技術スタック一覧（レイヤー別）

## スタックシナジー
k8sを軸に、k8sと相性の良い、dwh,mlopsをアドオン
アプリケーションもk8sと相性が良いイベント駆動 マイクロサービスアーキテクチャをＳｐｒｉｎｇ Ｂｏｏｔで構築

### 4.1 アーキテクチャパターン

* **モノリス**
* **フルスタック**
* **マイクロサービスアーキテクチャ（イベント駆動）**

---

### 4.2 インフラ & IaC

* **Kubernetes** (EKS / kind)
* Helm / Kustomize / Argo CD / Operator SDK
* Terraform / Ansible
* Docker / Docker Compose
* OS :

  * Linux (Ubuntu • CentOS)
  * Windows OS (開発 / 利用環境)

---

### 4.3 クラウド & サービス（AWS）

* EC2 / S3 / VPC / ELB / Route 53
* EKS / ECS (Fargate) / Amplify
* CloudWatch Logs / Cognito / IAM / KMS
* Kinesis Data Firehose / QuickSight
* Glue / RDS / Redshift

---

### 4.4 メッセージング

* **Kafka**
* **RabbitMQ**

---

### 4.5 観測性 (Observability)

* Prometheus / Grafana / Loki / Tempo
* **Fluent Bit** / Fluentd
* OpenTelemetry (Tracing)

---

### 4.6 データプラットフォーム

* Snowflake / Redshift / Glue / Athena / DuckDB
* ワークフロー : **dbt** / **Airflow(研究、学習中)**
* **DB** : PostgreSQL (主要) / MySQL / Redis

---

### 4.7 アプリケーション Back‑end

* Spring Boot (Java)
* Gin (Go)
* Express / Nest.js (TypeScript)
* Laravel (PHP) / Ruby on Rails / Scala (Play Framework など)

---

### 4.8 フロントエンド & BFF

* Next.js / React / Tailwind CSS / **Zustand**
* Next.js API Route (BFF)

---

### 4.9 テスト & CI/CD

* GitHub Actions / Jenkins / CircleCI
* JUnit / Jest / **Supertest** / React Testing Library / Playwright / RTL

---

### 4.10 機械学習 (ML)

| カテゴリ       | ツール / ライブラリ                                          |
| ---------- | ---------------------------------------------------- |
| **主要言語**   | Python                                               |
| **ライブラリ**  | scikit‑learn / TensorFlow / XGBoost / pandas / NumPy |
| **モデリング**  | LightGBM / CatBoost (補完)                             |
| **モデル最適化** | **ONNX** 変換 & Go バインディング                             |
| **開発環境**   | JupyterLab / VS Code (Remote SSH) / Docker Compose   |

---

### 4.11 MLOps (パイプライン & サービング) 研究、学習中。

| カテゴリ                    | ツール / サービス                                                            |
| ----------------------- | --------------------------------------------------------------------- |
| **パイプライン Orchestrator** | **Airflow** / Argo Workflows                                          |
| **データ変換・ETL/ELT**       | Glue / **dbt** / DuckDB                                               |
| **モデル管理**               | MLflow (*検証*) / ONNX Registry (S3 or MinIO)                           |
| **サービング**               | KServe / TensorFlow Serving / FastAPI (Go 組込 ONNX)                    |
| **オーケストレーション**          | Kubernetes (EKS / kind) + GitOps (Argo CD)                            |
| **監視・メトリクス**            | Prometheus + Grafana (モデルメトリクス) / Loki (ログ) / Tempo (トレース)            |
| **CI/CD**               | GitHub Actions (テスト & ビルド) → Argo CD (デプロイ)                           |
| **セキュリティ & ガバナンス**      | Terraform (IaC) / IAM Roles for Service Accounts (IRSA) / S3 バケットポリシー |

---

> **ご活用ください** : 各レイヤー／分野を必要に応じてカスタマイズし、案件ごとの技術要件に合わせたアピール資料としてご利用いただけます。追加のツールやフレームワークを追記する場合はお
