---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, high availability, highly available, HA, disaster recovery, DR, Microsft Windows Server Failover Clustering, WFSC, bring your own license, BYOL, single point of failure, SPOF, Link Aggregation Control Protocol, LACP, VLANs, SAP Certified, database, Linux Pacemaker

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# IBM Cloud の高可用性サポート
{: #ha}

{{site.data.keyword.cloud}} Infrastructure as a Service (IaaS) では、堅固なコンピュート環境の上に、高可用性 (HA) ソリューションをサポートするオプションのオペレーティング・システム (OS) をデプロイできます。HA ソリューションは、サポート対象の OS バージョンがベースになります。これについては、[SAP Note 2414097 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} で説明されています。HA ソリューションは、デプロイメントで一緒に注文した OS ライセンス、または、持ち込みライセンス (BYOL) などのサード・パーティー・ライセンスに制限されます。デプロイする前に、HA に関する詳細について {{site.data.keyword.cloud_notm}} サポートと相談してください。

{{site.data.keyword.cloud_notm}} for SAP でサポートおよびデプロイされるオペレーティング・システムは次のとおりです。
* Linux [Red Hat Enterprise Linux (RHEL) または SUSE Enterprise Linux Server (SLES)] は、SAP NetWeaver および SAP HANA の両方の HA ソリューションをサポートします。{{site.data.keyword.cloud_notm}} 環境には、いくつかの小さな制限があります。これについては、[SAP NetWeaver 高可用性構成の概要](#overview-configs)で説明しています。
* Microsoft Windows は、SAP NetWeaver の HA ソリューションのみをサポートします (SAP HANA データベースの制限のため)。

## SAP NetWeaver 高可用性構成の概要
{: #overview-configs}

SAP サービスのために HA 環境を計画してインストールする方法について詳しく説明したドキュメントが多数あります。これらのドキュメントには、フェイルオーバー、レプリケーション、スケールアウト、および災害復旧 (DR) に関する情報が記載されています。適宜、特定のドキュメントへの参照情報を記載しています。

SAP デプロイメントのために {{site.data.keyword.cloud_notm}} でサポートされているすべてのオペレーティング・システムおよびディストリビューション (Windows および Linux RHEL、および SLES) は、高可用性ソフトウェアおよび固有の拡張機能を備えています。サポートされている OS およびディストリビューションは以下のとおりです。

* [New Failover Clustering Improvements in Windows Server 2012 and Its Benefits for SAP NetWeaver High Availability ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://blogs.sap.com/2013/10/16/new-failover-clustering-improvements-in-windows-server-2012-and-its-benefits-for-sap-netweaver-high-availability/){: new_window} には、SAP NetWeaver を搭載した Windows OS の Microsoft Windows Server Failover Clustering (WFSC) に基づいた説明が記載されています。

* Linux Pacemaker による LINUX ベースの HA 環境に SAP NetWeaver をデプロイする方法については、次の 2 つの参考資料に説明があります。
  * SUSE SAP NetWeaver High Availability Cluster 7.40 Setup Guide
  * Deploying Highly Available SAP NetWeaver-based Servers Using Red Hat Enterprise Linux HA add-on with Pacemaker

* [Building High Availability for SAP NetWeaver and SAP HANA on Linux ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://support.sap.com/content/dam/SAAP/SAP_Activate/AGS_70.pdf){: new_window} は SAP のベスト・プラクティスを集めたドキュメントで、SAP HANAに特化した詳細な技術情報が記載されています。

* [SAP NetWeaver High Availability and Business Continuity in Virtual Environments with VMware and Hyper-V on Microsoft Windows ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://www.sap.com/documents/2015/07/508b62bc-5b7c-0010-82c7-eda71af511fa.html){: new_window} には、仮想サーバーに HA を実装する計画をしている場合に役立つ、仮想化の側面に関する情報が記載されています。

SAP パートナー認定を受けた高可用性シナリオ向けのその他の高可用性製品について詳しくは、[High Availability Partner Information ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://wiki.scn.sap.com/wiki/display/SI/High+Availability+Partner+Information){: new_window} を参照してください。
HANA 以外の SAP データベースを使用する場合は、HA フェイルオーバーおよび DR 構成の詳細については、使用するデータベースの資料を参照してください。

システムのフェイルオーバーをサポートするには、通常、ネットワーク・ファイル・システム (NFS)/共通インターネット・ファイル・システム (CIFS) ストレージへの共有アクセス、または iSCSI ベースの論理装置番号ストレージ (LUNS) への共有アクセスが必要です。DR のようなセットアップをサポートするには、通常、ローカル・ストレージをレプリケーション方式と組み合わせて使用する必要があります。オンプレミスへのインストールと同様に、デプロイメントの計画時にはデータベース製品のパフォーマンスおよび待ち時間の要件を確認してください。

## その他のガイダンス
{: #extra-guide}

[クォーラム・ベースのストレージ](#quorum)および[ネットワークに関する考慮事項](#network)に、デプロイメント時に検討しなければならない考慮事項を記載します。これらのセクションに概説する考慮事項を除けば、SAP NetWeaver とそのデータベース・システムを HA 環境にインストールする作業は、オンプレミスにインストールする場合と違いありません。

### クォーラム・ベースのストレージ
{: #quorum}

{{site.data.keyword.cloud_notm}} IBM Cloud 環境のセキュリティー上の制限により、Intelligent Platform Management Interface (IPMI) を使用したリモート管理デバイスへのネットワーク・ベース・アクセスは利用できません。クラスター環境では、通常、クォーラムを常に確保する「クラスター・ノードのフェンシング」のために、IPMI ベースのコンポーネントが使用されます。IPMI 対応デバイスが存在しない場合は、共有ストレージ・デバイスが使用されます。{{site.data.keyword.cloud_notm}} 環境では、共有ストレージ・デバイスは、iSCSI LUN をサーバーにクォーラム・デバイスとしてデプロイすることで実装されます。例えば、Microsoft クラスターのファイル共有監視 (FSW) や、Linux Pacemaker の Stonith の storage-based death (SDB) があります。
* Linux の高可用性クラスターの概念について詳しくは、[こちら ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](http://linux-ha.org/wiki/Cluster_Concepts){: new_window} をクリックしてください。
* Windows Server 2012 および Windows Server 2012 R2 のクォーラム・サーバーの構成および管理について詳しくは、[こちら ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://docs.microsoft.com/en-us/windows-server/failover-clustering/manage-cluster-quorum){: new_window} をクリックしてください。

{{site.data.keyword.cloud_notm}} ストレージには組み込みの HA 機能があり、ネットワーク・レイアウトが冗長化されているので、単一の共有 iSCSI LUN は単一障害点 (SPOF) にはなりません。しかし、使用するクラスター製品の仕様によっては、複数のクォーラム・デバイスが必要な場合があります。

### ネットワークに関する考慮事項
{: #network}

{{site.data.keyword.cloud_notm}} ベースのインストール環境には、次のいずれかのネットワーク構成が用意されます。
* プライベート・ネットワーク
* パブリック・ネットワーク
* パブリック・ネットワークおよびプライベート・ネットワーク
* 2 つのプライベート・ネットワーク (特別に要求があった場合)

オンプレミスへのインストールと同様に、ハードウェアの物理的な制限に応じて、追加のネットワーク・アダプターを注文することができます。この制限は、オンプレミスにインストールする場合と同じです。ハードウェアのデプロイメント時に冗長なネットワーク・アダプターを注文しておけば、ネットワーク・トポロジーに SPOF が生まれることを回避できます。冗長アダプターは、Link Aggregation Control Protocol (LACP) によるフェイルオーバー構成でセットアップされます。Linux の場合は、セットアップにボンディング・インターフェースが使用され、Microsoft Windows の場合は、チーミング・アダプターが使用されます。それらのアダプターが接続する {{site.data.keyword.cloud_notm}} スイッチ・インフラストラクチャーは冗長化されているので、新たに SPOF が生まれることはありません。冗長インフラストラクチャーは注文した VLAN で使用できます。

ネットワーク要件によっては、例えば DR セットアップのレプリケーション・シナリオなどでは、接続されたデバイスのロケーションや、対象の製品に固有のネットワーク要件を確認しておく必要があります。場合によっては、{{site.data.keyword.cloud_notm}} スナップショットのストレージ・ベースのレプリケーションで、要件を満たせることがあります。ビジネス・プロセスのニーズに最適なソリューションを決定するには、{{site.data.keyword.cloud_notm}} サポートにお問い合わせください。
