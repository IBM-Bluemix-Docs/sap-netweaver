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


# 關於 IBM Cloud SAP 認證基礎架構
{: #about_ibmcloud_for_sap}

IBM 與 SAP 在包括硬體、軟體、雲端、服務及融資的不同領域中已組隊、結盟及分工合作超過 45 年。第一個協同作業是在 1972 年，並繼續成長至數百個 SAP 用戶端，它們使用 {{site.data.keyword.cloud}} 作為基礎架構即服務 (IaaS) 解決方案。{{site.data.keyword.IBM_notm}} 繼續將其雲端基礎架構產品最佳化，以支援 SAP NetWeaver 運算平台。

由於這樣的關係以及其他的 {{site.data.keyword.cloud_notm}} 功能，{{site.data.keyword.IBM_notm}} 獲選為 SAP 的企業關鍵應用程式的雲端基礎架構服務的其中一個傑出策略提供者。可透過高可擴充、開放及高安全性的 {{site.data.keyword.cloud_notm}} 提供對 SAP NetWeaver 產品套組的支援。透過此夥伴關係， SAP NetWeaver 型的應用程式可由全球超過 60 個 {{site.data.keyword.IBM_notm}} 資料中心擴展到主要市場。

此供應項目的特性為具有八個記憶體選項的 {{site.data.keyword.cloud_notm}}{{site.data.keyword.baremetal_short}}：
  * 單插槽 32 GB
  * 單插槽 64 GB
  * 雙插槽 128 GB
  * 雙插槽 256 GB
  * 雙插槽 512 GB
  * 雙插槽 192 GB
  * 雙插槽 384 GB
  * 雙插槽 768 GB

所有這八個選項均針對 SAP NetWeaver 而認證，並可提供一個可擴充、高安全性而開放的全球企業雲端平台，以快速部署 SAP 應用程式。

您可以將伺服器用於正式作業、非正式作業或概念驗證 (POC) 環境。{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 支援所有 SAP NetWeaver Application Server ABAP 型產品，以及 SAP NetWeaver Application Server Java 型產品。對於所有其他軟體元件、非 SAP NetWeaver 型的 SAP 產品，或者協力廠商產品，請聯絡 [SAP 支援中心 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://support.sap.com/home.html){: new_window}，以瞭解那些產品在 IaaS 供應項目內是否受到支援。

## {{site.data.keyword.cloud_notm}} for SAP NetWeaver 供應項目模型
{: #offer_model}

{{site.data.keyword.cloud_notm}} for SAP Applications 供應項目適合透過 {{site.data.keyword.cloud_notm}} 網路的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 上的幾乎所有 SAP NetWeaver 使用案例支援的情境。

該供應項目是由下列伺服器、作業系統 (OS) 及資料庫所組成：
  * 八種大小的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 以及每一個伺服器附帶的軟體。
      * 4 核心，具有 32 GB RAM
      * 4 核心，具有 64 GB RAM
      * 24 核心，具有 128 GB RAM
      * 24 核心，具有 256 GB RAM
      * 28 核心，具有 512 GB RAM
      * 36 核心，具有 192 GB RAM
      * 36 核心，具有 384 GB RAM
      * 36 核心，具有 768 GB RAM

  * 作業系統或 Hypervisor
      * 伺服器上的 VMware vSphere ESXi 6.0 或 6.5
      * Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X OS [SAP Business Warehouse (SAP BW) 在 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 的正式作業中受到支援]
      * SUSE Linux Enterprise Server（請參閱 [SAP 附註 2414097 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 來取得版本詳細資料）
      * Microsoft Windows Server（請參閱 [SAP 附註 2414097 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 來取得版本詳細資料）

  * 提供的資料庫如下
      * Microsoft SQL Server for Windows（請參閱 [SAP 附註 2414097 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 來取得版本詳細資料）
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Linux（請參閱 [SAP 附註 101809 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/101809){: new_window}: Supported versions and fix pack levels）
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Windows（請參閱 [SAP 附註 101809-DB6 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/101809){: new_window}: Supported versions and fix pack levels）
      * SAP MaxDB（請參閱 [SAP 附註 2414097 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 來取得版本詳細資料）
      * SAP ASE 16.0（請參閱 [SAP 附註 2414097 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 來取得詳細資料）
      * SAP HANA

使用 VMware ESXi 部署的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 可以執行所列出的 RHEL 及 Windows 版本、參照的資料庫，以及 SAP NetWeaver 型的軟體產品。這些伺服器可以執行其他作業系統或非 SAP NetWeaver 型的產品，例如 [SAP 附註 2279688 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/2279688){: new_window} 上所列出的 SAP liveCache、SAP Content Server、SAP Business One on Microsft SQL，以及 SAP BusinessObjects。

如果您在 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 上執行 SAP NetWeaver 型的 SAP 產品，您還必須執行其中一個支援的作業系統和資料庫。
{: note}

如需部署 SAP HANA 的相關資訊，請參閱 [SAP HANA on {{site.data.keyword.cloud_notm}}](/docs/infrastructure/sap-hana?topic=sap-hana-getting-started#getting-started)。

請參閱 [SAP Product Availability Matrix (PAM) ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: new_window} 來瞭解 {{site.data.keyword.cloud_notm}} 的特定資料庫、作業系統，以及 SAP NetWeaver 的需求。需要 SAP S 使用者 ID 才能存取 SAP PAM。

## {{site.data.keyword.cloud_notm}} 網路
{: #ibm_cloud_network}

{{site.data.keyword.cloud_notm}} 提供超過 2,000 GB 的連線功能，全球覆蓋區超過 60 個 {{site.data.keyword.cloud_notm}} 資料中心和 28 個據點 (PoP)。{{site.data.keyword.cloud_notm}} 在其所有位置有 20 Gbps 網路連線。這些連線是由先進的全球網路提供者所提供，並且包括許多其他網際網路存取網路的多個公用對等鏈結。

該網路為三個不同的備援性十億位元 (Gb) 網路架構 - 公用、專用及資料中心到資料中心 - 無縫整合至業界的第一個網中網拓蹼。這項設計可提供 IT 基礎架構的最大可存取性、安全及控制。如需相關資訊，請參閱 [IBM Cloud 網路 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/cloud-computing/bluemix/our-network){: new_window}。
