---



copyright:
  years: 2017, 2018
lastupdated: "2018-01-25"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# IBM Cloud IaaS 上の SAP NetWeaver の概要
Infrastructure as a Service (IaaS) 環境は、データ・センター、コンピュート、接続、ストレージ、ネットワークといった多くのコンポーネントで構成されています。 

## データ・センター

北米、南米、ヨーロッパ、アジア、オーストラリアにデータ・センターが配置され、必要な場所で (必要な時に) クラウド・リソースをプロビジョンできます。各データ・センターは {{site.data.keyword.cloud_notm}} グローバル・プライベート・ネットワークに接続されているため、世界中どこにいてもデータを高速かつ効率的に転送できます。

{{site.data.keyword.cloud_notm}} データ・センターと Point of Presence (PoP) について詳しくは、[データ・センター](https://www.ibm.com/cloud-computing/bluemix/data-centers){: new_window}を参照してください。

## ベア・メタル・サーバー

{{site.data.keyword.baremetal_long}} は、カスタマイズ機能が制限されている物理サーバーです。これらのサーバーは、お客様専用またはお客様の顧客専用であり、サーバー・リソースを含め、いかなる部分も {{site.data.keyword.cloud_notm}} の他のお客様と共有されません。これらのサーバーは、お客様またはお客様の顧客が管理し、ハイパーバイザーなしでプロビジョンされます。

ベア・メタル・サーバーではカスタマイズ機能が制限されているため、1 時間から 4 時間という短時間でプロビジョニングを終えることも不可能ではありません。迅速にプロビジョニングを行う機能は、競合相手より先にアプリを市場に投入しようとしている場合に役立ちます。

SAP 認証サーバーの RAM の量と CPU の数は事前構成されていて、RAM と CPU の組み合わせが多数用意されています。この組み合わせを、注文手続き中に変更することや、サーバーのデプロイ後にサポート・チケットを使って変更することは、*できません*。

プロジェクトに仮想化層が必要な場合、SAP NetWeaver オファリングには、VMware ESXi にデプロイされる {{site.data.keyword.baremetal_short}} を注文するオプションがあります。ESX インスタンスは、お客様のデータ・センターにデプロイされると、お客様が完全に制御できるようになります。システムはネットワーキングに関して完全に構成されています (ストレージなどの追加の構成はお客様が行います)。プロジェクトを正常に開始するには、ESX 管理を理解しているスタッフを含めておくことを強くお勧めします。

ベア・メタル・サーバーについて詳しくは、[ベア・メタル・サーバーについて](https://console.bluemix.net/docs/bare-metal/index.html#about-bare-metal-servers)を参照してください。 

## オペレーティング・システム

SAP NetWeaver ベースのシステムをデプロイするゲスト・オペレーティング・システム (OS) のリストについては、[SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097){: new window} を参照してください。SAP Note にアクセスするには、SAP S ユーザー ID が必要です。ゲスト OS のライセンス交付は、お客様が行います。

## ネットワーク接続

{{site.data.keyword.cloud_notm}} アカウントがセットアップされると、{{site.data.keyword.cloud_notm}} 仮想クラウド・ネットワークへの仮想プライベート・ネットワーク (VPN) 接続が自動的に付与されます。サーバーにはデフォルトで、パブリック IP アドレスとプライベート IP アドレスが割り当てられています。サーバーをプライベートにする場合は、サーバーのプロビジョニング後にパブリック・インターフェースをオフにするか、サーバーをプライベートとして注文することができます。{{site.data.keyword.cloud_notm}} VPN について詳しくは、[Getting started with Virtual Private Networking](https://console.bluemix.net/docs/infrastructure/iaas-vpn/getting-started.html#getting-started-with-virtual-private-networking-vpn-) を参照してください。

## ストレージ
{: #storage}

{{site.data.keyword.baremetal_short}} では、ローカル・ストレージが提供され、{{site.data.keyword.cloud_notm}} プライベート・ネットワーク仮想 LAN (VLAN) を使用して、管理者のアクセスを妨げることなくエンタープライズ・レベルのセキュリティーを確保できます。これは、OS、データベース、アプリケーション・ソフトウェアなどのように、ストレージ使用頻度が多くて入出力ニーズが高いアプリケーションに最適です。SAP NetWeaver サーバーのディスク・スペースは、サーバーの構成方法によって異なります。サーバー上のローカル・ストレージがワークロードに対して不十分である場合は、拡張オプションについて[{{site.data.keyword.cloud_notm}}サポート](https://console.bluemix.net/docs/support/index.html#getting-customer-support)にお問い合わせください。

{{site.data.keyword.cloud_notm}} のストレージには、ブロックとファイルという 2 種類のタイプがあり、SAP NetWeaver のバックアップとリストアを実行するためにそのいずれかを選択できます。どちらのタイプでも、1 秒当たりの入出力操作数 (IOPS) を使用して、ストレージのニーズが判別されます。IOPS は、50/50 読み取り/書き込み混合の 16 KB ブロック・サイズに基づいて測定されます。1 つのボリュームで最大 IOPS を達成するには、適切なネットワーク・リソースを配置する必要があります。その他の考慮事項には、ストレージの外部とホスト・サイドのプライベート・ネットワーク使用量や、アプリケーション固有の調整 (IP スタックやキュー項目数など) などがあります。ストレージ層とパフォーマンスについて詳しくは、[ブロック・ストレージの概説](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage)と[ファイル・ストレージの概説](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage)を参照してください。

{{site.data.keyword.cloud_notm}} は Network Attached Storage (NAS) も提供しています。これはご使用のデバイスにおけるコスト効率の高い高速バックアップ・ソリューションを探している場合に役立ちます。NAS は以下と互換性があります。
  * Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X OS
  * Parallels Plesk Panel と cPanel@WHM の両方を使用するファイル転送プロトコル (FTP)
  * Common Internet File System (CIFS) プロトコルを使用する Windows 標準手順に従う Microsoft Windows Server
  
NAS と FTP ストレージは月次払いで、さまざまなストレージ・サイズで利用できます。主に、OS を使用してコマンド・ラインまたは端末内で、あるいは {{site.data.keyword.cloud_notm}} インフラストラクチャーのカスタマー・ポータル内のパネル上のポイント・アンド・クリック対話を使用して、NAS および FTP ストレージと対話できます。

{{site.data.keyword.cloud_notm}} 環境での NAS について詳しくは、[Getting started with NAS](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#getting-started-with-nas) を参照してください。

## デプロイメントと管理

{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} は、{{site.data.keyword.cloud_notm}} カスタマー・アカウントの作成後に、{{site.data.keyword.cloud_notm}} インフラストラクチャーのカスタマー・ポータルまたは API を介してデプロイされます。サーバーは、カスタマー・ポータル、API、またはコマンド・ライン・インターフェース (CLI) を使用して管理できます。詳しくは、[ベア・メタル・サーバーについて](https://console.bluemix.net/docs/bare-metal/index.html#about-bare-metal-servers)を参照してください。

## サポート

[{{site.data.keyword.cloud_notm}} お客様サポート](https://console.bluemix.net/docs/support/index.html#getting-customer-support)は、チャット、電話、チケット・ベースのサポートなどのさまざまな方法を使用して、サポートに寄せられる質問や問題に対処します。{{site.data.keyword.cloud_notm}} のお客様はすべて無料でお客様サポートを利用できます。お客様サポートは、日々発行されるほとんどのチケットに対応します。詳しくは、[お客様サポートの利用](https://console.bluemix.net./docs/support/index.html#getting-customer-support)を参照してください。
