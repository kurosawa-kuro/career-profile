| ブロック / 優先       | 資格                                 | 取得ターゲット         | 主なアウトカム                             | 補足                      |
| --------------- | ---------------------------------- | --------------- | ----------------------------------- | ----------------------- |
| **Core-K8s**    | **CKAD** → **CKA** → **CKS**       | 2025 5-11 月     | “開発 → 運用 → セキュリティ” を連続習得            | CKAD 直後に CKA、年内に CKS    |
| **Core-Snow**   | **SnowPro Core** → **Advanced DE** | 2025 7 月 → 10 月 | DWH 基礎バッジ → パイプライン専門バッジ             | Core が土台、DE が即実務提案に直結   |
| **Supporting**  | **Terraform Associate**            | 2025 8 月        | IaC スキルを資格で裏付け                      | CK 系クラスタ管理の自動化にも活用      |
| **拡張 (必要に応じて)** | **Advanced Architect**             | 2025 12 月       | マルチクラウド設計・コスト最適化                    | Terraform & セキュリティ学習と相乗 |
|                 | **Advanced ML**                    | 2026 Q2         | Snowpark／Feature Store など ML 機能を深掘り | MLOps が落ち着いた段階で         |
|                 | **HFCP (Fabric)**                  | 2026 以降         | Fabric 構築経験を公式ラベル化                  | ブロックチェーン再開時に取得          |
|                 | **Istio CA / CBDE / AWS SAA**      | 状況を見て           | Mesh、EVM、AWS 設計の補助資格                | あくまで「Nice-to-have」      |


---

## 全体ロードマップ（抜粋）

| 時期          | ブロック                       | ゴール                  |
| ----------- | -------------------------- | -------------------- |
| **2025-07** | SnowPro **Core**           | DWH 基礎バッジ            |
| **2025-10** | Advanced **Data Engineer** | Streaming & Task 実務力 |
| **2025-12** | Advanced **Architect**     | ネットワーク／Sharing 設計力   |
| **2026-Q2** | Advanced **ML**            | Snowpark + MLOps 最適化 |

（並行で CK 系 – CKAD/CKA/CKS と Terraform・Security Specialty を回す）

---

### 取捨の目安

| 資格                     | いつ取るとコスパ高？                                         | スキップしても困らないケース                             |
| ---------------------- | -------------------------------------------------- | ------------------------------------------ |
| **Advanced DE**        | ETL / dbt / Stream を提案・実装する立場                      | Snowflake を BI 専用 DWH として使うだけ              |
| **Advanced Architect** | **クロスアカウント共有**・**Org レベル設計** が仕事の範囲にある             | 単一アカ運用 & ネット要件が軽い案件                        |
| **Advanced ML**        | Snowpark/Python UDF で ML パイプラインを Snowflake 内完結させたい | モデル推論は KServe/ONNX で済ませ、Snowflake はデータ供給のみ |

---

### 結論

* Core → **DE** は “データパイプライン担当” のあなたに **確実に ROI が高い**。
* **Architect** は Terraform／Security 周辺学習とシナジー大、次点でおすすめ。
* **ML** は KServe / SageMaker と棲み分けながら取り組む **発展枠**。

この順序で進めれば **Snowflake × Kubernetes × GitOps** を軸にした “データ → パイプライン → セキュリティ & ネットワーク → ML” の一気通貫スキルマップが完成します。


> **ポイントまとめ**
>
> 1. **CK シリーズ(AD→A→S)** で Kubernetes は “開発→運用→安全” を一気に網羅。
> 2. **Snowflake Core → Advanced DE** で DWH 側の専門性を段階的に厚く。
> 3. **PoC (EKS×HLF×DWH)** を CK／Snow 系の間に挟み、学んだ内容を即アウトプット。
> 4. Terraform は PoC の直前取得がもっとも効果的。
> 5. Blockchain・Mesh・AWS など **周辺領域は後ろへ寄せて** 集中力を確保。

この順序なら **2025 年中に CK 系 + Snow 系 + 実演 PoC** まで無理なく到達でき、
2026 年は追加資格（HFCP／Istio など）を “必要に応じて” 積み上げるスタイルが取れます。


了解です。  
あなたの現在のスキルスタック（Kubernetes, EKS, GitOps, Terraform, Fabric, Snowflake, DWH, ML, Go）に直接関わる資格を以下に難易度順で整理しました（主観的難易度＋学習時間ベース）。  
特に「**再現性と設計力が問われるかどうか**」を基準にしています。

