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

# Points à prendre en compte lors de la planification de votre paysage SAP
{: #considerations}

Les systèmes SAP dans un paysage ont des exigences spécifiques relatives à la connectivité, entre eux ou à des systèmes externes. Vous devez également penser à un stockage externe pour votre paysage et aux tâches à effectuer si vous décidez de déployer VMware sur votre serveur.

## Connectivité du réseau
{: #network_connectivity}

Le réseau [{{site.data.keyword.cloud_notm}} network](/docs/infrastructure/sap-netweaver/sap-about.html#ibm_cloud_network) fournit un aperçu de l'approche {{site.data.keyword.cloud}} de connectivité réseau. Les problèmes liés à la connectivité du réseau peuvent entraîner des délais considérables pour votre projet si vous ne procédez pas à la planification correctement, quelle que soit la façon dont vous prévoyez d'utiliser votre système. 

En général, vous disposez de deux choix d'interface pour vos serveurs {{site.data.keyword.cloud_notm}} mis à disposition dans l'infrastructure sous forme de services (IaaS). Le premier choix est une interface externe possédant une adresse IP publique. Le deuxième est une interface interne fournie avec une .adresse IP privée. conformément à la demande de commentaires (RFC) 1918. Vous pouvez également choisir une interface interne unique avec une .adresse IP privée.. L'une et l'autre de ces options peuvent faire l'objet d'une redondance via une “interface de bonding” Linux ou une association de cartes réseau Windows, et peuvent fonctionner à des vitesses de 100 Mbits/s, 1 Gbits/s ou 10 Gbits/s.

En fonction de votre cas d'utilisation, une adresse IP publique peut être acceptable dans des paysages PoC (preuve de concept), car l'adresse IP externe peut se révéler plus facile d'utilisation. Toutefois, un risque de sécurité existe même si un pare-feu de base est installé et préconfiguré. Si vous voulez utiliser une interface publique, assurez-vous de choisir une valeur de **bande passante publique** suffisamment élevée lorsque vous commandez votre serveur. Cette valeur détermine la quantité totale de données pouvant être transférées via l'interface au cours d'un mois. Alors qu'une communication réseau standard, via une interface graphique ou une interface RFC SAP, peut se résumer à seulement quelques mégaoctets par jour, des téléchargements massifs de données peuvent facilement dépasser 1 000 Go par mois. Vous devez soit connaître la quantité de données transférée, ou tout du moins avoir une idée de l'ordre de grandeur, soit utiliser la seconde option.

La deuxième option accède au réseau privé virtuel d'{{site.data.keyword.cloud_notm}} par le biais du portail {{site.data.keyword.cloud_notm}} Infrastructure Customer Portal, ou déploie un périphérique de sécurité dans votre paysage. Les périphériques de sécurité sont proposés pour les pare-feux, la conversion d'adresse réseau, l'accès au réseau privé virtuel et d'autres fonctions de réseau. En outre, ils peuvent fournir une bande passante plus élevée, ce qui permet de transférer de plus grosses quantités de données vers un centre de données {{site.data.keyword.cloud_notm}}. Nous recommandons à votre service de gestion du réseau de parler à un membre de l'équipe de [support {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support) une fois que vous avez déterminé l'agencement de votre paysage et la connectivité requise sur la couche de l'application SAP.

### Réseaux locaux virtuels
{: #vlans}

Si vous voulez séparer différents types de trafic réseau dans votre paysage, vous pouvez commander d'autres réseaux locaux virtuels. Gardez à l'esprit que les réseaux locaux virtuels supplémentaires ne permettent qu'une séparation du trafic et n'améliorent pas les performances. La répartition du trafic doit être considérée dans un contexte de déploiements VMware élaborés, dans lequel différents types de trafic réseau doivent absolument être isolés les uns des autres pour des raisons de sécurité.

Par exemple, dans les cas d'utilisation ci-dessous, vous voudrez peut-être vous assurer que tous les serveurs sont installés sur le même réseau local virtuel lors du déploiement :
  *	Plusieurs serveurs échangent des données, notamment dans une configuration SAP à trois niveaux—dans laquelle la base de données et les instances d'application SAP se trouvent sur des serveurs différents
  *	Plusieurs systèmes échangent de grandes quantités de données

Dans le cas d'un déploiement SAP avec stockage local, même pour les configurations à trois niveaux, des réseaux de 1 Go sont suffisants. D'autres critères sont toutefois à prendre en compte ; pour en savoir plus sur les options de stockage réseau, voir [Stockage externe](/docs/infrastructure/sap-netweaver/sap-considerations.html#external_storage).

### Configurations hybrides
{: #hybrid}

L'offre {{site.data.keyword.cloud_notm}} pour applications SAP peut être considérée comme un centre de données externe, en particulier si vous envisagez d'implémenter un paysage hybride avec des systèmes SAP sur un centre de données {{site.data.keyword.cloud_notm}} et d'autres systèmes sur site. Dans le cadre d'une configuration hybride, les éléments de configuration spécifiques à prendre en compte pendant la phase de planification du projet sont les suivants :

  *	[Système de gestion des transports SAP (STMS)](https://help.sap.com/saphelp_me60/helpdata/en/c4/6045377b52253de10000009b38f889/frameset.htm) : Configurez-le sur la base de groupes  de transports pour empêcher le partage de fichiers sur plusieurs centres de données.
  *	[SAProuter](https://support.sap.com/en/tools/connectivity-tools/saprouter.html) : Application permettant d'accéder au système SAP SOS (On-Line Service System). Utilisez votre application SAProuter sur site, qui est déjà disponible, pour accéder à OSS. Cette application peut être utilisée via d'autres tronçons SAProuter si le routage IP n'est pas autorisé entre vos systèmes {{site.data.keyword.cloud_notm}} et votre application SAProuter sur site. Vous pouvez également envisager de configurer une autre application SAProuter basée sur un serveur {{site.data.keyword.cloud_notm}} avec une adresse IP publique et la connecter au système SAP OSS via une connexion Internet.
  *	[SAP Solution Manager](https://support.sap.com/en/solution-manager.html) : l'accès à SAP Solution Manager est soumis à diverses exigences de connectivité, entre la plateforme et ses systèmes gérés, en fonction de votre scénario d'utilisation. Ces scénarios requièrent une bonne compréhension de la connectivité réseau requise.  

## Stockage externe
{: #external_storage}

Le stockage local offre les meilleures performances en terme de déploiement de base de données. Outre le stockage local, vous pouvez avoir besoin de davantage de mémoire externe pour effectuer vos sauvegardes, ou la base de données de vos systèmes SAP risque de dépasser la capacité de stockage des disques internes. Vous pouvez également avoir besoin de mémoire externe pour votre projet, par exemple sous forme de serveurs ESX partageant plusieurs machines virtuelles (VM). Dans ce cas, vous pouvez commander un stockage par blocs ou un stockage NAS (Network Attached Storage) comme décrit dans [Stockage](/docs/infrastructure/sap-netweaver/sap-general-iaas-concepts.html#storage). Sachant que les données du périphérique de stockage par blocs ou NAS supplémentaire sont acheminées via les mêmes adaptateurs physiques que le reste du trafic réseau, vous devrez tenir compte des répercussions possibles. Les données de performances comparables aux données mesurées dans les référentiels de certification peuvent être difficiles à atteindre.

Il est préférable de choisir un centre de données 10 Go pour votre déploiement si vous envisagez d'avoir principalement recours à un stockage externe au lieu d'un stockage local. Par exemple, le stockage externe peut être utilisé à la fois pour vos sauvegardes et votre base de données, de même que si vous placez une charge élevée sur votre système SAP (avec un risque de surcharge du réseau 1 Go  avec une charge d'ES de 90 Mo/s).

Il est également conseillé d'utiliser au moins 4 IOPS/Go si votre base de données réside principalement sur le stockage externe. Un stockage moindre ne doit être envisagé que si les performances de base de données ne sont pas primordiales pour votre projet ou vos besoins de sauvegarde.

Si vous prévoyez d'utiliser le stockage externe comme magasin de données pour VMware ESX, consultez les bonnes pratiques sous [Storage to use with VMware Systems](https://console.bluemix.net/docs/infrastructure/vmware/select-storage-option-use-vmware.html#storage-to-use-with-vmware-systems) afin de déterminer le type de stockage optimal pour votre utilisation.

## Déploiement de serveurs VMware ESXi
{: #vmware_server}

Les déploiements basés sur VMware ESXi dans {{site.data.keyword.cloud_notm}} sont différents des autres déploiement basés sur le Cloud. {{site.data.keyword.cloud_notm}} ne fournit pas à ses clients de machines virtuelles en cours d'exécution. Il vous incombe de contrôler votre environnement et de le configurer en fonction de vos besoins. Lorsque vous commandez un serveur VMware ESX, celui-ci est déjà configuré. Les liens ci-dessous fournissent des informations sur les types de stockage supplémentaires et l'exécution de machines virtuelles invitées.

  *	[Storage to use with VMware Systems](https://console.bluemix.net/docs/infrastructure/vmware/select-storage-option-use-vmware.html#storage-to-use-with-vmware-systems) fournit des précisions sur les modalités d'intégration du stockage dans un environnement ESX.
  * [Mounting iSCSI VMware ESXi](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi) décrit la procédure d'intégration d'un stockage iSCSI à ESX.
  * [Creating a VMware ESX Virtual Machine](https://console.bluemix.net/docs/infrastructure/vmware/vmware-esx-create-virtual-machine.html#creating-a-vmware-esx-virtual-machine) vous guide tout au long du processus de déploiement de votre première machine virtuelle.

Notez que pour déployer un logiciel basé sur SAP NetWeaver, vous devez choisir le système d'exploitation invité dans la liste qui figure dans la [note SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097).
