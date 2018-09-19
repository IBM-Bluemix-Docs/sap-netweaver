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

# SAP NetWeaver on IBM Cloud 概述
“基础架构即服务器”(IaaS) 环境由很多组件组成：数据中心、计算、连接、存储器和网络。 

## 数据中心

通过北美洲、南美洲、欧洲、亚洲和澳大利亚的数据中心，可以根据需要随时随地供应云资源。每个数据中心都连接到 {{site.data.keyword.cloud_notm}} 全球专用网络，使数据在全球任何位置的传输速度更快，效率更高。

请参阅[数据中心](https://www.ibm.com/cloud-computing/bluemix/data-centers){: new_window}，以获取有关 {{site.data.keyword.cloud_notm}} 数据中心和存在点 (PoP) 的更多信息。

## 裸机服务器

{{site.data.keyword.baremetal_long}} 是具有有限定制功能的物理服务器。这些服务器专供您或您的客户使用，不会与其他 {{site.data.keyword.cloud_notm}} 客户共享任何部分（包括服务器资源）。这些服务器由您或您的客户管理，并且在供应时不带管理程序。

由于裸机服务器上的定制有限，因此可将供应时间缩短为 1 到 4 小时。当您力争先于竞争对手将应用程序推向市场时，快速供应会很有帮助。

由于 SAP 认证的服务器具有预先配置的 RAM 量和 CPU 数量，因此为您提供了一系列 RAM 和 CPU 组合。部署服务器之后，*无法*在订购过程中或通过支持凭单更改组合。

如果项目需要虚拟化层，那么 SAP NetWeaver 产品包含订购随 VMware ESXi 部署的 {{site.data.keyword.baremetal_short}} 的选项。您对 ESX 实例具有完全控制权，因为它部署在您的数据中心内。系统已完全配置了联网相关信息（由您决定是否进行诸如存储器之类的任何进一步配置）。强烈建议您配备了解 ESX 管理的人员，以成功启动项目。

请参阅[关于裸机服务器](https://console.bluemix.net/docs/bare-metal/about.html#about-bare-metal-servers)，以获取有关裸机服务器的更多信息。 

## 操作系统

需要参阅 [SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097){: new window}，以获取用于部署基于 SAP NetWeaver 的系统的访客操作系统 (OS) 列表。要访问 SAP Note，需要 SAP S 用户标识。访客操作系统的许可需要您处理。

## 网络连接

在设置 {{site.data.keyword.cloud_notm}} 帐户时，将自动授权到 {{site.data.keyword.cloud_notm}} Virtual Cloud Network 的虚拟专用网 (VPN) 连接。缺省情况下，服务器具有公共和专用 IP 地址。如果希望服务器为专用服务器，那么可在供应服务器后关闭公共接口，也可以将该服务器作为专用服务器进行订购。请参阅[虚拟专用网入门](https://console.bluemix.net/docs/infrastructure/iaas-vpn/getting-started.html#getting-started-with-virtual-private-networking-vpn-)，以获取有关 {{site.data.keyword.cloud_notm}} VPN 的更多信息。

## 存储器
{: #storage}

本地存储器随 {{site.data.keyword.baremetal_short}} 一起提供，它使用 {{site.data.keyword.cloud_notm}} 专用网络虚拟 LAN (VLAN) 来帮助提供企业级安全性，而不阻碍管理员访问。这非常适合 I/O 需求较高的存储密集型应用程序（例如，操作系统、数据库和应用程序软件）。SAP NetWeaver 服务器磁盘空间取决于服务器的配置方式。如果服务器上的本地存储器不足以用于工作负载，请联系 [{{site.data.keyword.cloud_notm}} 支持](https://console.bluemix.net/docs/support/index.html#getting-customer-support)以了解扩展选项。

提供了适用于 {{site.data.keyword.cloud_notm}} 的两种类型的存储器，即块存储器和文件存储器，可选择用于为 SAP NetWeaver 执行备份和复原。这两种类型都使用每秒输入/输出操作数 (IOPS)，这些操作数用于确定存储需求。IOPS 基于 16 KB 块大小（50/50 读/写混合）进行度量。要在卷上实现最大 IOPS，需要有足够的网络资源。其他注意事项包括专用网络在存储器和主机端之外的使用量，以及特定于应用程序的调整（例如，IP 堆栈和队列深度）。请参阅 [Block Storage 入门](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage)和 [File Storage 入门](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage)，以获取有关存储器层和性能的更多信息。

如果您希望寻求快速、经济高效的设备备份解决方案，{{site.data.keyword.cloud_notm}} 还提供了网络连接的存储器 (NAS)。NAS 兼容
  * Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X 操作系统
  * 具有 Parallels Plesk Panel 和 cPanel@WHM 的文件传输协议 (FTP)
  * 通过使用通用因特网文件系统 (CIFS) 协议的标准 Windows 过程实现功能的 Microsoft Windows Server
  
NAS 和 FTP 存储器按月计费，并且提供各种存储器大小。您可以主要通过以下方式与 NAS 和 FTP 存储器进行交互：通过操作系统在命令行或终端中，或者在 {{site.data.keyword.cloud_notm}} 基础架构客户门户网站中的面板上通过点击式交互。

可以在 [NAS 入门](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#getting-started-with-nas)下找到有关 {{site.data.keyword.cloud_notm}} 环境中 NAS 的更多信息。

## 部署和管理

创建 {{site.data.keyword.cloud_notm}} 客户帐户后，通过 {{site.data.keyword.cloud_notm}} 基础架构客户门户网站或 API 部署 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}。可通过客户门户网站、API 或命令行界面 (CLI) 来管理服务器。可以在[有关裸机服务器](https://console.bluemix.net/docs/bare-metal/about.html#about-bare-metal-servers)下找到更多信息。

## 支持

[{{site.data.keyword.cloud_notm}} 客户支持](https://console.bluemix.net/docs/support/index.html#getting-customer-support)处理在使用各种渠道（包括交谈、电话和基于凭单的支持）期间可能出现的任何支持疑问和问题。客户支持为所有 {{site.data.keyword.cloud_notm}} 客户免费提供，涵盖了每天开具的大多数凭单。请参阅[获取客户支持](https://console.bluemix.net./docs/support/index.html#getting-customer-support)，以了解更多信息。