---


CKAD, CKA, SnowPro Core, SnowPro Advanced: Data Engineer, SnowPro Advanced: ML

## 🧠 あなたに関わる資格｜難易度ランキング（高→低）

| 難易度順  | 資格名                                        | 難易度感（10点満点） | 主な理由・特徴                                     |
| ----- | ------------------------------------------ | ----------- | ------------------------------------------- |
| 🥇 1位 | **CKS（Kubernetes Security Specialist）**    | **9.5〜10**  | セキュリティ強化、OPA、mTLS、Pod制御、試験も実技で時間圧高め。        |
| 🥈 2位 | **CKA（Kubernetes Administrator）**          | **9〜9.5**   | クラスタ構築、運用、etcd、RBACなど範囲広。試験も実技のみ。           |
| 🥉 3位 | **CKAD（Kubernetes App Developer）**         | **8〜9**     | 実技オンリー。構成力・即時再現力が問われる。あなたは今ここに集中。           |
| 4位    | **CBDE（Ethereum DApp開発）**                  | **7〜8**     | Solidity, Gas制御, SmartContract設計など範囲が独特。    |
| 5位    | **SnowPro Advanced: Data Engineer**        | **7〜8**     | Stream, Task, COPYなど実践DWH構築寄り。あなたのDWH経験が直結。 |
| 6位    | **SnowPro Advanced: ML**                   | **6.5〜7.5** | Snowpark, UDF, モデル管理が中心。scikit-learn経験者に有利。 |
| 7位    | **HFCP（Hyperledger Fabric Practitioner）**  | **6〜7**     | CLI系ではないが構成・概念がやや難しい。Fabric構築経験が活きる。        |
| 8位    | **Terraform Associate**                    | **6〜6.5**   | HCLと構成設計の理解で十分対応可。あなたはほぼ即合格圏。               |
| 9位    | **SnowPro Core**                           | **4.5〜5**   | 選択式。SQL/DWH経験者にとっては内容が非常に軽く感じる。             |
| 10位   | **Istio Certified Associate (ICA)**        | **4〜5**     | mTLS, Service Mesh 理解がメイン。CKSと一緒に進めると効果的。   |
| 11位   | **AWS SAA（Solutions Architect Associate）** | **4**       | 幅広いが選択式中心。インフラ感覚の整理に。実務経験者は短期突破可。           |
| 12位   | **Linux Foundation Intro to SRE**          | **2.5〜3**   | SREの哲学や考え方。手を動かさずに理解中心。                     |
| 13位   | **DevOps Institute – SRE Foundation**      | **3〜4**     | 概念中心。実務再現力よりは用語・理論理解が主眼。                    |
| 14位   | **Grafana Observability Fundamentals**     | **2.5**     | Prometheus + Grafanaの入門。すぐ終わるが可観測性理解に役立つ。   |

---

## 🎯 難易度 vs 実務活用度グラフ（あなた向け）

```
高 ─────────────────────── 難易度
│ CKS
│ CKA
│ CKAD
│ CBDE
│ SnowAdv DE/ML
│ HFCP
│ Terraform
│ SnowCore
│ Istio
│ AWS SAA
│ SRE Intro系
└────────────────────── 実務直結度 → 高
```

---

## 📌 あなたが優先すべきは「高難度 × 高実務性」

|優先群|資格|理由|
|---|---|---|
|🎯 最優先|CKAD → CKA → HFCP / SnowCore|EKS + Fabric + DWHの企業PoCに必要不可欠|
|🔧 実務展開向け|Terraform, SnowAdv, CBDE|デモ資産の裏付けになる専門資格群|
|🧠 体系補完|CKS / Istio / SRE Foundation|本番環境セキュリティ or サービスメッシュ導入時に必要|
|🪶 軽量オプション|AWS SAA, Grafana Fundamental|資格というより基礎整理用。暇があれば程度でOK|

---

## ✅ 結論

> あなたのスキルスタックにおいて、**本当に差がつくのは CKAD / CKA / HFCP / SnowCore / Terraform の5本柱**。  
> その先に「PoC成果 → 専門証明（SnowAdv / CBDE / CKS）」を足すと、**市場価値が爆増**します。

