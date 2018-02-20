---



copyright:
  years: 2018
lastupdated: "2018-01-25"


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

You can use the steps under [Provisioning and Managing {{site.data.keyword.blockstorageshort}}](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) or [Provisioning and Managing {{site.data.keyword.filestorage_full_notm}}](https://console.bluemix.net/docs/infrastructure/FileStorage/provisioning-file-storage.html#provisioning-and-managing-ibm-file-storage-for-ibm-cloud) to order your backup and restore storage solution. You are guided through the process of deciding which storage type to use, how to order it, and how to deploy it to your server.

The *SAP NetWeaver Quick Reference Guides (for Microsoft Windows* or *for Red Hat Enterprise Linux*) take you through a complete server configuration and deployment, including {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}, and iSCSI configuration steps based on a sample deployment for Linux and Windows.

For VMware ESXi, the {{site.data.keyword.cloud_notm}} storage type can be used as data stores; in which case, it is mapped to ESXi as an iSCSI device. Follow the steps in [Mounting iSCSI VMware ESXi](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi) to map iSCSI devices to ESXi.

## Ordering NAS
{: #order-nas}

NAS storage might be another valuable extension of the local storage of your server if you need storage for archived log files of your database or frequent online and offline backups. Visit [Ordering NAS/FTP Storage](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#ordering-nas-ftp-storage) to order and set up NAS. Also, reference [Mounting NAS Storage in Linux](https://console.bluemix.net/docs/infrastructure/network-attached-storage/mount-nas-storage-linux.html#mounting-nas-storage-in-linux) to see how to map network file storage (NFS) to your Linux server. [NAS storage can also be mapped to VMware ESXi as a datastore through NFS](https://console.bluemix.net/docs/infrastructure/network-attached-storage/connect-nas-storage-windows.html#connecting-to-nas-storage-in-windows).

## Next Steps

  [2. Securing your environment](/docs/infrastructure/sap-netweaver/sap-secure-environment.html)

  [3. Installing your guest OS on the ESX hypervisor (optional)](/docs/infrastructure/sap-netweaver/sap-installing-guest-operating-system-VMware-deployments.html)

  [4. Downloading and installing SAP software and applications](/docs/infrastructure/sap-netweaver/sap-installing-SAP-landscape.html)
  
  [5. Testing connectivity to your {{site.data.keyword.cloud_notm}} data center](/docs/infrastructure/sap-netweaver/sap-testing-connectivity.html)
