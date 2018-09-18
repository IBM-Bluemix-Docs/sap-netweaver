---



copyright:
  years: 2017, 2018
lastupdated: "2018-05-30"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# システム・ランドスケープの計画
{: #planning-your-system-landscape}

SAP *ランドスケープ* とは、複数の SAP *システム* のグループのことで、通常は開発、品質、テスト、実動が含まれます。 1 つの SAP システムは 1 つ以上の *SAP インスタンス* で構成されます。SAP インスタンスとは、同時に開始/停止するプロセスをまとめたものです。 SAP ランドスケープについて詳しくは、[*SAP Business Suite on IBM X6 Systems Reference Architecture*](https://lenovopress.com/redp5073.pdf) を参照してください。 
{: shortdesc}

市販のすべての SAP ソリューションについて、サーバー (サイズ)/ストレージ (サイズ) など、いくつかのランドスケープ構成が考えられます。 これらのソリューションには、[SAP Business Suite](https://open.sap.com/courses/suitehana1)、SAP Business Warehouse、すべての固有の SAP アドオンなどの SAP NetWeaver ベースの製品が含まれます。これらの製品は、{{site.data.keyword.cloud}} SAP-Certified Infrastructure に属するサーバーでサポートされます。SAP NetWeaver ベースでない SAP ソリューションや、SAP と統合される可能性のあるサード・パーティー・ソフトウェアといったソリューションについても留意する必要があります。 {{site.data.keyword.cloud}} IaaS ランドスケープ内に SAP NetWeaver ベースでないソフトウェアかサード・パーティーのソフトウェアをデプロイすることを計画している場合は、[SAP Support](https://support.sap.com/en/index.html) にお問い合わせください。

実行する計画のアプリケーション、拡張の可能性、パフォーマンスに基づいてサーバーのサイズを決定する際には、できるだけ詳細に考慮してください。 また、ご使用のアプリケーションのストレージとメモリーの要件にも留意してください。 ランドスケープ内の SAP システムには、その内部での相互接続や外部システムへの接続に関する特定の要件があります。 詳しくは、[SAP ランドスケープを計画する際の考慮事項](/docs/infrastructure/sap-netweaver/sap-considerations.html)を参照してください。

表 1 には、計画プロセスの手順が記載されています。 この表を使用すると、ターゲットの SAP ランドスケープを構築する際に役立ちます。

表 1. 計画プロセスの概要

| ステップ | 詳細 |
| --- | --- |
| 1 | [SAP と {{site.data.keyword.cloud_notm}} の資格情報を取得してアカウントを作成する](/docs/infrastructure/sap-netweaver/sap-get-credentials.html)|
| 2 | [関連する SAP と {{site.data.keyword.cloud_notm}} の資料を確認する](/docs/infrastructure/sap-netweaver/sap-review-doc.html)|
| 3 | [SAP NetWeaver アプリケーションを決定する](sap-determine-apps.html)|
| 4 | [サーバーのサイズを決定する](/docs/infrastructure/sap-netweaver/sap-size-server.html)|
| 5 | [構成を決定する](/docs/infrastructure/sap-netweaver/sap-determine-configuration.html)|

## 次のステップ

表 1 の該当するステップを選択して、SAP ランドスケープの計画を開始します。

