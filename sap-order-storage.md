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

# 1. Ordering storage
{: #order_storage}

{{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}}, and Network Attached Storage (NAS) are ordered after you deploy your {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}.

## Ordering {{site.data.keyword.cloud_notm}} storage
{: #ibm_storage}

You can use the steps under [Provisioning and Managing {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted#GettingStarted) or [Provisioning and Managing {{site.data.keyword.filestorage_full_notm}}](/docs/infrastructure/FileStorage?topic=FileStorage-orderingConsole#orderingConsole) to order your backup and restore storage solution. You are guided through the process of deciding which storage type to use, how to order it, and how to deploy it to your server.

The *SAP NetWeaver Quick Reference Guides (for Microsoft Windows* or *for Red Hat Enterprise Linux*) take you through a complete server configuration and deployment, including {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}, and iSCSI configuration steps based on a sample deployment for Linux and Windows.

For VMware ESXi, the {{site.data.keyword.cloud_notm}} storage type can be used as data stores; in which case, it is mapped to ESXi as an iSCSI device. Follow the steps in [Mounting iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mounting-iscsi-vmware-esxi#mounting-iscsi-vmware-esxi) to map iSCSI devices to ESXi.

## Next Steps

  [2. Securing your environment](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. Installing your guest OS on the ESX hypervisor (optional)](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. Downloading and installing SAP software and applications](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
