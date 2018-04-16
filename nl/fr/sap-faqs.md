---



copyright:
  years: 2017, 2018
lastupdated: "2018-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Foire aux questions : SAP sur IBM Cloud
{: #faqs}

## Ai-je besoin que DB2 exécute SAP NetWeaver sur {{site.data.keyword.cloud_notm}} ?

Consultez régulièrement la [note SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) ainsi que la page Web [SAP Product Availability Matrix](https://apps.support.sap.com/sap/support/pam). Notez soigneusement le système d'exploitation mentionné dans la note SAP, car votre base de données requiert des Service Pack différents.

## Pourquoi {{site.data.keyword.Db2_on_Cloud_short}} a-t-il été choisi pour la certification {{site.data.keyword.cloud_notm}} ?

La raison est que {{site.data.keyword.Db2_on_Cloud_long_notm}} est un produit {{site.data.keyword.IBM_notm}} et que {{site.data.keyword.cloud_notm}} fait partie d'{{site.data.keyword.IBM_notm}} et a été choisi pour notre certification.

## Puis-je fractionner mon environnement SAP entre plusieurs centres de données ?

Pour une installation SAP distribuée, il est préférable d'avoir tous les noeuds dans le même centre de données et segment VLAN. Dans le cas contraire, des retards et temps d'attente peuvent être observés, rendant votre système SAP peu réceptif.

## Puis-je mettre en oeuvre la haute disponibilité SAP telle que définie par l'architecture SAP ?

La seule architecture à haute disponibilité prise en charge est la mise à l'échelle des serveurs d'applications. A l'heure actuelle, aucun matériel n'est compatible avec la haute disponibilité.

## Puis-je télécharger le logiciel de distribution SAP directement depuis {{site.data.keyword.cloud_notm}} ?

Pour l'instant, nous n'offrons pas de lien direct à [SAP Service Marketplace](https://websmp201.sap-ag.de/). Par conséquent, vous devez télécharger les DVD de distribution comme vous le faites actuellement pour le déploiement sur site.
