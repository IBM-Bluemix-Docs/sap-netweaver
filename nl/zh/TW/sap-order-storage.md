---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.blockstorageshort}}, {{site.data.keyword.filestorage_full_notm}}, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.baremetal_short}}

subcollection: sap-netweaver

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

您可以使用[佈建和管理{{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-getting-started#getting-started)或[佈建和管理 {{site.data.keyword.filestorage_full_notm}}](/docs/infrastructure/FileStorage?topic=FileStorage-orderingConsole#orderingConsole) 中的步驟，來訂購備份及還原儲存空間解決方案。會引導您完成處理程序，以決定要使用的儲存空間類型、如何訂購它，以及如何將它部署至伺服器。

*SAP NetWeaver 快速參照手冊（適用於 Microsoft Windows* 或*適用於 Red Hat Enterprise Linux*）會根據 Linux 及 Windows 的範例部署，引導您進行完整的伺服器配置及部署，包括 {{site.data.keyword.cloud_notm}}{{site.data.keyword.blockstorageshort}} 及 iSCSI 配置步驟。

對於 VMware ESXi，{{site.data.keyword.cloud_notm}}儲存空間類型可以用來作為資料儲存庫；在此情況下，它將對映至 ESXi 作為 iSCSI 裝置。請遵循[裝載 iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mount-iscsi-esxi#mount-iscsi-esxi) 中的步驟，將 iSCSI 裝置對映至 ESXi。

## 後續步驟

  [2. 保護環境的安全](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. 在 ESX Hypervisor 上安裝來賓作業系統（選用）](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. 下載及安裝 SAP 軟體和應用程式](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
