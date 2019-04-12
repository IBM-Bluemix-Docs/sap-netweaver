---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, network connectivity, VLANs, hybrid, STMS, SAProuter, SAP Solution Manager, SAP certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 規劃 SAP 架構時要考量的項目
{: #considerations}

架構中的 SAP 系統具有連線功能（彼此之間或與外部系統之間）的特定需求。您還需要思考您架構的外部儲存空間，以及如果您決定在伺服器上部署 VMware，則還需要執行些什麼動作。

## 網路連線功能
{: #network_connectivity}

[{{site.data.keyword.cloud_notm}} 網路](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-ibm_cloud_network#ibm_cloud_network)提供網路連線功能的 {{site.data.keyword.cloud}} 方法的概觀。如果您未適當規劃，則無論您打算要如何使用系統，網路連線功能的問題都會造成專案嚴重延遲。

一般而言，對於 IaaS 佈建的 {{site.data.keyword.cloud_notm}} 伺服器，您有兩個介面選擇 - 第一個是具有公用 IP 的外部介面。第二個是有提供「專用 IP」的內部介面，其符合 Request for Comment (RFC) 1918。您也可以選擇具有「專用 IP」的單一內部介面。這兩個選項都可以透過 Linux 的「結合介面」或或透過「Windows 網路介面卡 (NIC)」小組成為備援，且可以具備 100 MB/s、1 Gb/s 及 10 Gb/s 的速度。

視您的使用案例而定，概念驗證 (PoC) 架構或許可接受公用 IP，因為外部 IP 可能更容易使用。即使已安裝及預先配置基本防火牆，仍存在潛在的安全風險。如果您要使用公用介面，務必在訂購伺服器時，為**公用頻寬**選擇足夠高的值。此值決定在一個月期間內，可以透過介面傳送的總資料量。雖然正常網路通訊、SAP 圖形使用者介面 (GUI) 或 SAP 遠端函數呼叫 (RFC) 資料流量，它們每天的總和可能只有幾百萬位元組，但大量資料上傳很容易超過每月 1,000 GB。您必須瞭解依數量級至少傳送的資料量是多少，或者切換至第二個選項。

第二個選項透過 {{site.data.keyword.cloud_notm}} 基礎架構客戶入口網站存取 {{site.data.keyword.cloud_notm}} Virtual Private Network (VPN)，或將安全裝置部署到您的架構。安全裝置是為防火牆、網址轉換、VPN 存取及其他網路功能而提供。此外，這些安全裝置可以提供較高的頻寬，這可協助您將大量資料傳送至 {{site.data.keyword.cloud_notm}} 資料中心。在決定了架構的佈置及 SAP 應用程式層需要的連線功能之後，建議您的網路部門要與 [{{site.data.keyword.cloud_notm}} 支援中心](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support)進行會談。

### VLAN
{: #vlans}

如果您想要在架構中區隔不同類型的網路資料流量，則可以訂購更多虛擬 LAN (VLAN)。請記住，其他 VLAN 只會導致資料流量隔離，而不會提高效能。在 VMware 型精密部署中，需要考量資料流量隔離，為了安全起見，不同類型的網路資料流量可能需要更嚴格地區隔。

以下列使用案例而言，您可能想要確保所有伺服器在部署期間都位於相同的 VLAN 上：
  *	多個伺服器交換資料，例如三層 SAP 設定 - 不同伺服器上的資料庫和 SAP 應用程式實例
  *	多個系統交換大量資料

對於具有本端儲存空間的 SAP 部署，即使是三層設定，1 Gb 型網路就已足夠。可能需要考量更多因素；如需網路儲存空間選項的相關資訊，請參閱[外部儲存空間](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations#external_storage)。

### 混合式設定
{: #hybrid}

{{site.data.keyword.cloud_notm}} for SAP Applications 供應項目可被視為外部資料中心，尤其是當您想要在 {{site.data.keyword.cloud_notm}} 資料中心的一些 SAP 系統上以及現場的其他系統上實作混合式架構時。某些特定配置項目需要考量為在專案的規劃階段中使用混合式設定：

  *	[SAP Transport Management System (STMS) ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.sap.com/products/transportation-logistics.html){: new_window}。請根據「傳輸群組」配置它，以防止在資料中心間共用檔案。
  *	[SAProuter ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://support.sap.com/en/tools/connectivity-tools/saprouter.html){: new_window}。提供對 SAP On-Line Service System (OSS) 的存取。使用已提供的內部部署 SAProuter 來存取 OSS。如果在 {{site.data.keyword.cloud_notm}} 型的系統與內部部署的 SAProuter 之間不允許 IP 型遞送，則可以透過進一步的 SAProuter 中繼站來使用此 SAProuter。或者，您也可以考慮設定另一個 SAProuter，它是基於一個具有公用 IP 且為 {{site.data.keyword.cloud_notm}} 型的伺服器，並透過網際網路將它連接至 SAP OSS 系統。
  *	[SAP Solution Manager ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://support.sap.com/en/solution-manager.html){: new_window}。根據您的使用情境，SAP Solution Manager 的存取在 SAP Solution Manager 與其受管理系統之間，有不同的連線功能需求。這些情境需要瞭解必要的網路連線功能。  

## 外部儲存空間
{: #external_storage}

本端儲存空間提供資料庫部署的最佳效能。除了本端儲存空間之外，您可能需要更多外部儲存空間來執行備份，否則 SAP 系統的資料庫可能會超出內部磁碟的儲存空間容量。另一個範例是您的專案需求可能需要外部儲存空間；例如，對於要共用虛擬機器 (VM) 的多個 ESX 型伺服器。對於這些需求，您可以依照[儲存空間](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-storage#storage)中的說明，來訂購區塊儲存空間或網路連接儲存空間 (NAS)。由於額外區塊儲存空間和 NAS 資料是透過與所有其他網路資料流量的相同實體配接卡傳送，所以需要記住其影響。相較於憑證基準性能測試中所測量的數字，可能僅達到效能數字。

如果您打算主要使用外部儲存空間而非本端儲存空間，則建議您為部署選擇以 10 Gb 為基礎的資料中心。例如，對於備份及資料庫，以及如果您打算讓 SAP 系統有高負載，則使用外部儲存空間。如果您幾乎超載 1 Gb 網路，I/O 負載達到 90 MB/s。

如果您的資料庫主要位於外部儲存空間上，則另一項建議是至少使用 4 IOPS/GB。只有在資料庫效能對您的專案而言不重要，或為了備份時，才應該使用較慢速的儲存空間。

如果您打算使用外部儲存空間作為 VMware ESX 的資料儲存庫，請遵循[與 VMware 系統搭配使用的儲存空間](/docs/infrastructure/vmware?topic=VMware-vmware-storage#vmware-storage)的決策準則，以決定適合您使用案例的最佳儲存空間類型。

## VMware ESXi 伺服器部署
{: #vmware_server}

在 {{site.data.keyword.cloud_notm}} 中，VMware ESXi 型部署與其他雲端型部署不同。{{site.data.keyword.cloud_notm}} 不為其客戶提供執行的 VM；您可以控制自己的環境，並配置它來符合您的需求。當您訂購 VMware ESX 伺服器時，您會收到已配置的伺服器。下列鏈結提供關於其他儲存空間及執行的來賓 VM 的資訊。

  *	[與 VMware 系統搭配使用的儲存空間](/docs/infrastructure/vmware?topic=VMware-vmware-storage#vmware-storage)提供關於如何在 ESX 環境中整合儲存空間的進一步指示。
  * [裝載 iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mount-iscsi-esxi#mount-iscsi-esxi) 說明整合 iSCSI 型儲存空間與 ESX 的步驟。
  * [建立 VMware ESX 虛擬機器](/docs/infrastructure/vmware?topic=VMware-create-esx-vm#create-esx-vm)會引導您完成部署第一個 VM 的處理程序。

請記住，在來賓作業系統中部署 SAP NetWeaver 型的軟體時，您必須從 [SAP 附註 2414097 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 中提及的作業系統中選擇來賓作業系統。
