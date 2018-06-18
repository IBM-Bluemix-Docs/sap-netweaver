---



copyright:
  years: 2017, 2018
lastupdated: "2018-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 常见问题：SAP on IBM Cloud 
{: #faqs}

## 在 {{site.data.keyword.cloud_notm}} 上运行 SAP NetWeaver 是否需要 Db2？

定期查看 [SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097)，另请参考 [SAP Product Availability Matrix](https://apps.support.sap.com/sap/support/pam)。请注意 SAP Note 中提供的操作系统，因为您的数据库需要不同的 service pack 集。

## 为什么选择了 {{site.data.keyword.Db2_on_Cloud_short}} 来认证 {{site.data.keyword.cloud_notm}}？

因为 {{site.data.keyword.Db2_on_Cloud_long_notm}} 是 {{site.data.keyword.IBM_notm}} 产品，{{site.data.keyword.cloud_notm}} 是选择用于认证的 {{site.data.keyword.IBM_notm}} 的一部分。

## 是否可以在不同数据中心之间拆分分布式 SAP 环境？

针对分布式 SAP 安装，最好将所有节点放在相同的数据中心和 VLAN 段中。如果与此不同，可能会产生等待时间和超时，这会导致 SAP 系统无响应。

## 是否可以实现 SAP 体系结构所定义的 SAP 高可用性？

唯一受支持的高可用性体系结构是应用程序服务器的扩展。当前，没有为任何硬件启用高可用性支持。

## 是否可直接从 {{site.data.keyword.cloud_notm}} 下载 SAP 分发软件？

目前，我们未提供与 [SAP Service Marketplace](https://websmp201.sap-ag.de/) 的直接链接。因此，您应该像今天针对本地部署执行的操作一样，下载分发 DVD。
