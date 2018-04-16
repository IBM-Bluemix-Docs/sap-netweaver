---



copyright:
  years: 2018
lastupdated: "2018-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 5. 構成を決定する
{: #determine_configuration}

SAP NetWeaver システムには、以下の 2 つのデプロイメント・オプションがあります。
  * セントラル・システム (単一ホスト・インストール、2 層)
  * 分散システム (マルチホスト・インストール、3 層)
  
これらのオプションは、サーバーの選択に影響を与えます。ワークロードを複数の異なるサーバーに分散することも、簡素化を図るためにワークロードを 1 台のサーバー上に保持することもできます。サーバーのデプロイ方法の段階的なガイダンスについては、[インフラストラクチャーをセットアップする](/docs/infrastructure/sap-netweaver/sap-setting-up-infrastructure.html#set_up_infrastructure)を参照してください。

## ストレージ構成
{: #storage_config}

表 1 は、50,000 [SAPS](docs/infrastructure/sap-netweaver/sap-size-server.html) の 256 GB サーバーのサンプル・ストレージ構成です。SAP を備えた中央システムは 1.5 TB (6,000 IOPS) です。外部 [{{site.data.keyword.cloud_notm}}{{site.data.keyword.blockstorageshort}}](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) または [{{site.data.keyword.cloud_notm}} {{site.data.keyword.filestorage_short}}](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage) (4 IOPS/GB) とともに {{site.data.keyword.Db2_on_Cloud_long}} データベースを使用します。IOPS の計算は次のとおりです。

  * 6,000 IOPS/1,500 GG = 4 IOPS/GB (外部ストレージに必要)。バックアップの前提は 2 IOPS/GB で 3,000 GB (中程度のパフォーマンス) です。
  
表 1. IOPS の計算に基づいたストレージ・レイアウト例

| ファイル・システム | ボリューム数 | ストレージ・タイプ | IOPS/GB | GB | IOPS 数 |
| --- | --- | --- | --- | --- | --- |
| / | 1 | 内部 | N/A | 150 GB | N/A |
| /boot | 1 | 内部 | N/A | 0.25 GB | N/A |
| swap | 1 | 内部 | N/A | 256 GB | N/A |
| /db2 (ログを含む) | 1 | 内部 | N/A | 250 GB | N/A |
| sapdata | 1 | 外部 | 4 IOPS/GB | 1,500 GB | 6,000 IOPS |
| backup/log および backup | 1 | 外部 | 2 IOPS/GB | 3,000 GB | 6,000 IOPS |

## 高可用性構成
{: #ha_config}

{{site.data.keyword.cloud_notm}} 環境は、事前構成された高可用性 (HA) シナリオをサポートしません。ただし、HA シナリオは、選択したオペレーティング・システムの HA 拡張に基づいて構成できます。HA 拡張を追加するには、必要なハードウェアと必要なソフトウェア・コンポーネントをランドスケープに追加します。追加のソフトウェア・ライセンス、または別のソフトウェア・リポジトリーへのアクセスの一方、あるいはその両方が必要な場合は、追加要件のセットアップについて{{site.data.keyword.cloud_notm}}[サポート](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support)にお問い合わせください。

この情報は、SAP NetWeaver の HA ソフトウェアだけでなく、選択したリレーショナル・データベース管理システム (RDBMS) の HA ソフトウェアにも適用されます。これには、RDBMS の高可用性と災害復旧のメカニズム (複製など) が含まれます。セットアップ手順は、オンプレミス環境のセットアップ手順と同じです。同じ手順でハードウェア構成とソフトウェア構成を行う必要があります。

## 次のステップ

これで、{{site.data.keyword.baremetal_short}} のプロビジョニングを開始する準備ができました。次の手順については、[SAP NetWeaver 環境のプロビジョン](/docs/infrastructure/sap-netweaver/sap-provision-environment.html)を参照してください。
  
  


