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

# 1. 订购存储器
{: #order_storage}

部署 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 后，即订购了 {{site.data.keyword.blockstoragefull}}、{{site.data.keyword.filestorage_full_notm}} 和网络连接的存储器 (NAS)。

## 订购 {{site.data.keyword.cloud_notm}} 存储器
{: #ibm_storage}

您可以执行[供应和管理 {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted#GettingStarted) 或者[供应和管理 {{site.data.keyword.filestorage_full_notm}}](/docs/infrastructure/FileStorage?topic=FileStorage-orderingConsole#orderingConsole) 下的步骤，以订购备份和复原存储器解决方案。这些步骤将逐步指导您确定要使用哪种存储器类型、如何进行订购以及如何将其部署到服务器。

使用 *SAP NetWeaver 快速参考指南（针对 Microsoft Windows* 或*针对 Red Hat Enterprise Linux*），可以执行完整的服务器配置和部署，包括基于 Linux 和 Windows 的样本部署的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}} 和 iSCSI 配置步骤。

对于 VMware ESXi，可以使用 {{site.data.keyword.cloud_notm}} 存储器类型作为数据存储器；在此情况下，会将其作为 iSCSI 设备映射到 ESXi。遵循[安装 iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mounting-iscsi-vmware-esxi#mounting-iscsi-vmware-esxi) 中的步骤，以将 iSCSI 设备映射到 ESXi。

## 后续步骤

  [2. 保护环境](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. 在 ESX 管理程序上安装访客操作系统（可选）](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. 下载和安装 SAP 软件和应用程序](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
