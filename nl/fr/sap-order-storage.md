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

# 1. Commande de stockage
{: #order_storage}

Vous commandez {{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}} et Network Attached Storage (NAS) après le déploiement de vos serveurs Bare Metal {{site.data.keyword.cloud_notm}}. 

## Commande de stockage {{site.data.keyword.cloud_notm}}
{: #ibm_storage}

Vous pouvez suivre les étapes décrites dans [Provisioning and Managing {{site.data.keyword.blockstorageshort}}](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) ou [Provisioning and Managing {{site.data.keyword.filestorage_full_notm}}](https://console.bluemix.net/docs/infrastructure/FileStorage/provisioning-file-storage.html#provisioning-and-managing-ibm-file-storage-for-ibm-cloud) pour commander votre solution de stockage pour la sauvegarde et la restauration. Vous serez guidé pour choisir le type de stockage à utiliser, savoir comment le commander et savoir comment le déployer sur votre serveur.

Les manuels *SAP NetWeaver Quick Reference Guides (for Microsoft Windows* ou *for Red Hat Enterprise Linux*) décrivent la procédure complète de configuration et de déploiement d'un serveur, y compris du périphérique {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}, et indiquent les étapes de configuration iSCSI basées sur un exemple de déploiement sous Linux et Windows.

Pour VMware ESXi, le type de périphérique de stockage {{site.data.keyword.cloud_notm}} peut être utilisé comme magasins de données. Dans ce cas, il est mappé à ESXi en tant que périphérique iSCSI. Suivez les étapes décrites dans [Mounting iSCSI VMware ESXi](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi) pour mapper les périphériques iSCSI à ESXi.

## Commande de stockage NAS
{: #order-nas}

Le stockage NAS peut constituer une autre extension intéressante du stockage local de votre serveur si vous avez besoin de stockage pour les fichiers journaux archivés de votre base de données ou des sauvegardes en ligne et hors ligne fréquentes. Visitez la page [Ordering NAS/FTP Storage](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#ordering-nas-ftp-storage) pour commander et configurer un stockage NAS. De plus, consultez la rubrique [Mounting NAS Storage in Linux](https://console.bluemix.net/docs/infrastructure/network-attached-storage/mount-nas-storage-linux.html#mounting-nas-storage-in-linux) pour apprendre à mapper le stockage de fichiers réseau (NFS) à votre serveur Linux. [Le stockage NAS peut également être mappé à VMware ESXi en tant que magasin de données via NFS](https://console.bluemix.net/docs/infrastructure/network-attached-storage/connect-nas-storage-windows.html#connecting-to-nas-storage-in-windows).

## Etapes suivantes

  [2. Sécurisation de votre environnement](/docs/infrastructure/sap-netweaver/sap-secure-environment.html)

  [3. Installation de votre système d'exploitation invité sur l'hyperviseur ESX (facultatif) ](/docs/infrastructure/sap-netweaver/sap-installing-guest-operating-system-VMware-deployments.html)

  [4. Téléchargement et installation du logiciel et des applications SAP](/docs/infrastructure/sap-netweaver/sap-installing-SAP-landscape.html)
  
  
