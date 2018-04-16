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


# 關於 IBM Cloud for SAP Applications
{: #about_ibmcloud_for_sap}

IBM 與 SAP 在包括硬體、軟體、雲端、服務及融資的不同領域中已組隊、結盟及分工合作超過 45 年。第一個協同作業是在 1972 年，並繼續成長至數百個 SAP 用戶端，它們使用 {{site.data.keyword.cloud}} 作為基礎架構即服務 (IaaS) 解決方案。{{site.data.keyword.IBM_notm}} 繼續將其雲端基礎架構產品最佳化，以支援 SAP NetWeaver 運算平台。 

由於這樣的關係以及其他的 {{site.data.keyword.cloud_notm}} 功能，{{site.data.keyword.IBM_notm}} 獲選為 SAP 的企業關鍵應用程式的雲端基礎架構服務的其中一個傑出策略提供者。可透過高可擴充、開放及高安全性的 {{site.data.keyword.cloud_notm}} 提供對 SAP NetWeaver 產品套組的支援。透過此夥伴關係， SAP NetWeaver 型的應用程式可由全球超過 60 個 {{site.data.keyword.IBM_notm}} 資料中心擴展到主要市場。

此供應項目的特性為具有四個記憶體選項的 {{site.data.keyword.cloud_notm}}{{site.data.keyword.baremetal_short}}：
  * 單插槽 32 GB
  * 雙插槽 128 GB
  * 雙插槽 256 GB
  * 雙插槽 512 GB

所有這四個選項均針對 SAP NetWeaver 而認證，並可提供一個可擴充、高安全性而開放的全球企業雲端平台，以快速部署 SAP 應用程式。

您可以將伺服器用於正式作業、非正式作業或概念驗證 (PoC) 環境。{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 支援所有 SAP NetWeaver Application Server ABAP 型產品，以及 SAP NetWeaver Application Server Java 型產品。若為其他所有軟體元件、非 SAP NetWeaver 型的 SAP 產品或協力廠商產品，請洽詢 [SAP 支援中心](https://support.sap.com/home.html)，瞭解那些產品在 IaaS 供應項目內是否受到支援。

## {{site.data.keyword.cloud_notm}} for SAP NetWeaver 供應項目模型
{: #offer_model}

{{site.data.keyword.cloud_notm}} for SAP Applications 供應項目適合透過 {{site.data.keyword.cloud_notm}} 網路的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 上的幾乎所有 SAP NetWeaver 使用案例支援的情境。

該供應項目是由下列伺服器、作業系統 (OS) 及資料庫所組成：
  * 四種大小的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 以及每一個伺服器附帶的軟體。
      * 4 核心，具有 32 GB RAM
      * 24 核心，具有 128 GB RAM
      * 24 核心，具有 256 GB RAM
      * 28 核心，具有 512 GB RAM
      
  * 作業系統或 Hypervisor
      * 伺服器上的 VMware vSphere ESXi 6.0 或 6.5
      * Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X OS [SAP Business Warehouse (SAP BW) 在 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 的正式作業中受到支援]
      * Microsoft Windows Server（如需版本詳細資料，請參閱 [SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097)）
      
  * 提供的資料庫如下
      * Microsoft SQL Server for Windows（如需版本詳細資料，請參閱 [SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097)）
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Linux（請參閱 [SAP Note 101809](https://launchpad.support.sap.com/#/notes/101809)：支援的版本及修正套件層次）
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Windows（請參閱 [SAP Note 101809-DB6](https://launchpad.support.sap.com/#/notes/101809)：支援的版本及修正套件層次）
      
使用 VMware ESXi 部署的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 可以執行所列出的 RHEL 及 Windows 版本、參照的資料庫，以及 SAP NetWeaver 型的軟體產品。伺服器無法執行任何其他作業系統或非 SAP NetWeaver 型的 SAP 產品。

如需部署 SAP HANA 的相關資訊，請參閱 [{{site.data.keyword.cloud_notm}} 上的 SAP HANA](https://console.bluemix.net/doc/infrastructure/sap-hana/hana-index.html#getting-started)。Future versions of the {{site.data.keyword.cloud_notm}} for SAP Applications 供應項目的未來版本支援其他資料庫、高可用性及災難回復。

如需 {{site.data.keyword.cloud_notm}} 的特定資料庫、作業系統和 SAP NetWeaver 需求，請參閱 [SAP Product Availability Matrix (PAM)](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630)。需要 SAP S 使用者 ID 才能存取 SAP PAM。

## {{site.data.keyword.cloud_notm}} 網路
{: #ibm_cloud_network}

{{site.data.keyword.cloud_notm}} 提供超過 2,000 GB 的連線功能，全球覆蓋區超過 60 個 {{site.data.keyword.cloud_notm}} 資料中心和 28 個據點 (PoP)。{{site.data.keyword.cloud_notm}} 在其所有位置有 20 Gbps 網路連線。這些連線是由先進的全球網路提供者所提供，並且包括許多其他網際網路存取網路的多個公用對等鏈結。

該網路為三個不同的備援性十億位元 (Gb) 網路架構 - 公用、專用及資料中心到資料中心 - 無縫整合至業界的第一個網中網拓蹼。這項設計可提供 IT 基礎架構的最大可存取性、安全及控制。如需相關資訊，請參閱 [IBMCloud 網路](https://www.ibm.com/cloud-computing/bluemix/our-network)。
