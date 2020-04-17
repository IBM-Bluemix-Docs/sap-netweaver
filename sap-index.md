---

copyright:
  years: 2017, 2020
lastupdated: "2020-04-17"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, SAP certified servers, SAP Certified, database,

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external: target="_blank" .external}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Getting started with SAP NetWeaver on IBM Cloud
{: #getting-started}

{{site.data.keyword.IBM}} and SAP continue a 40-year collaboration in multiple areas, including hardware, software, cloud, services, and finance. They are now collaborating to run SAP NetWeaver-based applications on {{site.data.keyword.baremetal_long}}. The offering features four memory options, single socket (32 GB) and dual sockets (128 GB, 256 GB, and 512 GB). These memory options are all available in the more than 60 {{site.data.keyword.cloud_notm}} data centers worldwide.
{: shortdesc}

This content provides you with recommendations for the provisioning and installation of the infrastructure to support SAP NetWeaver-based SAP products and subscription on {{site.data.keyword.cloud_notm}}. It does not replace to any SAP NetWeaver implementation-related documentation. Its purpose is to help you with infrastructure planning and provisioning so you can begin your SAP installation. The SAP installation (including database installation) does not vary from installations for on-premises environments. Recommendations and guidelines are provided to help you operate your SAP system in the {{site.data.keyword.cloud_notm}} environment.

## Before you begin
{#: before-you-begin-index}

Before you can begin your SAP NetWeaver on {{site.data.keyword.cloud}}, you need to get an IBMid and review relevant SAP and {{site.data.keyword}} documentation. For information on how to obtain and IBMid, see [Getting SAP and IBM Cloud credentials and create accounts](/docs/sap-netweaver?topic=sap-netweaver-get_sap_ibm_credentials). For a list of documentation to review, see [Reviewing any relevant SAP and {{site.data.keyword.cloud_notm}} documentation](/docs/sap-netweaver?topic=sap-netweaver-review_doc).

## Building your Infrastructure
{# :build-infrastructure}

Table 1 contains steps to help you get your {{site.data.keyword.cloud_notm}} infrastructure built quickly.

| Task | Details |
|--- | --- |
| Access the IBM Cloud console | [IBM Cloud console](https://cloud.ibm.com) is your graphical gateway to all your infrastructure components-compute, connectivity, storage, network, and data centers. You need an [IBMid and password](/docs/account?topic=account-signup#signing-up-for-ibm-cloud) to access the customer portal. |
| Plan your system landscape | Use the information in [Planning your system landscape](/docs/sap-netweaver?topic=sap-netweaver-planning-your-system-landscape) to architect, size, and provision your IBM Cloud environment to support your SAP NetWeaver workload. |
| Provision your system | Use the steps and information in [Provisioning you SAP NetWeaver environment (/docs/sap-netweaver?topic=sap-netweaver-provision_environment) to set up your IBM Cloud infrastructure. You can also use the steps in the [Quick Reference Guides](/docs/sap-netweaver?topic=sap-netweaver-review_doc). |
| Install SAP software | Install SAP software on your IBM Cloud infrastructure the same as if the servers were on-premises. For more information about installing SAP software, see [Downloading and installing SAP software and applications](/docs/sap-netweaver?topic=sap-netweaver-install_sap). |
{: caption="Table 1. Steps to get up and running quickly" caption-side="top"}
