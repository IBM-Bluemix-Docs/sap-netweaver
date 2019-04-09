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


# IBM Cloud 高可用性支援
{: #ha}

{{site.data.keyword.cloud}} Infrastructure as a Service (IaaS) 在最上層部署可支援高可用性案 (HA) 解決方案的選用性作業系統 (OS)，來為您提供強健的運算環境。解決方案是以支援的 OS 版本（在 [SAP Note 2414097 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 中討論）為基礎。HA 解決方案限制在您的部署所附隨的訂購的 OS 授權或者協力廠商授權，例如自帶授權 (BYOL)。部署之前，請務必要和 {{site.data.keyword.cloud_notm}} 支援中心討論 HA 細節。

{{site.data.keyword.cloud_notm}} 針對 SAP 所支援和部署的作業系統如下
* Linux [Red Hat Enterprise Linux (RHEL) 或 SUSE Enterprise Linux Server (SLES)]，同時支援 SAP NetWeaver 和 SAP HANA HA 解決方案。{{site.data.keyword.cloud_notm}} 環境有一些次要的限制，請參閱 [SAP NetWeaver 高可用性配置概觀](#overview-configs)中的討論。
* Microsoft Windows 僅支援 SAP NetWeaver HA 解決方案（因為 SAP HANA 資料庫限制）。

## SAP NetWeaver 高可用性配置概觀
{: #overview-configs}

有多個文件針對為 SAP 服務進行規劃和安裝 HA 環境提供深度說明。文件包含失效接手、抄寫、橫向擴充，以及災難回復的相關資訊。只要情況適當，還會提供特定文件的參照。

{{site.data.keyword.cloud_notm}} 針對 SAP 部署（Windows、Linux RHEL，和 SLES）支援的所有作業系統和發行套件都附隨高可用性軟體和特定的延伸。以下是支援的 OS 和發行套件。

* [Windows Server 2012 新的失效接手叢集作業改進及其對 SAP NetWeaver 高可用性的優點 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://blogs.sap.com/2013/10/16/new-failover-clustering-improvements-in-windows-server-2012-and-its-benefits-for-sap-netweaver-high-availability/){: new_window}提供以具有 SAP NetWeaver 的 Windows 作業系統上的 Microsoft Windows Server Failover Clustering (WFSC) 為基礎的說明。

* 在具有 Linux Pacemaker 的 Linux 型的 HA 環境中部署 SAP NetWeaver 有兩個參考資料可作為指引。
  * SAP NetWeaver 高可用性叢集 7.40 安裝手冊
  * 使用具有 Pacemaker 的 Red Hat Enterprise Linux HA 附加程式部署高可用性 SAP NetWeaver 型伺服器

* [Building High Availability for SAP NetWeaver and SAP HANA on Linux ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://support.sap.com/content/dam/SAAP/SAP_Activate/AGS_70.pdf){: new_window} 是一個 SAP 最佳作法文件，提供深度的技術說明並著重於 SAP HANA。

* [SAP NetWeaver High Availability and Business Continuity in Virtual Environments with VMware and Hyper-V on Microsoft Windows ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.sap.com/documents/2015/07/508b62bc-5b7c-0010-82c7-eda71af511fa.html){: new_window} 涵蓋虛擬化各個層面，適用於您計劃和虛擬化伺服器上實作 HA 的情況。

如需更多 SAP 合作夥伴針對高可用性情境進行認證的高可用性產品，請參閱[高可用性合作夥伴資訊 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://wiki.scn.sap.com/wiki/display/SI/High+Availability+Partner+Information){: new_window}。對於非 HANA SAP 資料庫，請參閱資料庫文件來取得更多 HA 失效接手及 DR 配置的相關資訊。

請注意，一般而言，網路檔案系統 (NFS)/共用網際網路檔案系統 (CIFS) 儲存空間必須可以共用存取，或者 iSCSI 型邏輯唯一號碼儲存空間 (LUNS) 必須可以共用存取，才能夠支援系統失效接手。一般而言，必須要有搭配抄寫方法的本端儲存空間，才能夠支援 DR 相似安裝。對於內部部署安裝，請在規劃您的部署時檢查資料庫產品的效能以及延遲需求。

## 額外指引
{: #extra-guide}

[仲裁型儲存空間](#quorum)和[網路考量](#network)提供部署期間需要加以考量的事項的指引。除了這些小節概述的考量外，在 HA 環境安裝 SAP NetWeaver 及其資料庫系統和其他內部部署安裝之間並沒有不同之處。

### 仲裁型儲存空間
{: #quorum}

由於 {{site.data.keyword.cloud_notm}} IBM Cloud 環境中的安全限制，不提供使用「智慧型平台管理介面 (IPMI)」。叢集環境通常針對「隔離叢集節點」使用 IPMI 型元件來持續確保仲裁。如果沒有 IPMI 型裝置，將會使用共用儲存空間裝置。在 {{site.data.keyword.cloud_notm}} 環境中，共用儲存空間裝置乃是透過對您的伺服器部署 iSCSI LUN 以作為仲裁裝置的方式來實作。例如，「Microsoft 叢集」上的「檔案共用見證 (FSW)」，以及 Linux Pacemaker 的 Stonith 的「儲存空間型終止 (SDB)」。
* 如需「Linux 高可用性叢集概念」的相關資訊，請按一下[這裡 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://linux-ha.org/wiki/Cluster_Concepts){: new_window}。
* 如需配置和管理 Windows Server 2012 和 Windows Server 2012 R2 的仲裁伺服器的相關資訊，請按一下[這裡 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://docs.microsoft.com/en-us/windows-server/failover-clustering/manage-cluster-quorum){: new_window}。

{{site.data.keyword.cloud_notm}} 儲存空間具有內建 HA 功能，因此一個單一共用的 iSCSI LUN 不會導致「單點故障 (SPOF)」，因為您的網路為冗餘佈置。不過，您的叢集產品的特性可能需要多個仲裁裝置。

### 網路考量
{: #network}

{{site.data.keyword.cloud_notm}} 型安裝附隨下列其中個網路配置：
* 專用網路
* 公用網路
* 公用及專用網路
* 兩個專用網路（依特殊需求）

和內部部署安裝類似，可以根據硬體的實體限制訂購額外的網路配接卡。內部部署安裝也有相同的限制。在硬體部署期間訂購冗餘網路配接卡有助於在您的網路拓蹼中防範 SPOF。冗餘配接卡在具有「鏈結聚集控制通訊協定 (LACP)」的失效接手配置中設定。對於 Linux， 設定使用結合介面，Microsoft Windows 則使用小組配接卡。這些配接卡連接的 {{site.data.keyword.cloud_notm}} 切換基礎架構屬於冗餘，因此不會導致新的 SPOF。訂購的 VLAN 可使用此冗餘基礎架構。

視網路需求而定（例如，DR 設定中的抄寫情境），您必須檢查連接的裝置的位置，以及所討論的產品的任何特定的新網路需求。在某些情況下，{{site.data.keyword.cloud_notm}} Snapshot 儲存空間型抄寫可能可以滿足您的需求。請洽詢 {{site.data.keyword.cloud_notm}} 支援中心來決定適合您商業程序需求的解決方案。
