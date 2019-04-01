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

# 1. Commande de stockage
{: #order_storage}

Vous commandez {{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}} et Network Attached Storage (NAS) après le déploiement de vos serveurs Bare Metal {{site.data.keyword.cloud_notm}}.

## Commande de stockage {{site.data.keyword.cloud_notm}}
{: #ibm_storage}

Vous pouvez suivre les étapes décrites dans [Provisioning and Managing {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted#GettingStarted) ou [Provisioning and Managing {{site.data.keyword.filestorage_full_notm}}](/docs/infrastructure/FileStorage?topic=FileStorage-orderingConsole#orderingConsole) pour commander votre solution de stockage pour la sauvegarde et la restauration. Vous serez guidé pour choisir le type de stockage à utiliser, savoir comment le commander et savoir comment le déployer sur votre serveur.

Les manuels *SAP NetWeaver Quick Reference Guides (for Microsoft Windows* ou *for Red Hat Enterprise Linux*) décrivent la procédure complète de configuration et de déploiement d'un serveur, y compris du périphérique {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}, et indiquent les étapes de configuration iSCSI basées sur un exemple de déploiement sous Linux et Windows.

Pour VMware ESXi, le type de périphérique de stockage {{site.data.keyword.cloud_notm}} peut être utilisé comme magasins de données. Dans ce cas, il est mappé à ESXi en tant que périphérique iSCSI. Suivez les étapes décrites dans [Mounting iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mounting-iscsi-vmware-esxi#mounting-iscsi-vmware-esxi) pour mapper les périphériques iSCSI à ESXi.

## Etapes suivantes

  [2. Sécurisation de votre environnement](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. Installation de votre système d'exploitation invité sur l'hyperviseur ESX (facultatif)](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. Téléchargement et installation des logiciels et des applications SAP](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
