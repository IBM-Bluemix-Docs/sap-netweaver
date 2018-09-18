---



copyright:
  years: 2017, 2018
lastupdated: "2018-06-28"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Présentation de l'infrastructure IaaS SAP NetWeaver sur IBM Cloud
Un environnement d'infrastructure sous forme de services (IaaS) est constitué de plusieurs composants : centre de données, calcul, connectivité, stockage et réseau. 

## Centres de données

Avec des centres de données se trouvant en Amérique du Nord et en Amérique du Sud, en Europe, en Asie et en Australie, vous pouvez mettre à disposition des ressources de cloud partout où vous en avez besoin (et à tout moment). Chaque centre de données est connecté au réseau privé global d'{{site.data.keyword.cloud_notm}}, ce qui permet des transferts de données plus rapides et plus efficaces, partout dans le monde.

Consultez la page [Data Centers](https://www.ibm.com/cloud-computing/bluemix/data-centers){: new_window} pour en savoir plus sur les centres de données et les points de présence {{site.data.keyword.cloud_notm}}.

## Serveurs Bare Metal

Les serveurs IBM Bare Metal sont des serveurs physiques dont les fonctions de personnalisation sont limitées. Ils sont dédiés à votre usage particulier ou à celui de votre client, et ne sont pas jamais partagés, y compris au niveau des ressources serveur, avec d'autres clients {{site.data.keyword.cloud_notm}}. La gestion de ces serveurs vous appartient, à vous ou à vos clients, et ils sont mis à votre disposition sans hyperviseur.

Les possibilités de personnalisation étant limitées sur les serveurs bare metal, des temps de mise à disposition plus rapides, entre 1 et 4 heures, sont possibles. La mise à disposition rapide est utile lorsque vous essayez de mettre une application sur le marché avant vos concurrents.

Vous disposez d'un ensemble de combinaisons de mémoire RAM et d'unités centrales car les serveurs certifiés SAP présentent une quantité de mémoire RAM et un nombre d'unités centrales préconfigurés. La combinaison *ne peut pas* être changée au cours du processus de commande ou via un ticket de demande de service une fois les serveurs déployés.

Si votre projet inclut une couche de virtualisation, l'offre SAP NetWeaver prévoit la possibilité de commander des serveurs Bare Metal qui sont déployés avec VMware ESXi. L'instance ESX est directement sous votre contrôle, car elle est déployée dans votre centre de données. Le système est pleinement configuré en ce qui concerne la mise en réseau (en revanche, toute configuration supplémentaire, notamment en matière de stockage, vous incombe). Il est fortement recommandé qu'une personne ayant une bonne compréhension de l'administration ESX participe au lancement du projet.

Pour plus d'informations sur les serveurs bare metal, voir [About bare metal servers](https://console.bluemix.net/docs/bare-metal/about.html#about-bare-metal-servers). 

## Systèmes d'exploitation

Prenez connaissance de la [note SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097){: new window} pour obtenir la liste des systèmes d'exploitation permettant de déployer les systèmes basés sur SAP NetWeaver. Un identifiant SAP S-user est requis pour pouvoir accéder aux notes SAP. La licence associée au système d'exploitation invité est de votre responsabilité.

## Connectivité du réseau

La connectivité du réseau privé virtuel au réseau cloud virtuel d'{{site.data.keyword.cloud_notm}} est accordée automatiquement lorsque votre compte {{site.data.keyword.cloud_notm}} est configuré. Par défaut, votre serveur possède une adresse IP publique et une adresse IP privée. Si vous voulez que votre serveur soit privé, vous pouvez désactiver l'interface publique une fois votre serveur mis à disposition ou commander votre serveur en tant que serveur privé. Reportez-vous à la rubrique [Getting started with Virtual Private Networking](https://console.bluemix.net/docs/infrastructure/iaas-vpn/getting-started.html#getting-started-with-virtual-private-networking-vpn-) pour plus d'informations sur le réseau privé virtuel {{site.data.keyword.cloud_notm}}.

## Stockage
{: #storage}

Un stockage local est fourni avec vos serveurs Bare Metal ; il utilise le réseau local virtuel privé d'{{site.data.keyword.cloud_notm}} pour assurer une sécurité au niveau de l'entreprise sans empêcher l'accès administrateur. Il s'agit de la solution idéale pour les applications gourmandes en capacité de stockage et en besoins d'entrées/sorties, par exemple les systèmes d'exploitation, les bases de données et les logiciels d'application. L'espace disque du serveur SAP NetWeaver dépend de la configuration de votre serveur. Contactez le support [{{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/support/index.html#getting-customer-support) pour connaître les différentes options d'extension si le stockage local sur votre serveur est insuffisant pour votre charge de travail.

Il existe deux types de stockage pour {{site.data.keyword.cloud_notm}} de type bloc et fichier, à partir desquels effectuer les sauvegardes et les restaurations pour SAP NetWeaver. Les deux types utilisent des opérations d'entrée-sortie par seconde, qui permettent de déterminer les besoins en matière de stockage. Celles-ci sont mesurées en fonction d'une taille de bloc de 16 ko, avec une distribution égale entre les entrées et les sorties. Pour pouvoir effectuer le nombre maximal d'opérations d'entrée-sortie sur un volume, les ressources réseau adéquates doivent être disponibles. Vous devez également prendre en compte l'utilisation du réseau privé hors du stockage et hors côté hôte, ainsi que les réglages propres à l'application (par exemple les piles IP et les profondeurs de file d'attente). Pour plus d'informations sur les niveaux de stockage et les performances, voir [Getting started with Block Storage](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) et [Getting started with File Storage](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage).

{{site.data.keyword.cloud_notm}} propose également le stockage NAS (Network Attached Storage), qui est intéressant si vous recherchez une solution de sauvegarde rapide et économique pour vos périphériques. Le périphérique de stockage NAS est compatible avec :
  * Red Hat Enterprise Linux (RHEL) pour SAP Business Applications 6.X OS
  * Le protocole FTP avec Parallels Plesk Panel et cPanel@WHM
  * Microsoft Windows Server via des procédures Windows standard utilisant le protocole CIFS
  
Les stockages NAS et FTP sont facturés tous les mois et disponibles dans différentes tailles. Vous pouvez interagir avec vos stockages NAS et FTP principalement depuis la ligne de commande ou un terminal du système d'exploitation, ou par le biais d'interactions de type "pointer-cliquer" dans les panneaux, sur le portail client de l'infrastructure {{site.data.keyword.cloud_notm}}.

Vous trouverez davantage d'informations sur les NAS au sein d'un environnement {{site.data.keyword.cloud_notm}} sous [Getting started with NAS](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#getting-started-with-nas).

## Déploiement et gestion

Les serveurs Bare Metal d'{{site.data.keyword.cloud_notm}} sont déployés via le portail client de l'infrastructure {{site.data.keyword.cloud_notm}} ou l'API une fois que vous avez créé votre compte client {{site.data.keyword.cloud_notm}}. Ils peuvent être gérés par le biais du portail client, de l'API ou de l'interface de ligne de commande. Pour plus d'informations, consultez la rubrique [About bare metal servers](https://console.bluemix.net/docs/bare-metal/about.html#about-bare-metal-servers).

## Support

Le [support clients {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/support/index.html#getting-customer-support) traite toutes les questions et tous les problèmes susceptibles de survenir en recourant à divers médias, tels que le support par messagerie instantanée, téléphone ou création de ticket. Le support client est proposé gratuitement à tous les clients d'{{site.data.keyword.cloud_notm}} et traite la plupart des tickets de demande de service ouverts chaque jour. Pour plus d'informations, voir [Comment obtenir l'aide dont j'ai besoin ?](https://console.bluemix.net./docs/support/index.html#getting-customer-support).
