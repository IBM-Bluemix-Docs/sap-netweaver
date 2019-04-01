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

# 规划 SAP 格局时要考虑的事项
{: #considerations}

格局中的 SAP 系统在彼此的连接或与外部系统的连接方面存在特定需求。针对格局，还需要考虑外部存储器，以及决定在服务器上部署 VMware 时要执行的操作。

## 网络连接
{: #network_connectivity}

[{{site.data.keyword.cloud_notm}} 网络](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-ibm_cloud_network#ibm_cloud_network)提供了网络连接的 {{site.data.keyword.cloud}} 方法的概述。如果未正确规划，那么不管您计划如何使用系统，网络连接问题都可能会导致项目严重延迟。

通常，针对 IaaS 供应的 {{site.data.keyword.cloud_notm}} 服务器，您有两个接口选项：第一个是具有公共 IP 的外部接口。第二个是内部接口，提供了“专用 IP”，符合请求评论 (Request for Comment, RFC) 1918。也可以选择具有“专用 IP”的单个内部接口。这两个选项都可通过 Linux“结合接口”或通过 Windows 网络接口卡 (NIC) 组合来实现冗余，并且能够以 100 Mb/秒、1 Gb/秒和 10 Gb/秒的速度运行。

根据您的用例，公共 IP 可能适用于概念证明 (PoC) 格局，因为外部 IP 可能更易于使用。尽管安装并预配置了基本防火墙，也存在潜在的安全风险。如果要使用公共接口，请确保在订购服务器时为**公共带宽**选择一个足够大的值。此值确定在一个月内可以通过该接口传输的数据总量。虽然正常网络通信、SAP 图形用户界面 (GUI) 或 SAP 远程函数调用 (RFC) 流量可能每天总共仅达到数兆字节，但每月的大量数据上传可轻易超过 1,000 GB。您需要至少知道传输的数据量的数量级，或者切换到第二个选项。

第二个选项通过 {{site.data.keyword.cloud_notm}} 基础架构客户门户网站访问 {{site.data.keyword.cloud_notm}} 虚拟专用网 (VPN)，或者将安全设备部署到您的格局中。针对防火墙、网络地址转换、VPN 访问和其他网络功能提供了安全设备。此外，这些安全设备还可实现更高带宽，这可帮助您将更多数据传输到 {{site.data.keyword.cloud_notm}} 数据中心。建议在确定格局布局以及 SAP 应用程序层上所需的连接后，让您的网络部门与 [{{site.data.keyword.cloud_notm}} 支持人员](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support)联系和交流。

### VLAN
{: #vlans}

如果要在格局中隔离不同类型的网络流量，那么可订购更多虚拟 LAN (VLAN)。请记住，采用更多 VLAN 仅可以隔离流量，而不会提高性能。对于基于 VMware 的复杂部署，可能需要更严格地隔离不同类型的网络流量以确保安全，在此情况下，需要考虑隔离流量。

对于以下用例，可能希望确保所有服务器在部署期间都位于同一 VLAN 上：
  *	交换数据的多台服务器，例如，三层 SAP 设置 - 数据库和 SAP 应用程序实例位于不同服务器上
  *	交换大量数据的多个系统

对于具有本地存储器的 SAP 部署，甚至对于三层设置，基于 1 Gb 的网络也已足够。可能需要考虑更多因素；请参阅[外部存储器](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations#external_storage)，以获取有关网络存储器选项的更多信息。

### 混合设置
{: #hybrid}

{{site.data.keyword.cloud_notm}} for SAP Application 产品可以视为外部数据中心，尤其是当您考虑使用 {{site.data.keyword.cloud_notm}} 数据中心内一些 SAP 系统以及其他现场系统来实现混合格局时更是如此。在使用混合设置的项目规划阶段，需要考虑一些具体的配置项：

  *	[SAP Transport Management System (STMS) ![](../../icons/launch-glyph.svg "外部链接图标")](https://www.sap.com/products/transportation-logistics.html){: new_window}。基于传输组对其进行配置以阻止在数据中心之间共享文件。
  *	[SAProuter ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://support.sap.com/en/tools/connectivity-tools/saprouter.html){: new_window}。提供对 SAP 联机服务系统 (OSS) 的访问。使用内部部署 SAProuter（已经可用）访问 OSS。如果在基于 {{site.data.keyword.cloud_notm}} 的系统和内部部署 SAProuter 之间不允许进行基于 IP 的路由，那么可以通过更多 SAProuter 中继段来使用此 SAProuter。或者，可以考虑设置另一个 SAProuter（基于一台具有公共 IP 且基于 {{site.data.keyword.cloud_notm}} 的服务器），然后通过因特网将其连接到 SAP OSS 系统。
  *	[SAP Solution Manager ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://support.sap.com/en/solution-manager.html){: new_window}。根据您的使用场景，对 SAP Solution Manager 的访问权在 SAP Solution Manager 与其受管系统之间存在不同的连接需求。这些场景要求了解所需的网络连接。  

## 外部存储器
{: #external_storage}

本地存储器为数据库部署提供最佳性能。除了本地存储器之外，还可能需要更多外部存储器来执行备份，否则 SAP 系统的数据库可能会超出内部磁盘的存储容量。另一个示例是根据项目需求，可能需要外部存储器；例如，要共享虚拟机 (VM) 的多个基于 ESX 的服务器。对于这些需求，可以如[存储器](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-storage#storage)中所述，订购块存储器或网络连接的存储器 (NAS)。由于额外的块存储器和 NAS 数据是通过与所有其他网络流量相同的物理适配器传输的，因此需要牢记影响。与认证基准中所测量的数字相当的性能数字可能仅仅是可实现的。

如果计划主要使用外部存储器而非本地存储器，那么建议为您的部署选择基于 10 Gb 的数据中心。例如，外部存储器同时用于备份和数据库，以及用于您计划在 SAP 系统上实现高负载的情况。如果以 90 MB/秒的 I/O 负载运行而使得 1 Gb 网络即将超负荷，也会使用外部存储器。

另一个建议是，如果数据库主要驻留在外部存储器上，至少使用 4 IOPS/GB。仅当数据库性能对于项目或备份而言不太重要时，才应使用速度较慢的存储器。

如果计划使用外部存储器作为 VMware ESX 的数据存储器，请遵循[与 VMware 系统配合使用的存储器](/docs/infrastructure/vmware?topic=VMware-storage-to-use-with-vmware-systems#storage-to-use-with-vmware-systems)中的决策准则，以确定适用于您用例的最佳存储器类型。

## VMware ESXi 服务器部署
{: #vmware_server}

{{site.data.keyword.cloud_notm}} 中基于 VMware ESXi 的部署不同于其他基于云的部署。{{site.data.keyword.cloud_notm}} 不向客户提供运行的 VM；您可以控制和配置环境以满足自己的需求。在订购 VMware ESX 服务器时，您收到的是已配置的服务器。以下链接提供有关其他存储器和运行的访客 VM 的信息。

  *	[与 VMware 系统配合使用的存储器](/docs/infrastructure/vmware?topic=VMware-storage-to-use-with-vmware-systems#storage-to-use-with-vmware-systems)提供有关如何在 ESX 环境中集成存储器的更多指示信息。
  * [安装 iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mounting-iscsi-vmware-esxi#mounting-iscsi-vmware-esxi) 描述将基于 iSCSI 的存储器与 ESX 集成的步骤。
  * [创建 VMware ESX 虚拟机](/docs/infrastructure/vmware?topic=VMware-creating-a-vmware-esx-virtual-machine#creating-a-vmware-esx-virtual-machine)指导您完成部署第一个 VM 的过程。

请记住，要在访客操作系统中部署基于 SAP NetWeaver 的软件，必须从 [SAP Note 2414097 ![外部链接图标](../../icons/launch-glyph.svg "")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 中提及的操作系统选择访客操作系统。
