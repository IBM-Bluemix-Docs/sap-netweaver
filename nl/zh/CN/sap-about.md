---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-18"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.baremetal_short}}, ABAP, application server, SAP Product Availability Matrix, PAM, SAP Certified, SAP Content Server, SAP liveCache

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:note: .note}
{:faq: .faq}


# 关于 IBM Cloud SAP-Certified Infrastructure
{: #about_ibmcloud_for_sap}

IBM 和 SAP 已在包括硬件、软件、云、服务和金融在内的多个领域开展合作、合伙和协作超过 45 年。第一次协作是在 1972 年进行的，随后又与使用 {{site.data.keyword.cloud}} 作为其基础架构即服务 (IaaS) 解决方案的数百个 SAP 客户开展合作。{{site.data.keyword.IBM_notm}} 持续优化其云基础架构产品，以支持 SAP NetWeaver 计算平台。

由于此关系以及其他 {{site.data.keyword.cloud_notm}} 功能，{{site.data.keyword.IBM_notm}} 被选为 SAP 业务关键型应用程序的云基础架构服务的首要战略提供商之一。通过高度可缩放、开放且高度安全的 {{site.data.keyword.cloud_notm}}，提供了对 SAP NetWeaver 系列产品的支持。利用这种合作伙伴关系，基于 SAP NetWeaver 的应用程序能够借助于全球范围内超过 60 个 {{site.data.keyword.IBM_notm}} 数据中心占领主要市场。

此产品以具有以下八种内存选项的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 为特色：
  * 单插槽 32 GB
  * 单插槽 64 GB
  * 双插槽 128 GB
  * 双插槽 256 GB
  * 双插槽 512 GB
  * 双插槽 192 GB
  * 双插槽 384 GB
  * 双插槽 768 GB

所有八个选项都针对 SAP NetWeaver 进行了认证，可以提供一个可缩放、高度安全、开放的全球企业云平台，从而快速部署 SAP 应用程序。

您可以将服务器用于生产、非生产或概念证明 (POC) 环境。所有 SAP NetWeaver Application Server 基于 ABAP 的产品和 SAP NetWeaver Application Server 基于 Java 的产品都在 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 上受支持。对于所有其他软件组件、非基于 SAP NetWeaver 的 SAP 产品或第三方产品，如果 IaaS 产品中支持这些产品，请联系 [SAP 支持 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://support.sap.com/home.html){: new_window}。

## {{site.data.keyword.cloud_notm}} for SAP NetWeaver 产品模型
{: #offer_model}

{{site.data.keyword.cloud_notm}} for SAP Application 产品非常适合通过 {{site.data.keyword.cloud_notm}} 网络在 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 上用于几乎所有支持 SAP NetWeaver 用例的场景。

该产品包含以下服务器、操作系统 (OS) 和数据库：
  * 八种大小的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 和每台服务器随附的软件。
      * 4 核，含 32 GB RAM
      * 4 核，含 64 GB RAM
      * 24 核，含 128 GB RAM
      * 24 核，含 256 GB RAM
      * 28 核，含 512 GB RAM
      * 36 核，含 192 GB RAM
      * 36 核，含 384 GB RAM
      * 36 核，含 768 GB RAM

  * 操作系统或管理程序
      * 服务器上的 VMware vSphere ESXi 6.0 或 6.5
      * Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X 操作系统 [SAP Business Warehouse (SAP BW) 在 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 上的生产环境中受支持]
      * SUSE Linux Enterprise Server（请参阅 [SAP Note 2414097 ![](../../icons/launch-glyph.svg "外部链接图标")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 以获取版本详细信息）
      * Microsoft Windows Server（请参阅 [SAP Note 2414097 ![](../../icons/launch-glyph.svg "外部链接图标")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 以获取版本详细信息）

  * 提供的数据库为
      * Microsoft SQL Server for Windows（请参阅 [SAP Note 2414097 ![](../../icons/launch-glyph.svg "外部链接图标")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 以获取版本详细信息）
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Linux（请参阅 [SAP Note 101809 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://launchpad.support.sap.com/#/notes/101809){: new_window}：支持的版本和修订包级别）
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Windows（请参阅 [SAP Note 101809-DB6 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://launchpad.support.sap.com/#/notes/101809){: new_window}：支持的版本和修订包级别）
      * SAP MaxDB（请参阅 [SAP Note 2414097 ![](../../icons/launch-glyph.svg "外部链接图标")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 以获取版本详细信息）
      * SAP ASE 16.0（请参阅 [SAP Note 2414097 ![](../../icons/launch-glyph.svg "外部链接图标")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 以获取详细信息）
      * SAP HANA

随 VMware ESXi 部署的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 可以运行列出的 RHEL 和 Windows 版本、引用的数据库以及基于 SAP NetWeaver 的软件产品。服务器可以运行其他操作系统或非基于 SAP NetWeaver 的产品，例如 SAP liveCache、SAP Content Server、SAP Business One on Microsft SQL 以及 SAP BusinessObjects，如
[SAP Note 2279688 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://launchpad.support.sap.com/#/notes/2279688){: new_window} 中所列示。

如果您在 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 上运行基于 SAP NetWeaver 的 SAP 产品，那么您还必须运行一个支持的操作系统和数据库。
{: note}

请参阅 [{{site.data.keyword.cloud_notm}} 上的 SAP HANA](/docs/infrastructure/sap-hana?topic=sap-hana-getting-started#getting-started) 以获取有关部署 SAP HANA 的信息。

请查看 [SAP Product Availability Matrix (PAM) ![外部链接图标](../../icons/launch-glyph.svg "")](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: new_window}，以获取 {{site.data.keyword.cloud_notm}} 的特定数据库、操作系统和 SAP NetWeaver 需求。要访问 SAP PAM，需要 SAP S 用户标识。

## {{site.data.keyword.cloud_notm}} 网络
{: #ibm_cloud_network}

{{site.data.keyword.cloud_notm}} 在全球超过 60 个 {{site.data.keyword.cloud_notm}} 数据中心和 28 个存在点 (PoP) 提供 2000 GB 以上的连接。{{site.data.keyword.cloud_notm}} 在其各个位置之间有 20 Gbps 网络连接。这些连接由领先的全球网络提供商提供，并包含与数十个可访问因特网的其他网络的多个公共对等链路。

此网络是无缝集成到行业第一个网中网拓扑的三个不同的冗余千兆位网络体系结构 - 公用、专用和数据中心到数据中心。这种设计能够为您的 IT 基础架构提供最强的可访问性、安全性和控制能力。请参阅
[IBM Cloud 网络 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud-computing/bluemix/our-network){: new_window} 以获取更多信息。
