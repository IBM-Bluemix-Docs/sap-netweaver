---

copyright:
  years: 2018, 2019
lastupdated: "2019-09-23"

keywords: SAP NetWeaver, {{site.data.keyword.blockstorageshort}}, {{site.data.keyword.filestorage_full_notm}}, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.baremetal_short}}

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external: target="_blank" .external}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. Ordering storage
{: #order_storage}

{{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}}, and Network Attached Storage (NAS) are ordered after you deploy your {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}.
{:shortdesc}

## Ordering {{site.data.keyword.cloud_notm}} storage
{: #ibm_storage}

{{site.data.keyword.cloud_notm}} storage LUNS ({{site.data.keyword.blockstorageshort}}) and volumes ({{site.data.keyword.filestorage_full_notm}}) can be provisioned with two options - Endurance and Performance. Endurance tiers feature pre-defined performance levels and other features, such as [snapshot](/docs/infrastructure/BlockStorage?topic=BlockStorage-snapshots) and replication. A custom Performance environment is built with allocated input/output/operations per second (IOPS) between 100 and 1,000.

[Getting started with Block Storage](/docs/infrastructure/BlockStorage?topic=BlockStorage-getting-started) and [Getting started with File Storage](/docs/infrastructure/FileStorage?topic=FileStorage-getting-started) provides you with provisioning considerations, how to submit your order (if you didn't order when you originally provisioned your server), and connecting to and managing your new storage.

Use the following links to learn more about {{site.data.keyword.blockstorageshort}} and {{site.data.keyword.filestorage_full_notm}}:
* [Learn about {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-About)
* [Learn about {{site.data.keyword.filestorage_full_notm}}](/docs/infrastructure/FileStorage?topic=FileStorage-about)

Provisioning steps can be found under
* [Ordering Block Storage through the Console](/docs/infrastructure/BlockStorage?topic=BlockStorage-orderingthroughConsole)
* [Ordering File Storage through the Console](/docs/infrastructure/FileStorage?topic-FileStorage-orderConsole)

The *SAP NetWeaver Quick Reference Guides (for Microsoft Windows* or *for Red Hat Enterprise Linux*) take you through a complete server configuration and deployment, including ordering {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}} and iSCSI configuration steps based on a sample deployment for Linux and Windows.

For VMware ESXi, the {{site.data.keyword.cloud_notm}} storage type can be used as data stores; in which case, it is mapped to ESXi as an iSCSI device. Follow the steps in [Mounting iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mount-iscsi-esxi#mount-iscsi-esxi) to map iSCSI devices to ESXi.

## Next Steps
{: #order-storage-next-steps}

  [2. Securing your environment](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. Installing your guest OS on the ESX hypervisor (optional)](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. Downloading and installing SAP software and applications](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
