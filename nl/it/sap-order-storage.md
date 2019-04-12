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

# 1. Ordinazione dell'archiviazione
{: #order_storage}

{{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}} e NAS (Network Attached Storage) vengono ordinati dopo che hai distribuito i tuoi {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}.

## Ordinazione dell'archiviazione {{site.data.keyword.cloud_notm}}
{: #ibm_storage}

Puoi utilizzare la procedura nel documento relativo a [provisioning e gestione di {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-getting-started#getting-started) o a quello relativo a [provisioning o gestione di {{site.data.keyword.filestorage_full_notm}}](/docs/infrastructure/FileStorage?topic=FileStorage-orderingConsole#orderingConsole) per ordinare la tua soluzione di archiviazione di backup e ripristino. Vieni guidato attraverso il processo per decidere il tipo di archiviazione da utilizzare e come ordinarlo e come distribuirlo al tuo server.

Le *guide di riferimento rapido SAP NetWeaver (per Microsoft Windows* o *per Red Hat Enterprise Linux*) ti presentano una configurazione e una distribuzione del server completi, compresi {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}} e la procedura di configurazione iSCSI basati su una distribuzione di esempio per Linux e Windows.

Per VMware ESXi, il tipo di archiviazione {{site.data.keyword.cloud_notm}} può essere utilizzato come archivi di dati; in tal caso, viene associato a ESXi come un dispositivo iSCSI. Attieniti alla procedura in [Mounting iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mount-iscsi-esxi#mount-iscsi-esxi) per associare i dispositivi iSCSI a ESXi.

## Passi successivi

  [2. Protezione del tuo ambiente](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. Installazione del tuo sistema operativo guest sull'hypervisor ESX (facoltativo)](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. Download e installazione di software e applicazioni SAP](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
