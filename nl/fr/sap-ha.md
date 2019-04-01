---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, high availability, highly available, HA, disaster recovery, DR, Microsft Windows Server Failover Clustering, WFSC, bring your own license, BYOL, single point of failure, SPOF, Link Aggregation Control Protocol, LACP, VLANs, SAP Certified, database, Linux Pacemaker

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# Prise en charge de la haute disponibilité IBM Cloud
{: #ha}

L'infrastructure IaaS (Infrastructure as a Service) {{site.data.keyword.cloud}} vous offre un environnement de calcul robuste avec un déploiement de système d'exploitation en option prenant en charge des solutions à haute disponibilité. La solution est basée sur la version de système d'exploitation prise en charge, décrite dans la [note SAP 2414097 ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}. La solution à haute disponibilité est limitée aux licences de système d'exploitation commandées livrées avec votre déploiement, ou aux licences tierces, telles que les licences BYOL. Prenez soin de discuter de la haute disponibilité avec le support {{site.data.keyword.cloud_notm}} avant de commencer votre déploiement. 

Les systèmes d'exploitation pris en charge et déployés par {{site.data.keyword.cloud_notm}} pour SAP sont les suivants :
* Linux [Red Hat Enterprise Linux (RHEL) ou SUSE Enterprise Linux Server (SLES)] prend en charge les solutions à haute disponibilité SAP NetWeaver et SAP HANA. L'environnement {{site.data.keyword.cloud_notm}} présente des restrictions mineures, présentées dans la rubrique [Présentation des configurations à haute disponibilité SAP NetWeaver](#overview-configs).
* Microsoft Windows prend uniquement en charge la solution à haute disponibilité SAP NetWeaver (en raison de restrictions liées à la base de données SAP HANA). 

## Présentation des configurations à haute disponibilité SAP NetWeaver
{: #overview-configs}

Il existe de nombreux documents fournissant une aide approfondie sur la planification et l'installation d'un environnement à haute disponibilité pour les services SAP. Les documents comprennent des informations sur le basculement, la réplication, l'extension et la reprise après incident. Des références à certains documents sont fournies le cas échéant. 

Tous les systèmes d'exploitation et toutes les distributions pris en charge par {{site.data.keyword.cloud_notm}} pour un déploiement SAP (Windows et Linux RHEL et SLES) sont livrés avec des logiciels à haute disponibilité et des extensions spécifiques. Les systèmes d'exploitation et les distributions pris en charge sont les suivants :

* Le blogue [New Failover Clustering Improvements in Windows Server 2012 and Its Benefits for SAP NetWeaver High Availability ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://blogs.sap.com/2013/10/16/new-failover-clustering-improvements-in-windows-server-2012-and-its-benefits-for-sap-netweaver-high-availability/){: new_window} fournit une description basée sur la fonction WFSC (Windows Server Failover Clustering) sur le système d'exploitation Windows avec SAP NetWeaver.

* Il existe deux références traitant du déploiement de SAP NetWeaver dans un environnement à haute disponibilité Linux avec Linux Pacemaker :
  * SUSE SAP NetWeaver High Availability Cluster 7.40 Setup Guide
  * Deploying Highly Available SAP NetWeaver-based Servers Using Red Hat Enterprise Linux HA add-on with Pacemaker

* [Building High Availability for SAP NetWeaver and SAP HANA on Linux ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://support.sap.com/content/dam/SAAP/SAP_Activate/AGS_70.pdf){: new_window} est un document dédié aux meilleures pratiques SAP qui fournit une description technique très détaillée qui cible surtout SAP HANA.

* [SAP NetWeaver High Availability and Business Continuity in Virtual Environments with VMware and Hyper-V on Microsoft Windows ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.sap.com/documents/2015/07/508b62bc-5b7c-0010-82c7-eda71af511fa.html){: new_window} traite de la virtualisation si vous prévoyez d'implémenter la haute disponibilité sur des serveurs virtualisés. 

Pour connaître d'autres produits à haute disponibilité certifiés par les partenaires SAP dans le cadre de scénarios de haute disponibilité, voir [High Availability Partner Information ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://wiki.scn.sap.com/wiki/display/SI/High+Availability+Partner+Information){: new_window}.
Pour les bases de données SAP non HANA, d'autres informations sur la configuration du basculement et de la reprise après incident dans un environnement à haute disponibilité sont disponibles dans la documentation de votre base de données. 

Notez que l'accès partagé au stockage NFS (Network File System)/CIFS (Common Internet File System) ou l'accès partagé au stockage LUNS (Logical Unique Number Storage) basé sur iSCSI, est généralement requis pour prendre en charge le basculement système. Le stockage local, combiné à une méthode réplication, est généralement requis pour prendre en charge la configuration de la reprise après incident. Comme pour les installations sur site, vérifiez les exigences en matière de performances et de latence du produit base de données lorsque vous planifiez votre déploiement. 

## Conseils supplémentaires
{: #extra-guide}

Les sections [Stockage basé sur quorum](#quorum) et [Remarques relatives au réseau](#network) fournissent des conseils utiles pour le déploiement. En dehors des remarques décrites dans ces sections, l'installation de SAP NetWeaver et de son système de base de données n'est pas différente des autres installations sur site. 

### Stockage basé sur quorum
{: #quorum}

En raison de restrictions de sécurité dans l'environnement {{site.data.keyword.cloud_notm}}, l'accès réseau aux unités de gestion à distance via l'interface IPMI (Intelligent Platform Management Interface) n'est pas disponible. Les environnements de cluster utilisent généralement des composants basés sur IPMI pour le "clôturage de noeuds de cluster" afin de toujours garantir un quorum. En l'absence d'unité IPMI, des unités de stockage partagé sont utilisées. Dans un environnement {{site.data.keyword.cloud_notm}}, les unités de stockage partagé sont implémentées en déployant un numéro d'unité logique iSCSI sur vos serveurs en tant que périphérique quorum. Par exemple, un témoin de partage de fichiers sur un cluster Microsoft et pour SDB (storage-based death) pour Stonith de Linux Pacemaker. 
* Cliquez [ici ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://linux-ha.org/wiki/Cluster_Concepts){: new_window} pour obtenir plus d'informations sur les concepts de cluster à haute disponibilité Linux. 
* Cliquez [ici ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://docs.microsoft.com/en-us/windows-server/failover-clustering/manage-cluster-quorum){: new_window} pour en savoir plus sur la configuration et la gestion de serveurs quorum pour Windows Server 2012 et Windows Server 2012 R2.

Le stockage {{site.data.keyword.cloud_notm}} comporte des fonctions haute disponibilité intégrées, par conséquent, un numéro d'unité logique iSCSI partagé n'introduit pas de point de défaillance unique car la présentation de votre réseau est redondante. Toutefois, les spécificités de votre cluster peuvent nécessiter plusieurs périphériques quorum. 

### Remarques relatives au réseau
{: #network}

Une installation basée sur {{site.data.keyword.cloud_notm}} est livrée avec l'une des configurations réseau suivantes :
* Réseau privé
* Réseau public
* Réseau public et réseau privé
* Deux réseaux privés (sur demande)

Comme les installations sur site, des adaptateurs de réseau supplémentaires peuvent être commandés selon les restrictions physiques du matériel. La restriction est la même pour les installations sur site. Commander des adaptateurs de réseau redondants durant les déploiements de matériel permet d'empêcher la création d'un point de défaillance unique dans votre topologie de réseau. Les adaptateurs redondants sont configurés dans une configuration de basculement avec le protocole LACP (Link Aggregation Control Protocol). Pour Linux, la configuration utilise des interfaces de liaison, et des adaptateurs de groupage sont utilisés pour Microsoft Windows. L'infrastructure de basculement {{site.data.keyword.cloud_notm}} à laquelle ces adaptateurs sont connectés est redondante, par conséquent, de nouveaux points de défaillance uniques sont introduits. L'infrastructure redondante peut être utilisée par les VLAN commandés. 

Selon les exigences de réseau, tels que des scénarios de réplication dans une configuration de reprise après incident, vous devez vérifier l'emplacement des unités connectées et les nouvelles exigences réseau propres au produit concerné. Dans certains cas, la réplication basée sur le stockage d'image instantanée {{site.data.keyword.cloud_notm}} peut répondre à vos exigences. Contactez le support {{site.data.keyword.cloud_notm}} afin d'identifier la solution la mieux adaptée à vos besoins de processus métier. 
