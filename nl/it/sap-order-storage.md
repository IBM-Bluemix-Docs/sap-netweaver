---



copyright:
  years: 2018
lastupdated: "2018-06-28"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. Ordinazione dell'archiviazione
{: #order_storage}

{{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}} e NAS (Network Attached Storage) vengono ordinati dopo che hai distribuito i tuoi {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}. 

## Ordinazione dell'archiviazione {{site.data.keyword.cloud_notm}}
{: #ibm_storage}

Puoi utilizzare la procedura nel documento relativo a [provisioning e gestione di {{site.data.keyword.blockstorageshort}}](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) o a quello relativo a [provisioning o gestione di {{site.data.keyword.filestorage_full_notm}}](https://console.bluemix.net/docs/infrastructure/FileStorage/provisioning-file-storage.html#provisioning-and-managing-ibm-file-storage-for-ibm-cloud) per ordinare la tua soluzione di archiviazione di backup e ripristino. Vieni guidato attraverso il processo per decidere il tipo di archiviazione da utilizzare e come ordinarlo e come distribuirlo al tuo server.

Le *guide di riferimento rapido SAP NetWeaver (per Microsoft Windows* o *per Red Hat Enterprise Linux*) ti presentano una configurazione e una distribuzione del server completi, compresi {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}} e la procedura di configurazione iSCSI basati su una distribuzione di esempio per Linux e Windows.

Per VMware ESXi, il tipo di archiviazione {{site.data.keyword.cloud_notm}} può essere utilizzato come archivi di dati; in tal caso, viene associato a ESXi come un dispositivo iSCSI. Attieniti alla procedura in [Mounting iSCSI VMware ESXi](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi) per associare i dispositivi iSCSI a ESXi.

## Ordinazione di NAS
{: #order-nas}

L'archiviazione NAS può essere un'altra preziosa estensione dell'archiviazione locale del tuo server se ti occorre dell'archiviazione per i file di log archiviati del tuo database oppure dei frequenti backup online e offline. Visita [Ordering NAS/FTP Storage](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#ordering-nas-ftp-storage) per ordinare e configurare NAS. Fai inoltre riferimento a [Mounting NAS Storage in Linux](https://console.bluemix.net/docs/infrastructure/network-attached-storage/mount-nas-storage-linux.html#mounting-nas-storage-in-linux) per informazioni su come associare NFS (network file storage) al tuo server Linux. [L'archiviazione NAS può essere associata a VMware ESXi come un archivio dati tramite NFS](https://console.bluemix.net/docs/infrastructure/network-attached-storage/connect-nas-storage-windows.html#connecting-to-nas-storage-in-windows).

## Passi successivi

  [2. Protezione del tuo ambiente](/docs/infrastructure/sap-netweaver/sap-secure-environment.html)

  [3. Installazione del tuo sistema operativo guest sull'hypervisor ESX (facoltativo)](/docs/infrastructure/sap-netweaver/sap-installing-guest-operating-system-VMware-deployments.html)

  [4. Download e installazione di software e applicazioni SAP](/docs/infrastructure/sap-netweaver/sap-installing-SAP-landscape.html)
  
  
