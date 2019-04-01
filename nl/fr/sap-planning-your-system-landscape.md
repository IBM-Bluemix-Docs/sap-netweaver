---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, SAP landscape, SAP Business Suite, SAP Business Warehouse, SAP BW

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: .faq}

# Planification du paysage de votre système
{: #planning-your-system-landscape}

Un *paysage* SAP est un groupe de deux *systèmes* SAP ou plus, qui incluent habituellement le développement, la qualité et le test, et la production. Un système SAP se compose d'une ou de plusieurs *instances SAP*, qui constituent des groupes de processus démarrés et arrêtés simultanément. Pour plus d'informations sur les paysages SAP, voir [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://lenovopress.com/redp5073.pdf){: new_window}.
{: shortdesc}

Vous pouvez configurer plusieurs aspects du paysage, par exemple la taille du serveur ou la taille du stockage, pour toutes les solutions SAP sur le marché. Ces solutions incluent des produits reposant sur SAP NetWeaver, tels que [SAP Business Suite ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://open.sap.com/courses/suitehana1){: new_window}, SAP Business Warehouse, et tous les modules complémentaires SAP spécifiques, que les serveurs de l'offre d'infrastructure certifiée SAP d'{{site.data.keyword.cloud}} prennent en charge. Vous pouvez également choisir des solutions SAP basées sur des produits NetWeaver non-SAP, ainsi que des logiciels tiers capables de s'intégrer à SAP. Contactez le [support SAP ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://support.sap.com/en/index.html){: new_window} si vous envisagez de déployer un logiciel NetWeaver non-SAP ou un logiciel tiers dans votre paysage IaaS {{site.data.keyword.cloud}}. 

Soyez aussi précis que possible lorsque vous déterminez la talle de votre serveur en fonction des applications que vous prévoyez d'exécuter, de la croissance potentielle et des performances. De plus, gardez à l'esprit les exigences en matière de stockage et de mémoire pour vos applications. Les systèmes SAP dans un paysage présentent des exigences spécifiques pour la connectivité entre eux ou à des systèmes externes. Pour plus d'informations, voir [Points à prendre en compte lors de la planification de votre paysage SAP](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations).

Le tableau 1 contient les étapes du processus de planification. Utilisez-le pour générer votre paysage SAP cible.

Tableau 1. Présentation du processus de planification

| Etape | Détails |
| --- | --- |
| 1 | [Obtention des données d'identification SAP et {{site.data.keyword.cloud_notm}} et création de comptes](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-get_sap_ibm_credentials#get_sap_ibm_credentials) |
| 2 | [Consultation de la documentation SAP et {{site.data.keyword.cloud_notm}} pertinente](/docs/infrastructure/sap-netweaver/sap-review-doc.html) |
| 3 | [Détermination de vos applications SAP NetWeaver](/docs/infrastructure/sap-netweaver/sap-determine-apps.html) |
| 4 | [Dimensionnement du serveur](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server) |
| 5 | [Détermination de votre configuration](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration) |

## Etapes suivantes

Sélectionnez l'étape approprié dans le tableau 1 pour commencer à planifier votre paysage SAP.
