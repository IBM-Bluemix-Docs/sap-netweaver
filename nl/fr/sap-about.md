---



copyright:
  years: 2017, 2018
lastupdated: "2018-05-30"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# A propos de l'infrastructure certifiée SAP d'IBM Cloud
{: #about_ibmcloud_for_sap}

IBM et SAP se sont associés pour travailler en équipe et collaborer dans des domaines incluant le matériel, les logiciels, le cloud, les services et le financement depuis plus de 45 ans. La première collaboration a eu lieu en 1972 et s'est développée, avec des centaines de clients SAP utilisant {{site.data.keyword.cloud}} comme solution IaaS (infrastructure sous forme de services). {{site.data.keyword.IBM_notm}} a continué d'optimiser ses produits d'infrastructure de Cloud pour inclure une prise en charge de la plateforme SAP NetWeaver. 

C'est en raison de cette relation et pour d'autres fonctionnalités d'{{site.data.keyword.cloud_notm}} qu'{{site.data.keyword.IBM_notm}} a été sélectionnée par SAP comme l'un de ses fournisseurs stratégiques principaux de services d'infrastructure de cloud pour ses applications essentielles aux entreprises. La prise en charge de la suite de produits SAP NetWeaver est disponible via l'infrastructure ouverte, sécurisée et hautement évolutive {{site.data.keyword.cloud_notm}}. Les applications SAP NetWeaver peuvent ainsi être déployées sur les principaux marchés dans plus de 60 centres de données {{site.data.keyword.IBM_notm}} implantés dans le monde entier.

L'offre inclut des serveurs Bare Metal {{site.data.keyword.cloud_notm}} avec huit possibilités de mémoire :
  * Simple socket 32 Go
  * Simple socket 64 Go
  * Double socket 128 Go
  * Double socket 256 Go
  * Double socket 512 Go
  * Double socket 192 Go
  * Double socket 384 Go
  * Double socket 768 Go

Les huit options ci-dessus sont certifiées SAP NetWeaver et offrent une plateforme cloud d'entreprise évolutive, sécurisée, ouverte et globale pour un déploiement rapide d'applications SAP.

Vous pouvez utiliser vos serveurs pour des environnements de production, hors production ou de démonstration de faisabilité. Tous les produits SAP NetWeaver Application Server ABAP et Java sont pris en charge sur les serveurs Bare Metal {{site.data.keyword.cloud_notm}}. Pour tous les autres composants logiciels, produits non-SAP de SAP NetWeaver ou produits tiers, contactez le [support SAP](https://support.sap.com/home.html) si les produits sont pris en charge dans le cadre des offres IaaS.

## Modèle d'offre {{site.data.keyword.cloud_notm}} pour SAP NetWeaver
{: #offer_model}

L'offre {{site.data.keyword.cloud_notm}} pour les applications SAP s'adapte à pratiquement tous les scénarios SAP NetWeaver sur les serveurs Bare Metal {{site.data.keyword.cloud_notm}} via le réseau {{site.data.keyword.cloud_notm}}.

L'offre se compose des serveurs, systèmes d'exploitation et bases de données ci-dessous :
  * Les serveurs Bare Metal {{site.data.keyword.cloud_notm}} disponibles dans huit tailles différentes et équipés du logiciel correspondant.
      * 4 coeurs avec 32 Go de RAM
      * 4 coeurs avec 64 Go de RAM
      * 24 coeurs avec 128 Go de RAM
      * 24 coeurs avec 256 Go de RAM
      * 28 coeurs avec 512 Go de RAM
      * 36 coeurs avec 192 Go de RAM
      * 36 coeurs avec 384 Go de RAM
      * 36 coeurs avec 768 Go de RAM
      
  * Les systèmes d'exploitation ou hyperviseurs
      * VMware vSphere ESXi 6.0 ou 6.5 sur votre serveur
      * Red Hat Enterprise Linux (RHEL) pour SAP Business Applications 6.X OS [SAP Business Warehouse (SAP BW) est pris en charge en production sur les serveurs Bare Metal {{site.data.keyword.cloud_notm}}]
      * Microsoft Windows Server (voir la [note SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) pour en savoir plus sur les versions)
      
  * Les bases de données
      * Microsoft SQL Server pour Windows (voir la [note SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) pour en savoir plus sur les versions)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} pour Linux (voir la [note SAP 101809](https://launchpad.support.sap.com/#/notes/101809) : Versions prises en charge et niveaux de groupes de correctifs)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} pour Windows (voir la [note SAP 101809-DB6](https://launchpad.support.sap.com/#/notes/101809) : Versions prises en charge et niveaux de groupes de correctifs)
      
Les serveurs Bare Metal {{site.data.keyword.cloud_notm}} qui sont déployés avec VMware ESXi peuvent exécuter les versions RHEL et Windows, les bases de données référencées et les produits logiciels basés sur SAP NetWeaver. Les serveurs ne peuvent pas exécuter d'autres systèmes d'exploitation ni produits SAP basés sur NetWeaver non-SAP.

Voir [SAP HANA sur {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/infrastructure/sap-hana/hana-index.html#getting-started) pour obtenir des informations sur le déploiement de SAP HANA. Les futures versions de l'offre {{site.data.keyword.cloud_notm}} pour applications SAP seront compatibles avec d'autres bases de données, la haute disponibilité et la reprise après incident.

Consultez la page [SAP Product Availability Matrix (PAM)](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630) pour en savoir plus sur les exigences liées aux bases de données spécifiques, systèmes d'exploitation et SAP NetWeaver sous {{site.data.keyword.cloud_notm}}. Vous devez disposer d'un identifiant SAP S-user pour pouvoir accéder à SAP PAM.

## Réseau {{site.data.keyword.cloud_notm}}
{: #ibm_cloud_network}

Le réseau {{site.data.keyword.cloud_notm}} fournit plus de 2 000 Gbits/s de connectivité avec une présence mondiale intégrant plus de 60 centres de données {{site.data.keyword.cloud_notm}} et 28 points de présence (POP). {{site.data.keyword.cloud_notm}} dispose de connexions réseau de 20 gigabits par seconde dans ses emplacements. Ces connexions sont mises à disposition par les fournisseurs de réseau internationaux leaders sur le marché et incluent plusieurs liaisons d'appairage public à des douzaines de réseau d'accès à Internet supplémentaires.

Le réseau est constitué de trois architectures de réseau en gigabits distinctes et redondantes : une architecture publique, une architecture privée et une architecture centre de données à centre de données. Celles-ci sont intégrés de façon transparente à la première topologie de type "réseau dans un réseau" de l'industrie. Cette conception optimise l'accessibilité, la sécurité et le contrôle de votre infrastructure informatique. Pour plus d'informations, voir [The IBM Cloud network](https://www.ibm.com/cloud-computing/bluemix/our-network).
