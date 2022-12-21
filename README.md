<div align="center">
<h1>
<img width="30", src="./docs/images/azureml-icon.svg"> 
&nbsp;
MLOps with Azure Machine Learning
</h1>
Azure Machine Learning + GitHub を利用した MLOps 実装サンプルコード

[![MIT licensed](https://img.shields.io/badge/license-MIT-brightgreen.svg)](LICENSE)
[![](https://img.shields.io/github/contributors-anon/Azure/MLInsider-MLOps)](https://github.com/Azure/MLInsider-MLOps/graphs/contributors)
[![Star](https://img.shields.io/github/stars/Azure/MLInsider-MLOps.svg)](https://github.com/Azure/MLInsider-MLOps)


</div>

---

## 👋 概要
本リポジトリは、MLOps のサンプルコードを素早く利用できることを目的に作成されました。Azure Machine Learning と GitHub Actions を利用する想定です。 


## 🚀 使い方
- Azure Machine Learning と GitHub の環境を準備します。
- .env ファイルに環境変数の設定をします。
- GitHub の Secrets を作成します。
- [./scripts](./scripts) フォルダの各シェルスクリプトを実行します。
- 更に詳しい手順や参考資料は [./docs/README.md](./docs/README.md) の各ドキュメントを参照してください。


## 📝 技術条件
- GitHub
    - ソースコード管理、CI/CD パイプライン
- Data
    - [NYC タクシー & リムジン協会 - グリーンタクシー運行記録](https://learn.microsoft.com/ja-jp/azure/open-datasets/dataset-taxi-green?tabs=azureml-opendatasets)
- Azure Machine Learning
    - チーム・組織で共有の機械学習プラットフォーム
    - Compute Instance : CPU タイプ、クライアント端末 (もしくは Dev Container に対応した GitHub Codespace など)
    - Compute Cluster : 共有のクラスター環境
- IDE/Editor
    - Visual Studio Code

## 📁 コンテンツ
### Assets
**CLI v2 + YAML**
|シナリオ              |YAML ファイル|シェルスクリプト|詳細        |
|--------------------|---------|-----------|-----------|
|Create Data asset   |[assets/create-data.yml](assets/create-data.yml)|[scripts/assets/create-data.sh](scripts/assets/create-data.sh)|データアセットを作成する|
|Create Compute Cluster|[assets/create-compute.yml](assets/create-compute.yml)|[scripts/assets/create-compute.sh](scripts/assets/create-compute.sh)|Compute を作成する|
|Create Environment for training|[assets/create-environment.yml](assets/create-environment.yml)|[scripts/assets/create-environment.sh](scripts/assets/create-environment.sh)|環境を作成する|

### Prototyping
**Notebook**

|シナリオ              |Notebook|シェルスクリプト|詳細        |
|--------------------|---------|-----------|-----------|
|Baseline Notebook   |[notebooks/train-prototyping.ipynb](notebooks/train-prototyping.ipynb)|[scripts/prototyping/run-notebook.sh](scripts/prototyping/run-notebook.sh)|実験用の Notebook|


### Training
**CLI v2 + YAML**
|シナリオ              |YAML ファイル|シェルスクリプト|詳細        |
|--------------------|---------|-----------|-----------|
|Job for training model |[jobs/train.yml](jobs/train.yml)           |[scripts/training/train.sh](scripts/training/train.sh)| Azure ML の Job として Python script を実行 |


**CI/CD Pipeline**
|シナリオ              |YAML ファイル|Status     |詳細        |
|--------------------|---------|-----------|-----------|
|Smoke Test          |[.github/workflows/smoke-testing.yml](.github/workflows/smoke-testing.yml)|[![smoke-testing](https://github.com/Azure/MLInsider-MLOps/actions/workflows/smoke-testing.yml/badge.svg)](https://github.com/Azure/MLInsider-MLOps/actions/workflows/smoke-testing.yml)|Smoke Test パイプライン|


### Operationalizing
**CLI v2 + YAML**
|シナリオ                            |YAML ファイル |シェルスクリプト|詳細        |
|----------------------------------|---------|-----------|-----------|
|Create Batch Endpoint (custom)  |[jobs/batch_deployment.yml](jobs/batch_deployment.yml)|[scripts/operationalizing/deploy-batch-endpoint.sh](scripts/operationalizing/deploy-batch-endpoint-custom.sh)           |カスタム型モデルのバッチエンドポイントへのデプロイ|
|Create Batch Endpoint (mlflow)  |[jobs/batch_deployment_mlflow.yml](jobs/batch_deployment_mlflow.yml)|[scripts/operationalizing/deploy-batch-endpoint.sh](scripts/operationalizing/deploy-online-endpoint-mlflow.sh)|MLflow 型モデルのバッチエンドポイントへのデプロイ|
|Create Online Endpoint (custom)  |[jobs/online_deployment.yml](jobs/online_deployment.yml)|           |           |
|Create Online Endpoint (mlflow)  |[jobs/online_deployment_mlflow.yml](jobs/online_deployment_mlflow.yml)|           |           |

---
## 🗒️ ドキュメンテーション
- [Coding Guideline](./docs/coding-guidelines.md)
---
## 📄 ディレクトリ構造

>TODO

## 関連リポジトリ/リソース

### 主要なリポジトリ/リソースとの比較
| リポジトリ/リソース名 | 概要と目的 | 本リポジトリとの差異 |
| --- | --- | --- |
| [microsoft/MLOps](https://github.com/microsoft/MLOps) | MLOps の概要説明から、Microsoft 製品でどのように MLOps を実現するのか Azure DevOps や GitHub Actions、IaCなどのツール単位やシナリオ単位でサンプルコードを提供している。 | 本リポジトリは、ツールを１シナリオに絞り、迅速的に活用可能な MLOps のテンプレートを提供する。|
| [Azure/mlops-v2](https://github.com/Azure/mlops-v2) | MLOps に関してより広範で抽象的なテンプレート。 | 本リポジトリは、より具体的なデータ・コードを含み、実行可能なサンプルを目指している。|
| [Azure/azureml-examples](https://github.com/Azure/azureml-examples) | AzureML に関してのサンプルコード集。テストコード等が整備されている。 | 本リポジトリは、単発のサンプルコード群ではなく、ML ライフサイクルの一連の流れが end-to-end で網羅されたものを目指している。|
| [Tutorial: Azure Machine Learning in a day](https://learn.microsoft.com/en-us/azure/machine-learning/tutorial-azure-ml-in-a-day) | End-to-End で AzureML を学ぶことができるチュートリアルページ。 | 本リポジトリは、比較対象のリポジトリでは掲載されていない ML システムを設計・運用していくための Tips も提供している。|

### その他
- https://github.com/dslp/dslp-repo-template

## 🛡 免責事項
当社は、外部のリンク先ウェブサイトの内容に関していかなる責任も負うものではありません。お客様は、自らの責任においてこれらのリンクをご利用ください。なお、お客様によるリンクご利用の結果、ないしはリンクご利用に関連して、お客様が被るいかなる損害または損失について当社は、責任を負うものではありません。

## 🤝 Contributing
We are welcome your contribution from customers and internal microsoft employees. Please see [CONTRIBUTING](./CONTRIBUTING.md). We appreciate all contributors from Microsoft employees and community to make this repo thrive.


<a href="https://github.com/Azure/MLInsider-MLOps/graphs/contributors"><img src="https://contrib.rocks/image?repo=Azure/MLInsider-MLOps&max=240&columns=18" /></a>

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft
trademarks or logos is subject to and must follow
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