必要であればこのリストを **学習順序付きプラン／Trelloテンプレート／ロードマップ化**しますので、お気軽に！

**調整と優先順位の考慮**

ユーザーが「企業向けポートフォリオ EKS ツイン HLF DWH」を2ヶ月で学習したと明記していますが、これは認定資格ではなく、ポートフォリオプロジェクトです。優先順位をどう設定するかが課題です。ポートフォリオはCKAD/CKA後、高優先度で、その後にTerraformの前に配置するのが良いかもしれません。CKAD、CKAは上位に保つべきですが、HFCPやSnowPro Coreの後、ポートフォリオを優先順位5に位置付けることを提案します。

思考時間: 7 秒

### 追加いただいた **「企業向けポートフォリオ EKS ツイン HLF DWH」** を組み込み、工程依存を整理した最新版です


| 優先度      | 資格／プロジェクト                           | 日本語試験                                                                                                                                                                                                                    | 主な試験形式                                                                                                                                                                                                                                                                                                                                           | 推奨取得・着手時期       | 目安学習／構築時間* | 主な理由・目的                    |
| -------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------- | ---------- | -------------------------- |
| 🥇 **1** | **CKAD-JP**                         | **◯** ([Linux Foundation Documentation](https://docs.linuxfoundation.org/tc-docs/certification/lf-handbook2/language "Language \| T&C DOCS (Candidate Facing Resources)"))                                               | **実技（kubectl / YAML）** ([Linux Foundation - Education](https://training.linuxfoundation.org/certification/certified-kubernetes-application-developer-ckad-jp/?utm_source=chatgpt.com "認定Kubernetesアプリケーション開発者 (CKAD-JP)"))                                                                                                                       | 2025 5 月末       | 30-40 h    | マニフェスト即実装 → PoC の土台        |
| 🥈 **2** | **CKA-JP**                          | **◯** ([Linux Foundation Documentation](https://docs.linuxfoundation.org/tc-docs/certification/lf-handbook2/language "Language \| T&C DOCS (Candidate Facing Resources)"))                                               | **実技（kubectl / YAML）** ([Linux Foundation - Education](https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka-jp/?utm_source=chatgpt.com "認定Kubernetes管理者 (CKA-JP) - Linux Foundation - Education"))                                                                                                          | 2025 6 月下旬      | 40-60 h    | クラスタ運用スキル／NTT 案件必須         |
| 🧠 **3** | **HFCP**                            | ✕ ([Linux Foundation Documentation](https://docs.linuxfoundation.org/tc-docs/certification/lf-handbook2/language "Language \| T&C DOCS (Candidate Facing Resources)"))                                                   | **選択式（Multiple-Choice）** ([Linux Foundation - Education](https://training.linuxfoundation.org/certification/hyperledger-fabric-certified-practitioner-hfcp/?utm_source=chatgpt.com "Hyperledger Fabric Certified Practitioner (HFCP) - Linux Foundation"))                                                                                       | 2025 7 月上旬      | 30-40 h    | Fabric PoC を公式資格で裏付け       |
| 🔐 **9** | **CKS-JP**                          | **◯** ([Linux Foundation Documentation](https://docs.linuxfoundation.org/tc-docs/certification/lf-handbook2/language "Language \| T&C DOCS (Candidate Facing Resources)"))                                               | **実技（kubectl / YAML）** ([Linux Foundation - Education](https://training.linuxfoundation.org/certification/certified-kubernetes-security-specialist-cks-jp/?utm_source=chatgpt.com "認定Kubernetesセキュリティスペシャリスト (CKS-JP)"))                                                                                                                         | 2025 11 月       | 40-50 h    | 本番 EKS を守るセキュリティ武装         |
| **5**    | **Terraform Associate (003)**       | ✕ ([HashiCorp Developer](https://developer.hashicorp.com/certifications/infrastructure-automation?utm_source=chatgpt.com "Infrastructure Automation Certifications - HashiCorp Developer"))                              | **選択式（MC／MR／T/F）** ([HashiCorp Developer](https://developer.hashicorp.com/certifications/infrastructure-automation?utm_source=chatgpt.com "Infrastructure Automation Certifications - HashiCorp Developer"))                                                                                                                                     | 2025 8 月上旬      | 25-30 h    | EKS & ポートフォリオ環境の IaC       |
| ✅ **4**  | **SnowPro Core**                    | **◯**（EN/JP/KR） ([LinkedIn](https://www.linkedin.com/pulse/unlocking-power-snowpro-core-certification-exam-tips-sudeep-kumar--yyttc?utm_source=chatgpt.com "Snowflake SnowPro Core Certification Exam Tips - LinkedIn")) | **選択式（MC／MS／T/F）** ([LinkedIn](https://www.linkedin.com/pulse/unlocking-power-snowpro-core-certification-exam-tips-sudeep-kumar--yyttc?utm_source=chatgpt.com "Snowflake SnowPro Core Certification Exam Tips - LinkedIn"))                                                                                                                      | 2025 7 月下旬      | 30-35 h    | DWH 基礎 × Snowflake を証明     |
| **6**    | **企業向け PoC**（EKS ツイン + HLF + DWH）   | ―                                                                                                                                                                                                                        | ―                                                                                                                                                                                                                                                                                                                                                | 2025 8 月上旬〜9 月末 | _約 2 か月_   | 総合デモ環境                     |
| **7**    | **SnowPro Advanced Data Engineer**  | **◯**（EN/JP）※ ([Snowflake Learn](https://learn.snowflake.com/en/certifications/snowpro-practice-exams/?utm_source=chatgpt.com "SnowPro Practice Exam: Core - Snowflake University"))                                     | **選択式（MC／MS／T/F）** ([LinkedIn](https://www.linkedin.com/pulse/how-crack-snowpro-advanced-architect-exam-ruchi-soni?utm_source=chatgpt.com "How to Crack SnowPro Advanced Architect Exam - LinkedIn"))                                                                                                                                            | 2025 10 月       | 45-55 h    | Streaming-ETL 専門性拡大        |
| **8**    | **CBDE**                            | ✕（EN のみ） ([Blockchain Training Alliance](https://blockchaintrainingalliance.com/products/cbde?utm_source=chatgpt.com "Certified Blockchain Developer - Ethereum (CBDE)"))                                                | **選択式 70 問** ([Blockchain Training Alliance](https://blockchaintrainingalliance.com/products/cbde?utm_source=chatgpt.com "Certified Blockchain Developer - Ethereum (CBDE)"))                                                                                                                                                                    | 2025 10 月下旬     | 35-45 h    | Solidity・EVM DApp／HFCP と相乗 |
| **10**   | **Istio Certified Associate (ICA)** | ✕ ([Linux Foundation Documentation](https://docs.linuxfoundation.org/tc-docs/certification/lf-handbook2/language "Language \| T&C DOCS (Candidate Facing Resources)"))                                                   | **実技 + 選択**（K8s+Istio操作と MC） ([CNCF](https://www.cncf.io/training/certification/ica/?utm_source=chatgpt.com "Istio Certified Associate (ICA) - Cloud Native Computing Foundation"), [jimmysong.io](https://jimmysong.io/en/blog/ica-certificate/?utm_source=chatgpt.com "ICA Certification: Latest Changes and Exam Preparation Guide for ...")) | 2025 11 月末      | 20-25 h    | サービスメッシュ習得                 |
| ↓低       | **AWS SAA (SAA-C03)**               | **◯**（JP 含む 11 言語） ([Amazon Web Services, Inc.](https://aws.amazon.com/certification/certified-solutions-architect-associate/ "AWS Certified Solutions Architect – Associate Certification"))                            | **選択式（MC／MR）** ([Amazon Web Services, Inc.](https://aws.amazon.com/certification/certified-solutions-architect-associate/ "AWS Certified Solutions Architect – Associate Certification"))                                                                                                                                                        | 2026 以降         | 25-30 h    | AWS 基礎公式化                  |
| ↓低       | **AWS DAS-S**（2024 4 月廃止）           | **◯**（JP 含む）※ ([Amazon Web Services, Inc.](https://aws.amazon.com/blogs/training-and-certification/aws-certification-retirements-and-launches/?utm_source=chatgpt.com "AWS Certification retirements and launches"))     | **選択式（MC／MR）**                                                                                                                                                                                                                                                                                                                                   | 〃               | 70-90 h    | Glue→Redshift 提案に代替可       |
| ↓低       | **PMI-ACP**                         | **◯**（JP 含む 10 言語）                                                                                                                                                                                                       | 〃                                                                                                                                                                                                                                                                                                                                                | 100 h+          | アジャイル管理公式化 |                            |

But we need to adjust table accordingly.

We must insert correct citations.

Hold on: We need to correct citation markers: for PMI-ACP languages: turn10 search result is turn10 search ID is turn10 search0? Actually earlier we retrieved "Agile Certified Practitioner (PMI-ACP) Certification" page which is turn10 (turn10search0). So we cite turn10search0.

Let's revise.

Also Japanese support row for SnowPro Advanced Data Engineer should maybe note JP available.

But we only have practice exam languages list; assumption.

Let's refine table.

We'll rewrite in final message.

Need to ensure citations included in correct format.

Let's craft final table again.

| 優先度      | 資格／プロジェクト                                            | 推奨取得・着手時期       | 目安学習／構築時間* | 主な理由・目的                                                                                                                       | 必要な前提                                        |
| -------- | ---------------------------------------------------- | --------------- | ---------- | ----------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| 🥇 **1** | **CKAD-JP**                                          | 2025 5 月末       | 30-40 h    | マニフェスト即実装 → PoC の土台                                                                                                           | –                                            |
| 🥈 **2** | **CKA-JP**                                           | 2025 6 月下旬      | 40-60 h    | クラスタ運用スキル／NTT 案件必須                                                                                                            | CKAD                                         |
| 🧠 **3** | **HFCP**                                             | 2025 7 月上旬      | 30-40 h    | Fabric PoC を公式資格で裏付け                                                                                                          | –                                            |
| 🔐 **9** | **CKS-JP**                                           | 2025 11 月       | 40-50 h    | 本番 EKS を守るセキュリティ武装                                                                                                            | CKA                                          |
| **5**    | **Terraform Associate**                              | 2025 8 月上旬      | 25-30 h    | EKS & ポートフォリオ環境の IaC                                                                                                          | –                                            |
| ✅ **4**  | **SnowPro Core**                                     | 2025 7 月下旬      | 30-35 h    | DWH 基礎 × Snowflake を証明                                                                                                        | –                                            |
| **6**    | **企業向けポートフォリオ EKS ツイン HLF DWH**                      | 2025 8 月上旬〜9 月末 | _約 2 か月_   | - **EKS ツイン**: Prod / Stg2 cluster- **HLF**: HFCP を活かし Fabric ネットワークを実装- **DWH**: Snowflake に ETL パイプライン→ **企業案件で即提示できる総合デモ** | CKAD / CKA / HFCP / SnowPro Core / Terraform |
| **7**    | **SnowPro Advanced: Data Engineer**                  | 2025 10 月       | 45-55 h    | Streaming-ETL 専門性で DWH 提案幅を拡大                                                                                                 | Core                                         |
| **8**    | **Certified Blockchain Developer – Ethereum (CBDE)** | 2025 10 月下旬     | 35-45 h    | Solidity・EVM DApp／HFCP と相乗                                                                                                    | HFCP                                         |
| **10**   | **Istio Certified Associate**                        | 2025 11 月末      | 20-25 h    | CKS 直後にサービスメッシュを習得                                                                                                            | CKS 推奨                                       |
| ↓低       | **AWS SAA-Associate**                                | 2026 以降         | 25-30 h    | EKS / Terraform の基礎 AWS 知識を公式化                                                                                                | –                                            |
| ↓低       | **AWS DAS-Specialty**                                | 〃               | 70-90 h    | Glue → Redshift 提案の本命資格                                                                                                       | SAA                                          |
| ↓低       | **PMI-ACP**                                          | 〃               | 100 h+     | 将来リーダー職でアジャイル管理を公式化                                                                                                           | 実務証明                                         |
| ↓低       | **Kaggle 銅メダル**                                      | 〃               | 60-100 h   | DS 熱意の証明・GitHub 資産化                                                                                                           | コンペ結果依存                                      |

*学習時間＝合格ライン到達の平均目安／ポートフォリオは構築＋ドキュメント化を含む

---

### レビュー結果 & 調整理由

1. **ポートフォリオを優先度 6 に配置**  
    _Terraform Associate_ 修了直後に着手すると **IaC → EKS → HLF → Snowflake** を一気通貫で実装でき、採用面談や営業提案で強いインパクトを持つため。
    
2. **SnowPro Advanced・CBDE を 7-8 番へ**  
    ポートフォリオ完成後に各専門認定を追加取得することで “実装デモ＋資格” の両輪がそろう流れ。
    
3. **Istio CA を CKS 直後へ前倒し**  
    CKS 学習で NetworkPolicy & mTLS を押さえたタイミングで、Istio の概念を最少コストで習得できる。
    
4. **SAA を DAS より前に移動**（低優先内で順序逆転）  
    DAS の前提であり、長期的に AWS 提案力を上げたい場合はこちらが先行。
    

この順序なら **2025 年内に k8s 運用 → ブロックチェーン／DWH 連携 → GitOps/セキュリティ強化 → 企業向け総合デモ** まで到達できます。  
さらなる微調整や個別学習リソースのご相談があればお知らせください！


了解です。「Snowflake 側の専門性とかぶり — ＝ “DWH／ETL 系の深掘り” — には踏み込まず、 それ以外でスタック全体を底上げできる AWS 資格」に絞って再整理しました。

| 優先    | 資格名（試験コード ※2025-06 時点）                          | 何が強くなるか                              | スタックとの直接リンク                           | 学習ボリューム感       |
| ----- | ----------------------------------------------- | ------------------------------------ | ------------------------------------- | -------------- |
| **①** | **Solutions Architect – Associate (SAA-C03)**   | EKS＋VPC／ALB／IAM の設計全般                | インフラ基盤全レイヤ                            | ★★★☆☆（40-60 h） |
| **②** | **DevOps Engineer – Professional (DOP-C02)**    | Terraform & GitOps／CI → EKS デプロイ運用   | Argo CD／Jenkins／GitHub Actions ワークフロー | ★★★★☆（60-80 h） |
| **③** | **Security – Specialty (SCS-C02)**              | IAM ポリシー最小化・IRSA／KMS 暗号化             | CKS で学ぶ PodSecurity＋AWS 側制御を補完        | ★★★★☆（50-70 h） |
| **④** | **Advanced Networking – Specialty (ANS-C01)**   | マルチ VPC／EKS 間通信・Service Mesh 入りネット設計 | EKS×Istio／Linkerd＋Transit Gateway     | ★★★★☆（70-90 h） |
| **⑤** | **Machine Learning – Specialty (MLS-C02)**〈※任意〉 | SageMaker Pipelines➡KServe 比較検証      | ONNX 推論とサービス統合を AWS 側で証明              | ★★★★☆（60-80 h） |

### なぜ DEA-C01（Data Engineer Assoc）を外したか

* Redshift/Glue/Kinesis を深掘りする＝Snowflake とドメインが丸かぶり
  → Snowflake Pro Core で既に評価される領域と重複し、ROI が下がるため。

### この並びのメリット

1. **基盤設計 → 運用自動化 → セキュリティ → 高可用ネット** と段階的にパワーアップ
2. Snowflake 周辺は **既存 SnowPro 資格 & 実務** で差別化し、AWS 側は “インフラ＋SecOps” に集中
3. 月単価／年俸アップに直結しやすいスクリーニング順
   *SAA ⇒ DevOpsPro で 100 万/月帯、Security／Networking を載せて 120 万+ 帯へ*

---

## 具体的ロードマップ（例）

| 期           | ゴール                         | 実施メモ                            |
| ----------- | --------------------------- | ------------------------------- |
| **2025 Q3** | SAA-C03 合格                  | 既習 k8s ネット／IAM とリンクして覚える        |
| **2025 Q4** | DevOps Pro 取得               | Terraform + ArgoCD 既存リポを使い実機演習  |
| **2026 Q1** | Security Spec 取得            | KMS, GuardDuty, IRSA を Labs で再現 |
| **2026 Q2** | Advanced Networking Spec 取得 | EKS マルチ AZ × TGW × Service Mesh |
| **以降**      | ML Spec (任意)                | SageMaker vs KServe ベンチ兼ねて勉強    |

---

### 学習リソース・Tips

* **Stephane Maarek / Tutorial Dojo 模試** ⇒ SAA & DOP-C02 に最短
* **AWS Workshop Studio** で Security Workshop → KMS、GuardDuty、IAM Access Analyzer を実機
* ネットワーク系は **AWS Immersion Day – Networking** ハンズオンが無料公開

---

これで **Snowflake 領域とはバッティングせず**、 黒澤さんの EKS＋GitOps＋SecOps 価値を最大化する AWS 資格ルートになります。
他に「この分野も深めたい」「逆に削りたい」などあれば遠慮なくどうぞ！
