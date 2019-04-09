---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, RDBMS, SAP Application Performance Standards, SAPS, SAP Certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 5. 确定配置
{: #determine_configuration}

对于 SAP NetWeaver 系统，提供了两个部署选项：
  * 中央系统，单主机安装（双层）
  * 分布式系统，多主机安装（三层）

这些选项会影响服务器选项。您可能希望将工作负载分布到不同服务器，或者为简单起见，将工作负载保留在一台服务器上。请参阅[设置基础架构](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-set_up_infrastructure#set_up_infrastructure)以获取有关如何部署服务器的逐步指导。

## 存储器配置
{: #storage_config}

表 1 是样本存储器配置，用于 [SAPS](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server) 为 50,000 的 256 GB 服务器，针对具有 SAP 的中央系统，大小为 1.5 TB 且 IOPS 为 6,000，同时使用带有外部 [{{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted#GettingStarted) 或 [{{site.data.keyword.cloud_notm}} {{site.data.keyword.filestorage_short}}](/docs/infrastructure/FileStorage?topic=FileStorage-GettingStarted#GettingStarted) 的 {{site.data.keyword.Db2_on_Cloud_long}} 数据库 (4 IOPS/GB)。IOPS 的计算方法为

  * 6,000 IOPS/1,500 GB = 4 IOPS/GB（外部存储器所需）。假定将 3,000 GB 用于备份，速度为 2 IOPS/GB（中等性能）。

表 1. 基于 IOPS 计算的样本存储器布局

|文件系统 |卷数|存储器类型|IOPS/GB |GB |IOPS 数|
| --- | --- | --- | --- | --- | --- |
| `/` |1 |内部|不适用|150 GB |不适用|
| `/boot` |1 |内部|不适用|0.25 GB |不适用|
| `swap` |1 |内部|不适用|256 GB |不适用|
| `/db2`（包括日志）|1 |内部|不适用|250 GB |不适用|
| `sapdata` |1 |外部|4 IOPS/GB |1,500 GB |6,000 IOPS |
| `backup/log and backup` |1 |外部|2 IOPS/GB |3,000 GB |6,000 IOPS |

## 高可用性配置
{: #ha_config}

{{site.data.keyword.cloud_notm}} 环境不支持任何预先配置的高可用性 (HA) 场景。但是，您可以根据所选操作系统的 HA 扩展来配置 HA 场景。通过将必需的硬件和软件组件添加到您的格局来添加 HA 扩展。如果需要更多软件许可证和/或访问不同软件存储库，请联系 [{{site.data.keyword.cloud_notm}} 支持](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) 以帮助您设置任何更多需求。

此信息不仅适用于 SAP NetWeaver 的 HA 软件，还适用于您选择的关系数据库管理系统 (RDBMS) 的 HA 软件。这包含了 RDBMS 的高可用性和灾难恢复机制，例如，复制。设置过程与内部部署环境中的任何设置过程相同，需要执行相同的硬件和软件配置步骤。

## 后续步骤

现在，您可以开始供应 {{site.data.keyword.baremetal_short}}。请参阅[供应 SAP NetWeaver 环境](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment)，以了解后续步骤。
