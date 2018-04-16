---



copyright:
  years: 2017, 2018
lastupdated: "2018-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# SAP ランドスケープを計画する際の考慮事項
{: #considerations}

ランドスケープ内の SAP システムには、その内部での相互接続や外部システムへの接続に関する特定の要件があります。また、ランドスケープの外部ストレージについても考慮する必要があります。VMware をサーバーにデプロイすることにした場合には、行うべき作業について考慮する必要もあります。

## ネットワーク接続
{: #network_connectivity}

[{{site.data.keyword.cloud_notm}} ネットワークの説明](/docs/infrastructure/sap-netweaver/sap-about.html#ibm_cloud_network)では、ネットワーク接続に対する {{site.data.keyword.cloud}} のアプローチの概要を記載しました。システムの使用方法に関係なく、ネットワーク接続を適切に計画していないと、その問題が原因になってプロジェクトが大きく遅れるおそれがあります。 

一般的に、IaaS でプロビジョンされた {{site.data.keyword.cloud_notm}} サーバーのインターフェースとして 2 種類の選択肢があります。最初のものはパブリック IP を持つ外部インターフェースです。2 番目のものは、Request for Comment (RFC) 1918 に準拠する「プライベート IP」を持つ内部インターフェースです。「プライベート IP」を持つ単一の内部インターフェースを選択することもできます。どちらのオプションも Linux の「結合インターフェース」または Windows ネットワーク・インターフェース・カード (NIC) チーミングを介して冗長化することが可能で、100 Mb/s、1 Gb/s、10 Gb/s の速度で利用できます。

ユース・ケースによっては、外部 IP の方が使いやすい場合があるため、PoC (概念検証) のランドスケープでパブリック IP を使用できる場合もあります。基本的なファイアウォールをインストールして事前構成した場合でも、潜在的なセキュリティー・リスクは存在します。パブリック・インターフェースを使用する場合は、サーバーの注文時に**パブリック処理能力**を十分高い値に設定してください。この値によって、1 カ月間にインターフェースを介して転送できるデータの総量が決まります。通常のネットワーク通信である SAP グラフィカル・ユーザー・インターフェース (GUI) や SAP リモート関数呼び出し (RFC) のトラフィックは、1 日の合計が数メガバイトに過ぎなかったとしても、大量のデータをアップロードすると、月に 1,000 GB を軽く超えてしまう可能性があります。それで、転送データ量を 1 桁以内の誤差で把握するか、2 番目のオプションに切り替える必要があります。

2 番目のオプションでは、{{site.data.keyword.cloud_notm}} インフラストラクチャーのカスタマー・ポータルから {{site.data.keyword.cloud_notm}} 仮想プライベート・ネットワーク (VPN) にアクセスするか、セキュリティー・デバイスをランドスケープにデプロイします。ファイアウォール、ネットワーク・アドレス変換、VPN アクセス、その他のネットワーク機能用に、セキュリティー・デバイスが提供されています。また、これらのセキュリティー・デバイスは、より高い処理能力を提供できるため、より多くのデータを {{site.data.keyword.cloud_notm}} データ・センターに転送することができます。組織のネットワーキング部門は、ランドスケープのレイアウト、および SAP アプリケーション層で必要な接続を決定した後、[{{site.data.keyword.cloud_notm}} サポート](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support)に連絡することをお勧めします。

### VLAN
{: #vlans}

ランドスケープ内のネットワーク・トラフィックをタイプごとに分離する場合は、追加の仮想 LAN (VLAN) を注文できます。VLAN を追加してもトラフィックが分離されるだけで、パフォーマンスは向上しないことに注意してください。トラフィックを分離するときには、VMware ベースのデプロイメントも綿密に検討する必要があります。このようなデプロイメントでは、セキュリティー上の理由から、異なる種類のネットワーク・トラフィックをより厳密に分離しなければならない場合があるためです。

以下のユース・ケースでは、デプロイメントの際にすべてのサーバーを同じ VLAN 上に配置することをお勧めします。
  *	データを交換する複数のサーバー (異なるサーバー上にある 3 層 SAP セットアップ・データベース・インスタンスや SAP アプリケーション・インスタンスなど)
  *	大量のデータを交換する複数のシステム

ローカル・ストレージを使用する SAP デプロイメントの場合は、3 層セットアップの場合でも、1 Gb ベースのネットワークで十分です。さらに多くの要因を考慮しなければならない場合もあります。ネットワーク・ストレージの選択肢について詳しくは、[外部ストレージ](/docs/infrastructure/sap-netweaver/sap-considerations.html#external_storage)を参照してください。

### ハイブリッド・セットアップ
{: #hybrid}

{{site.data.keyword.cloud_notm}} for SAP Applications オファリングは、外部データ・センターと考えることができます。{{site.data.keyword.cloud_notm}} データ・センターや現場の他のシステムに、SAP システムを組み込んだハイブリッド・ランドスケープを実装することを検討している場合は、特にそう言えます。ハイブリッド・セットアップでプロジェクトの計画フェーズの一部として考慮する必要のある具体的な構成項目を以下に示します。

  *	[SAP 移送管理システム (STMS)](https://help.sap.com/saphelp_me60/helpdata/en/c4/6045377b52253de10000009b38f889/frameset.htm)。データ・センター間でのファイル共有を防止するために、移送グループに基づいて構成します。
  *	[SAProuter](https://support.sap.com/en/tools/connectivity-tools/saprouter.html)。SAP オンライン・サービス・システム (OSS) にアクセスできるようにします。OSS にアクセスするには、既に使用できるオンプレミス SAProuter を使用します。この SAProuter は、{{site.data.keyword.cloud_notm}} ベースのシステムとオンプレミスの SAProuter の間で IP ベースのルーティングが許可されていない場合、SAProuter ホップ繰り返すことによって使用できます。あるいは、パブリック IP を持つ {{site.data.keyword.cloud_notm}} ベースの 1 台のサーバーに基づく別の SAProuter をセットアップし、インターネット経由で SAP OSS システムに接続することもできます。
  *	[SAP Solution Manager](https://support.sap.com/en/solution-manager.html)。SAP Solution Manager へのアクセスは、使用シナリオに応じて、SAP Solution Manager とその管理対象システムの間の接続要件が異なります。これらのシナリオでは、必要なネットワーク接続についての知識が必要です。  

## 外部ストレージ
{: #external_storage}

ローカル・ストレージを使用すると、データベース・デプロイメントに最適なパフォーマンスを得られます。ローカル・ストレージに加えて、バックアップを実行するために追加の外部ストレージが必要になる場合や、SAP システムのデータベースが内部ディスクのストレージ容量を超える場合があります。もう 1 つの例は、プロジェクト要件で外部ストレージが要求されている場合です。例えば、仮想マシン (VM) を共有する複数の ESX ベースのサーバーの場合などです。このような要件の場合は、[ストレージ](/docs/infrastructure/sap-netweaver/sap-general-iaas-concepts.html#storage)の説明に従って、ブロック・ストレージまたは Network Attached Storage (NAS) を注文できます。追加のブロック・ストレージと NAS データは、他のすべてのネットワーク・トラフィックと同じ物理アダプターを介して転送されるため、影響を考慮する必要があります。認証ベンチマークで測定された数値に相当するパフォーマンス数は、単に達成可能であるというだけの場合があります。

ローカル・ストレージの代わりに主に外部ストレージを使用する予定の場合は、デプロイメントに 10 Gb ベースのデータ・センターを選択することをお勧めします。例えば、外部ストレージは、バックアップとデータベースの両方に使用され、SAP システムに高い負荷をかける計画の場合に使用されます。入出力負荷が 90 MB/s であると、1 Gb ネットワークが過負荷に近い状態になります。

もう 1 つの推奨事項として、データベースが主に外部ストレージ上にある場合は、4 IOPS/GB 以上を使用することをお勧めします。これより低速なストレージは、プロジェクトにおいてデータベース・パフォーマンスが重要ではない場合、またはバックアップの目的で使用される場合にのみ使用してください。

VMware ESX のデータ・ストアとして外部ストレージを使用する場合は、[VMware システムで使用するストレージ](https://console.bluemix.net/docs/infrastructure/vmware/select-storage-option-use-vmware.html#storage-to-use-with-vmware-systems)の決定ガイドラインに従って、ご使用のユース・ケースに最適なストレージ・タイプを判別してください。

## VMware ESXi サーバーのデプロイメント
{: #vmware_server}

{{site.data.keyword.cloud_notm}} での VMware ESXi ベースのデプロイメントは、他のクラウド・ベースのデプロイメントとは異なります。{{site.data.keyword.cloud_notm}} は、稼働状態の VM をお客様に提供しません。お客様自身でご使用の環境を制御し、要件を満たすように環境を構成する必要があります。VMware ESX サーバーを注文すると、構成済みのサーバーを受け取ることができます。以下のリンクから、追加ストレージと稼働状態のゲスト VM に関する情報にアクセスすることができます。

  *	[VMware システムで使用するストレージ](https://console.bluemix.net/docs/infrastructure/vmware/select-storage-option-use-vmware.html#storage-to-use-with-vmware-systems)では、ESX 環境でストレージを統合する方法について詳しく説明しています。
  * [iSCSI の VMware ESXi へのマウント](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi)では、SCSI ベースのストレージを ESX に統合する手順について説明しています。
  * [VMware ESX 仮想マシンの作成](https://console.bluemix.net/docs/infrastructure/vmware/vmware-esx-create-virtual-machine.html#creating-a-vmware-esx-virtual-machine)では、VM を初めてデプロイするためのプロセスについて説明しています。

ゲスト OS に SAP NetWeaver ベースのソフトウェアをデプロイする場合は、[SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097) に記載されているオペレーティング・システムからゲスト OS を選択する必要があります。
