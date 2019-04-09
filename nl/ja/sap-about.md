---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-18"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.baremetal_short}}, ABAP, application server, SAP Product Availability Matrix, PAM, SAP Certified, SAP Content Server, SAP liveCache

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:note: .note}
{:faq: .faq}


# IBM Cloud SAP-Certified Infrastructure について
{: #about_ibmcloud_for_sap}

IBM と SAP は 45 年以上にわたり、ハードウェア、ソフトウェア、クラウド、サービス、ファイナンシングなどの分野でチームを結成し、パートナーシップを築き、コラボレーションを行ってきました。 コラボレーションの始まりは 1972 年で、それ以降、{{site.data.keyword.cloud}} を Infrastructure as a Service (IaaS) ソリューションとして使用する SAP クライアントの数は増加を続け、今や数百にも及びます。 {{site.data.keyword.IBM_notm}} は、SAP NetWeaver コンピューティング・プラットフォームのサポートを組み込むために、クラウド・インフラストラクチャー製品の最適化を継続的に行ってきました。

このような協力関係がある他に、{{site.data.keyword.cloud_notm}} は機能面でも優れているため、SAP は、ビジネスに不可欠なアプリケーション用のクラウド・インフラストラクチャー・サービスを提供する主要な戦略的プロバイダーの 1 つに、{{site.data.keyword.IBM_notm}} を選びました。 SAP NetWeaver の製品スイートは、高度にスケーラブルでオープン、かつセキュリティー機能が充実した {{site.data.keyword.cloud_notm}} を介してサポートされています。 このようなパートナーシップにより、SAP NetWeaver ベースのアプリケーションは、世界中の 60 カ所を超える {{site.data.keyword.IBM_notm}} データ・センターにより可能となる巨大市場に展開できます。

このオファリングには {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} が含まれており、以下の 8 つのメモリー・オプションから選ぶことができます。
  * シングル・ソケット 32 GB
  * シングル・ソケット 64 GB
  * デュアル・ソケット 128 GB
  * デュアル・ソケット 256 GB
  * デュアル・ソケット 512 GB
  * デュアル・ソケット 192 GB
  * デュアル・ソケット 384 GB
  * デュアル・ソケット 768 GB

8 つのオプションはすべて SAP NetWeaver に対応するものとして認定されており、スケーラブルでセキュリティー機能が充実したオープンなエンタープライズ・クラウド・プラットフォームをグローバルに提供できるので、SAP アプリケーションを迅速にデプロイできます。

実動環境、非実動環境、POC (概念検証) 環境のいずれにおいても、ご使用のサーバーを使用できます。 すべての SAP NetWeaver Application Server ABAP ベースの製品と SAP NetWeaver Application Server Java ベースの製品が、{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} でサポートされています。 IaaS オファリング内でサポートされているその他のすべてのソフトウェア・コンポーネント、非 SAP NetWeaver ベースの SAP 製品、またはサード・パーティー製品については、[SAP サポート ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://support.sap.com/home.html){: new_window} にお問い合わせください。

## {{site.data.keyword.cloud_notm}} for SAP NetWeaver オファリング・モデル
{: #offer_model}

{{site.data.keyword.cloud_notm}} for SAP Applications オファリングは、{{site.data.keyword.cloud_notm}} ネットワーク上の {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} における、事実上すべての SAP NetWeaver ユース・ケース・サポート・シナリオにおいて理想的な選択肢です。

このオファリングは、以下のサーバー、オペレーティング・システム (OS)、データベースで構成されています。
  * 8 種類のサイズの {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} および各サーバーに付属するソフトウェア。
      * 4 コアと 32 GB RAM
      * 4 コアと 64 GB RAM
      * 24 コアと 128 GB RAM
      * 24 コアと 256 GB RAM
      * 28 コアと 512 GB RAM
      * 36 コアと 192 GB RAM
      * 36 コアと 384 GB RAM
      * 36 コアと 768 GB RAM

  * オペレーティング・システムまたはハイパーバイザー
      * サーバー上の VMware vSphere ESXi 6.0 または 6.5
      * Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X OS (SAP Business Warehouse (SAP BW) は、{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} の実動環境でサポートされます)
      * SUSE Linux Enterprise Server (バージョンの詳細については、[SAP Note 2414097 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} を参照)
      * Microsoft Windows Server (バージョンの詳細については [SAP Note 2414097 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} を参照)

  * 提供されるデータベースは以下のとおりです。
      * Microsoft SQL Server for Windows (バージョンの詳細については [SAP Note 2414097 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} を参照)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Linux (サポートされるバージョンとフィックスパック・レベルについては、[SAP Note 101809 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://launchpad.support.sap.com/#/notes/101809){: new_window} を参照)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Windows (サポートされるバージョンとフィックスパック・レベルについては [SAP Note 101809-DB6 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://launchpad.support.sap.com/#/notes/101809){: new_window} を参照)
      * SAP MaxDB (バージョンの詳細については [SAP Note 2414097 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} を参照)
      * SAP ASE 16.0 (詳細については、[SAP Note 2414097 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} を参照)
      * SAP HANA

VMware ESXi でデプロイされた {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} では、リストされているバージョンの RHEL と Windows、参照されているデータベース、SAP NetWeaver ベースのソフトウェア製品を実行できます。 サーバーは、他のオペレーティング・システムや、[SAP Note 2279688 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://launchpad.support.sap.com/#/notes/2279688){: new_window} にリストされている SAP liveCache、SAP Content Server、SAP Business One on Microsft SQL、SAP BusinessObjects などの非 SAP NetWeaver ベースの製品を実行できます。

{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} で SAP NetWeaver ベースの SAP 製品を実行する場合は、サポート対象のいずれかのオペレーティング・システムとデータベースも実行する必要があります。
{: note}

SAP HANA のデプロイについては、[SAP HANA on {{site.data.keyword.cloud_notm}}](/docs/infrastructure/sap-hana?topic=sap-hana-getting-started#getting-started) を参照してください。

{{site.data.keyword.cloud_notm}} のデータベース、オペレーティング・システム、SAP NetWeaver に関する具体的な要件については、[SAP の製品出荷マトリクス (PAM) ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: new_window} を参照してください。SAP PAM にアクセスするには、SAP S ユーザー ID が必要です。

## {{site.data.keyword.cloud_notm}} ネットワーク
{: #ibm_cloud_network}

{{site.data.keyword.cloud_notm}} は、60 カ所を超える {{site.data.keyword.cloud_notm}} データ・センターと 28 カ所の Point of Presence (PoP) から成るグローバル・フットプリント全体で 2,000 GB を超える接続性を備えています。 {{site.data.keyword.cloud_notm}} のロケーション間には 20 Gbps のネットワーク接続があります。 これらの接続は、有数のグローバル・ネットワーク・プロバイダーによって提供されるもので、他の多数のインターネット・アクセス・ネットワークへの複数のパブリック・ピアリング・リンクが設定されています。

このネットワークは、パブリック、プライベート、データ・センター間という 3 つの異なる冗長ギガビット・ネットワーク・アーキテクチャーであり、それぞれが業界初のネットワーク内ネットワークのトポロジーにシームレスに統合されています。 この設計により、IT インフラストラクチャーのアクセシビリティー、セキュリティー、制御が最大限に高められています。 詳しくは、[IBM Cloud ネットワーク ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://www.ibm.com/cloud-computing/bluemix/our-network){: new_window} を参照してください。
