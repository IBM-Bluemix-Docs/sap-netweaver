---



copyright:
  years: 2017, 2018
lastupdated: "2018-06-28"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# SAP NetWeaver on IBM Cloud IaaS 概觀
基礎架構即伺服器 (IaaS) 環境包含許多元件：資料中心、運算、連線功能、儲存空間及網路。 

## 資料中心

透過北美洲、南美洲、歐洲、亞洲及澳洲的資料中心，您可以在需要時隨時隨地佈建雲端資源。每個資料中心都連接至 {{site.data.keyword.cloud_notm}} 全球專用網路，讓世界各地的資料傳送更快更有效率。

如需 {{site.data.keyword.cloud_notm}} 資料中心和據點 (PoP) 的相關資訊，請參閱[資料中心](https://www.ibm.com/cloud-computing/bluemix/data-centers){: new_window}。

## 裸機伺服器

{{site.data.keyword.baremetal_long}} 是具有有限自訂功能的實體伺服器。這些伺服器由您或您的客戶專用，且不會與其他 {{site.data.keyword.cloud_notm}} 客戶共用其任何部分（包括伺服器資源）。這些伺服器由您或您的客戶管理，並且在沒有 Hypervisor 的情況下佈建。

因為自訂作業在裸機伺服器上受到限制，所以可以達到 1 到 4 小時的更快佈建時間。當您嘗試在競爭開始之前讓應用程式進入市場時，快速佈建很有幫助。

已為您提供 RAM 及 CPU 組合的陣列，因為 SAP 認證的伺服器具有預先配置的 RAM 數量及 CPU 數目。在訂購處理程序期間，或在部署伺服器之後透過支援問題單，並*無法* 變更組合。

如果您的專案需要虛擬化層級，則 SAP NetWeaver 供應項目包括了訂購隨 VMware ESXi 部署的 {{site.data.keyword.baremetal_short}} 的選項。ESX 實例將完全在您的控制之下，就像部署在您的資料中心內一樣。系統有完整配置的網路功能（任何進一步配置，例如儲存空間，將由您決定）。強烈建議您有對 ESX 管理瞭解的人員，以順利啟動您的專案。

如需裸機伺服器的相關資訊，請參閱[關於裸機伺服器](https://console.bluemix.net/docs/bare-metal/about.html#about-bare-metal-servers)。 

## 作業系統

您需要參閱 [SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097){: new window}，以取得要部署 SAP NetWeaver 型的系統的來賓作業系統 (OS) 的清單。需要 SAP S 使用者 ID 才能存取 SAP Note。已涵蓋來賓作業系統的授權。

## 網路連線功能

設定 {{site.data.keyword.cloud_notm}} 帳戶時，會自動授與 Virtual Private Network (VPN) 與 {{site.data.keyword.cloud_notm}} Virtual Cloud Network 的連線功能。依預設，您的伺服器有公用及專用 IP 位址。如果要讓伺服器成為專用伺服器，則可以在佈建伺服器之後關閉公用介面，或將伺服器訂購為專用伺服器。如需 {{site.data.keyword.cloud_notm}} VPN 的相關資訊，請參閱[開始使用 Virtual Private Networking (VPN)](https://console.bluemix.net/docs/infrastructure/iaas-vpn/getting-started.html#getting-started-with-virtual-private-networking-vpn-)。

## 儲存空間
{: #storage}

本端儲存空間是隨著 {{site.data.keyword.baremetal_short}} 一起提供，它使用 {{site.data.keyword.cloud_notm}} 專用網路虛擬 LAN (VLAN) 來協助提供企業級安全，且不阻礙管理者存取。它很適合具有高 I/O 需求之耗用大量儲存空間的應用程式，例如 OS、資料庫及應用軟體。SAP NetWeaver 伺服器磁碟空間視如何配置伺服器而定。如果伺服器上的本端儲存空間不夠工作負載使用，請聯絡 [{{site.data.keyword.cloud_notm}} 支援中心](https://console.bluemix.net/docs/support/index.html#getting-customer-support)，以取得延伸選項。

{{site.data.keyword.cloud_notm}} 有兩種類型的儲存空間 - 區塊和檔案 - 可從中選擇來執行 SAP NetWeaver 的備份及還原。兩種類型都使用每秒輸入/輸出作業數 (IOPS)，其用來決定儲存空間需求。IOPS 是根據 16 KB 區塊大小與 50/50 讀寫混合大小進行測量。若要達到磁區的 IOPS 上限，需要備妥足夠的網路資源。其他考量包括在儲存空間和主機端外的專用網路使用情形，以及應用程式特定的調整（例如，IP 堆疊及佇列深度）。如需儲存空間層級及效能的相關資訊，請參閱[開始使用區塊儲存空間](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage)和[開始使用檔案儲存空間](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage)。

如果您要為裝置尋找快速、具成本效益的備份解決方案，則 {{site.data.keyword.cloud_notm}} 也提供「網路連接儲存空間 (NAS)」。NAS 與下列各項相容
  * Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X OS
  * 檔案傳送通訊協定 (FTP)，包括 Parallels Plesk Panel 及 cPanel@WHM
  * Microsoft Windows Server，其透過使用「共用網際網路檔案系統 (CIFS)」通訊協定的標準 Windows 程序來進行
  
NAS 及 FTP 儲存空間為每月計費，並有各種不同的儲存空間大小可供使用。您主要可以透過作業系統，在指令行或終端機內與 NAS 及 FTP 儲存空間進行互動，或者透過 {{site.data.keyword.cloud_notm}} 基礎架構客戶入口網站內之畫面上的點按方式來進行互動。

可在[開始使用 NAS](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#getting-started-with-nas) 中找到 {{site.data.keyword.cloud_notm}} 環境中的 NAS 的相關資訊。

## 部署及管理

當您建立 {{site.data.keyword.cloud_notm}} 客戶帳號之後，可透過 {{site.data.keyword.cloud_notm}} 基礎架構客戶入口網站或 API 來部署 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}。伺服器可以透過客戶入口網站、API 或指令行介面 (CLI) 來管理。如需相關資訊，請參考[關於裸機伺服器](https://console.bluemix.net/docs/bare-metal/about.html#about-bare-metal-servers)。

## 支援

[{{site.data.keyword.cloud_notm}}客戶支援中心](https://console.bluemix.net/docs/support/index.html#getting-customer-support)能處理因使用各種銷路（包括會談、電話及問題單型支援）而可能引起的任何支援問題和議題。客戶支援中心免費提供給所有 {{site.data.keyword.cloud_notm}} 客戶，且範圍涵蓋每天所提出的大部分問題單。如需相關資訊，請參閱[取得客戶支援](https://console.bluemix.net./docs/support/index.html#getting-customer-support)。
