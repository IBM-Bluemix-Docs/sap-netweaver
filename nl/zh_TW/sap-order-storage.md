---



copyright:
  years: 2018
lastupdated: "2018-01-25"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. 訂購儲存空間
{: #order_storage}

在您部署 {{site.data.keyword.cloud_notm}}{{site.data.keyword.baremetal_short}} 之後，會訂購 {{site.data.keyword.blockstoragefull}}、{{site.data.keyword.filestorage_full_notm}} 及「網路連接儲存空間 (NAS)」。 

## 訂購 {{site.data.keyword.cloud_notm}} 儲存空間
{: #ibm_storage}

您可以使用[佈建和管理{{site.data.keyword.blockstorageshort}}](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage)或[佈建和管理 {{site.data.keyword.filestorage_full_notm}}](https://console.bluemix.net/docs/infrastructure/FileStorage/provisioning-file-storage.html#provisioning-and-managing-ibm-file-storage-for-ibm-cloud) 中的步驟，來訂購備份及還原儲存空間解決方案。會引導您完成處理程序，以決定要使用的儲存空間類型、如何訂購它，以及如何將它部署至伺服器。

*SAP NetWeaver 快速參照手冊（適用於 Microsoft Windows* 或*適用於 Red Hat Enterprise Linux*）會根據 Linux 及 Windows 的範例部署，引導您進行完整的伺服器配置及部署，包括 {{site.data.keyword.cloud_notm}}{{site.data.keyword.blockstorageshort}} 及 iSCSI 配置步驟。

對於 VMware ESXi，{{site.data.keyword.cloud_notm}}儲存空間類型可以用來作為資料儲存庫；在此情況下，它將對映至 ESXi 作為 iSCSI 裝置。請遵循[裝載 iSCSI VMware ESXi](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi) 中的步驟，將 iSCSI 裝置對映至 ESXi。

## 訂購 NAS
{: #order-nas}

如果您需要有用於資料庫的保存日誌檔或用於頻繁的線上及離線備份的儲存空間，則 NAS 儲存空間可能是伺服器本端儲存空間的另一項重要延伸。請造訪[訂購 NAS/FTP 儲存空間](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#ordering-nas-ftp-storage)，以訂購及設定 NAS。此外，請參閱[在 Linux 中裝載 NAS 儲存空間](https://console.bluemix.net/docs/infrastructure/network-attached-storage/mount-nas-storage-linux.html#mounting-nas-storage-in-linux)，以瞭解如何將網路檔案儲存空間 (NFS) 對映至 Linux 伺服器。[NAS 儲存空間也可以透過 NFS 對映至 VMware ESXi 作為資料儲存庫](https://console.bluemix.net/docs/infrastructure/network-attached-storage/connect-nas-storage-windows.html#connecting-to-nas-storage-in-windows)。

## 後續步驟

  [2. 保護環境的安全](/docs/infrastructure/sap-netweaver/sap-secure-environment.html)

  [3. 在 ESX Hypervisor 上安裝來賓作業系統（選用）](/docs/infrastructure/sap-netweaver/sap-installing-guest-operating-system-VMware-deployments.html)

  [4. 下載及安裝 SAP 軟體和應用程式](/docs/infrastructure/sap-netweaver/sap-installing-SAP-landscape.html)
  
  [5. 測試 {{site.data.keyword.cloud_notm}} 資料中心的連線功能](/docs/infrastructure/sap-netweaver/sap-testing-connectivity.html)
