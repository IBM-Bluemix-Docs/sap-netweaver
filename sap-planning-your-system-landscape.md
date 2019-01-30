---



copyright:
  years: 2017, 2018
lastupdated: "2019-01-30"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Planning your system landscape
{: #planning-your-system-landscape}

An SAP *landscape* is a group of two or more SAP *systems* that usually include development, quality and test, and production. One SAP system consists of one or more *SAP instances*, which are a group of processes that are started and stopped at the same time. For more information on SAP landscapes, see [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://lenovopress.com/redp5073.pdf){: new_window}.
{: shortdesc}

There are several possible landscape configurations, such as server (size)/storage (size), for all SAP solutions in the market. These solutions include SAP NetWeaver-based products, such as [SAP Business Suite ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://open.sap.com/courses/suitehana1){: new_window}, SAP Business Warehouse, and all specific SAP add-ons, which the servers in the {{site.data.keyword.cloud}} SAP-Certified Infrastructure support. More solutions to keep in mind are any non-SAP NetWeaver-based SAP solutions and any third-party software that might integrate with SAP. Contact [SAP Support ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://support.sap.com/en/index.html){: new_window} if you’re planning to deploy non-SAP NetWeaver-based or third-party software in your {{site.data.keyword.cloud}} IaaS landscape.

You want to be as detailed as possible when you determine the size of your server based on the applications you plan to run, potential growth, and performance. Additionally, keep in mind your storage and memory requirements for your applications. SAP systems in a landscape have specific requirements for connectivity, either among each other or to external systems. For more information, see [Items to consider when planning your SAP landscape](/docs/infrastructure/sap-netweaver/sap-considerations.html).

Table 1 contains the steps within the planning process. Use it to help build your target SAP landscape.

Table 1. Planning process overview

| Step | Details |
| --- | --- |
| 1 | [Get SAP and {{site.data.keyword.cloud_notm}} credentials and create accounts](/docs/infrastructure/sap-netweaver/sap-get-credentials.html) |
| 2 | [Review any relevant SAP and {{site.data.keyword.cloud_notm}} documentation](/docs/infrastructure/sap-netweaver/sap-review-doc.html) |
| 3 | [Determine your SAP NetWeaver applications](/docs/infrastructure/sap-netweaver/sap-determine-apps.html) |
| 4 | [Size the server](/docs/infrastructure/sap-netweaver/sap-size-server.html) |
| 5 | [Determine your configuration](/docs/infrastructure/sap-netweaver/sap-determine-configuration.html) |

## Next Steps

Select the appropriate step in Table 1 to begin planning your SAP landscape.
