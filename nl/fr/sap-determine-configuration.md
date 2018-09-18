---



copyright:
  years: 2018
lastupdated: "2018-05-18"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 5. Détermination de votre configuration
{: #determine_configuration}

Au sein d'un système SAP NetWeaver, deux options de déploiement s'offrent à vous :
  * Un système central, qui représente une installation sur un hôte unique (deux niveaux)
  * Un système distribué, qui représente une installation sur plusieurs hôtes (trois niveaux)
  
L'option retenue a une influence sur le choix du serveur. En effet, vous pouvez vouloir distribuer votre charge de travail sur différents serveurs ou la conserver sur un seul serveur pour des raisons de simplicité. Consultez la rubrique [Configuration de votre infrastructure](/docs/infrastructure/sap-netweaver/sap-setting-up-infrastructure.html#set_up_infrastructure) pour obtenir une description détaillée des étapes de déploiement de votre serveur.

## Configuration du stockage
{: #storage_config}

Le tableau 1 ci-dessous illustre un exemple de configuration de stockage pour un serveur 256 Go avec 50 000 [SAPS](/docs/infrastructure/sap-netweaver/sap-size-server.html), 1,5 To à 6 000 IOPS pour un système central avec SAP, associé à une base de données {{site.data.keyword.Db2_on_Cloud_long}} avec un stockage externe de type [{{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) ou [{{site.data.keyword.cloud_notm}} {{site.data.keyword.filestorage_short}}](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage) (4 IOPS/Go). Le calcul de la valeur IOPS est le suivant :

  * 6 000 IOPS/1 500 GG = 4 IOPS/Go requis pour le stockage externe. On part de l'hypothèse selon laquelle 3 000 Go sont nécessaires pour la sauvegarde à 2 IOPS/Go (performances moyennes).
  
Tableau 1. Exemple de configuration de stockage basé sur le calcul du nombre d'E/S par seconde (IOPS)

| Système de fichiers | Nbre de volumes | Type de stockage | IOPS/Go | Go | Nbre d'E/S par seconde (IOPS) |
| --- | --- | --- | --- | --- | --- |
| / | 1 | Interne | N/A | 150 Go | N/A |
| /boot | 1 | Interne | N/A | 0,25 Go | N/A |
| swap | 1 | Interne | N/A | 256 Go | N/A |
| /db2 (y compris les journaux) | 1 | Interne | N/A | 250 Go | N/A |
| sapdata | 1 | Externe | 4 IOPS/Go | 1 500 Go | 6 000 IOPS |
| backup/log et backup | 1 | Externe | 2 IOPS/Go | 3 000 Go | 6 000 IOPS |

## Configuration à haute disponibilité
{: #ha_config}

L'environnement {{site.data.keyword.cloud_notm}} ne prend pas en charge les scénarios à haute disponibilité (HA) préconfigurés. Toutefois, vous pouvez configurer des scénarios HA basés sur l'extension HA de votre système d'exploitation. Vous ajoutez l'extension HA en intégrant les composants matériels et logiciels requis pour votre paysage. Si vous avez besoin de licences logicielles supplémentaires, accédez aux différents référentiels logiciels ou contactez le [support {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support) pour obtenir de l'aide sur la configuration des exigences supplémentaires.

Ces informations ne s'appliquent pas seulement au logiciel HA pour SAP NetWeaver, elles s'appliquent également au logiciel HA que vous choisissez pour le système de gestion de base de données relationnelle (RDBMS). Ceci inclut les mécanismes de haute disponibilité et de reprise après incident de votre RDBMS, telles que la réplication. Les procédures de configuration sont identiques à celles des procédures sur site et nécessitent les mêmes étapes de configuration matérielle et logicielle.

## Etapes suivantes

Vous pouvez maintenant commencer à mettre à disposition vos serveurs Bare Metal. Voir la rubrique [Provisioning your SAP NetWeaver environment](/docs/infrastructure/sap-netweaver/sap-provision-environment.html) pour en savoir plus sur les étapes suivantes.
  
  


