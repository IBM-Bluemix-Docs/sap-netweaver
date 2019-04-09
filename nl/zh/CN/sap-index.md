---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, SAP certified servers, SAP Certified, database,

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 入门教程
{: #getting-started}

{{site.data.keyword.IBM_notm}} 和 SAP 在包括硬件、软件、云、服务和融资在内的多个领域连续开展了 40 年的合作。目前双方正在协作以在 {{site.data.keyword.baremetal_long}} 上运行基于 SAP NetWeaver 的应用程序。该产品提供四个内存选项，即单插槽 (32 GB) 和双插槽（128 GB、256 GB 和 512 GB）。
这些内存选项在全球 60 多个 {{site.data.keyword.cloud_notm}} 数据中心都可用。
{: shortdesc}

此内容为您提供了用于在 {{site.data.keyword.cloud_notm}} 上供应和安装基础架构以支持基于 SAP NetWeaver 的 SAP 产品和预订的建议。它不能代替任何与 SAP NetWeaver 实施相关的文档。其目的是帮助您进行基础架构规划和供应，以便可以开始 SAP 安装。SAP 安装（包括数据库安装）在内部部署环境的各个安装之间并无差别。提供了建议和准则以帮助您在 {{site.data.keyword.cloud_notm}} 环境中操作 SAP 系统。

表 1 包含帮助您快速构建 {{site.data.keyword.cloud_notm}} 基础架构的步骤。
<table>
   <CAPTION>表 1. 快速入门步骤</CAPTION>
   <THEAD>
   <TR>
   <th>任务</th>
   <th>详细信息</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>1. 阅读与您的实施相关的 IBM Cloud 和 SAP 内容</td>
   <td>如果您的组织不熟悉 IBM Cloud，请在规划阶段之前阅读以下信息。<li><a href="https://ibm.com/cloud-computing/">什么是 IBM Cloud</a></li>
   <li><a href="https://ibm.com/cloud/get-started">IBM Cloud 入门</a></li>
   <li><a href="https://help.sap.com/nw75#section2">SAP NetWeaver 7.5 安装和升级信息</a>：下载安装指南</li>

   您还可能发现以下 SAP 文档很有用：
   <li><a href="https://www.youtube.com/watch?v=4wICiRTP8u0/">如何创建 SAP S 用户标识</a>。请注意，只有超级管理员或具有所需授权的 S 用户才可以创建 S 用户标识。</li>
   <li><a href="https://help.sap.com/netweaver">SAP NetWeaver 帮助</a></li>
   <li><a href="https://support.sap.com">SAP Support Portal 中的 SAP Note</a>；需要 SAP S 用户标识</li>
   </td>
   <tr>
   <td>2. 注册 IBM Cloud</td>
   <td>请参阅<a href="https://cloud.ibm.com/docs/account/adminpublic.html#signing-up-for-ibm-cloud">注册 IBM Cloud</a> 以获取有关如何设置 IBM Cloud 帐户的步骤。</td>
 <tr>
   <td>3. 访问 IBM Cloud Infrastructure 客户门户网站</td>
   <td><a href="https://control.softlayer.com">IBM Cloud Infrastructure 客户门户网站</a>是所有基础架构组件（计算、连接、存储器、网络和数据中心）的图形网关。需要 <a href="https://console.bluemix.net/docs/customer-portal/getting-started.html#getting-started">IBM 标识和密码</a>才能访问客户门户网站。</td>
   <tr>
   <td>4. 规划系统格局</td>
   <td>使用<a href="sap-netweaver?topic=sap-netweaver-planning-your-system-landscape#planning-your-system-landscape">规划系统格局</a>中的信息，设计 IBM Cloud 环境的架构、设置其大小并进行供应，以支持 SAP NetWeaver 工作负载。</td>  
 <tr>
   <td>5. 供应系统</td>
   <td>使用<a href="sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment">供应 SAP NetWeaver 环境</a>中的步骤和信息来设置 IBM Cloud Infrastructure。您还可以使用“快速参考指南”中的步骤。</td>
   <tr>
   <td>6. 安装 SAP NetWeaver</td>
   <td>在 IBM Cloud Infrastructure 上安装 SAP NetWeaver 时，就如同服务器是内部部署的一样进行安装。有关安装 SAP NetWeaver 的更多信息，请参阅<a href="sap-netweaver?topic=sap-netweaver-install_sap#install_sap">下载和安装 SAP 软件和应用程序</a>以获取更多信息。</td>
   </td>
   </tr>
   </TBODY>
   </table>
