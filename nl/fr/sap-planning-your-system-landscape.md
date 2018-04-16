---



copyright:
  years: 2017, 2018
lastupdated: "2018-01-23"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Planification du paysage de votre système
{: #planning-your-system-landscape}

Un *paysage* SAP est un groupe de deux *systèmes* SAP ou plus, qui incluent habituellement le développement, la qualité et le test, et la production. Un système SAP se compose d'une ou de plusieurs *instances SAP*, qui constituent des groupes de processus démarrés et arrêtés simultanément. Pour plus d'informations sur les paysages SAP, voir [*SAP Business Suite on IBM X6 Systems Reference Architecture*](https://lenovopress.com/redp5073.pdf). 
{: shortdesc}

Vous pouvez configurer plusieurs aspects du paysage, par exemple la taille du serveur ou la taille du stockage, pour toutes les solutions SAP sur le marché. Ces solutions incluent les produits reposant sur SAP NetWeaver, comme [SAP Business Suite](https://open.sap.com/courses/suitehana1), SAP Business Warehouse, et tous les modules complémentaires SAP spécifiques, que les serveurs de l'offre {{site.data.keyword.cloud}} for SAP Applications prennent en charge. Vous pouvez également choisir des solutions SAP basées sur des produits NetWeaver non-SAP, ainsi que des logiciels tiers capables de s'intégrer à SAP. Contactez le [support SAP](https://support.sap.com/en/index.html) si vous envisagez de déployer un logiciel NetWeaver non-SAP ou un logiciel tiers dans votre paysage IaaS {{site.data.keyword.cloud}}.

Soyez aussi précis que possible lorsque vous déterminez la talle de votre serveur en fonction des applications que vous prévoyez d'exécuter, de la croissance potentielle et des performances. De plus, gardez à l'esprit les exigences en matière de stockage et de mémoire pour vos applications. Les systèmes SAP dans un paysage présentent des exigences spécifiques pour la connectivité entre eux ou à des systèmes externes. Pour plus d'informations, voir [Points à prendre en compte lors de la planification de votre paysage SAP](/docs/infrastructure/sap-netweaver/sap-considerations.html).

Le tableau 1 contient les étapes du processus de planification. Utilisez-le pour générer votre paysage SAP cible.

Tableau 1. Présentation du processus de planification

| Etape | Détails |
| --- | --- |
| 1 | [Obtention des données d'identification SAP et {{site.data.keyword.cloud_notm}} et création de comptes](/docs/infrastructure/sap-netweaver/sap-get-credentials.html) |
| 2 | [Consultation de la documentation SAP et {{site.data.keyword.cloud_notm}} pertinente](/docs/infrastructure/sap-netweaver/sap-review-doc.html) |
| 3 | [Déterminer vos applications SAP NetWeaver](sap-determine-apps.html) |
| 4 | [Dimensionnement du serveur](/docs/infrastructure/sap-netweaver/sap-size-server.html) |
| 5 | [Détermination de votre configuration](/docs/infrastructure/sap-netweaver/sap-determine-configuration.html) |

## Etapes suivantes

Sélectionnez l'étape approprié dans le tableau 1 pour commencer à planifier votre paysage SAP.

