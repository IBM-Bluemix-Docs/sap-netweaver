---



copyright:
  years: 2018
lastupdated: "2018-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 4. Dimensionnement du serveur
{: #size_the_server}

Une fois que vous avez choisi les solutions SAP à utiliser, l'étape suivante consiste à déterminer le nombre de serveurs IBM Bare Metal dont vous avez besoin pour prendre en charge votre paysage SAP et garantir un dimensionnement approprié des serveurs.
{: shortdesc}

## Comprendre la méthodologie de dimensionnement de SAP
{: #size_method}

La méthode de dimensionnement SAP conçue pour les applications orientées SAP NetWeaver s'appuie sur les benchmarks SAP, notamment sur la base d'expériences clients et SAP. L'unité de charge de travail SAP de base est la norme SAPS (SAP Application Performance Standard), qui désigne un terme inventé par le personnel en charge des tests de performance et de la planification des capacités SAP. Par exemple, 100 SAPS représentent le traitement de 2 000 lignes de commande d'achat par heure dans le cadre du benchmark de l'application standard Administration des ventes SAP (SAP SD). Cela correspond à 2 400 transactions SAP par heure avec le progiciel de gestion intégré (SAP ERP). La capacité des processeurs se mesure pendant le benchmark type (SAP SD) qui est certifié par SAP. Pour plus d'informations sur le test de performances certifié par SAP, voir le manuel [*SAP Business Suite on IBM X6 Systems Reference Architecture*](https://lenovopress.com/redp5073.pdf) (en anglais). Le test évalue le processus sur sa capacité à exécuter les tâches avec une charge CPU proche de 100 % et un temps de réponse inférieur à 1 seconde.

## Exécuter SAP Quick Sizer
{: #quicksizer}
  
[SAP Quick Sizer](https://service.sap.com/quicksizer) est un outil Web mis à la disposition de tous les partenaires et clients SAP. Les informations de dimensionnement sont saisies directement dans l'outil, qui calcule la taille des applications NetWeaver SAP et non-SAP. Vous devez disposer pour cela d'un identifiant SAP S-user.
  
L'outil calcule la charge de travail (en SAPS) et l'ajuste en fonction de l'utilisation du processeur. Par conséquent, si une charge de travail de 4 800 transactions par heure (benchmark SAP SD) est requise, l'outil le convertit en 200 SAPS. Si la charge CPU autorisée est de 33 %, modifiez cette valeur de manière à avoir un processeur capable d'exécuter 600 SAPS avec une charge de 100 % (soit environ 200 à 33 %). Pour plus de détails sur le calcul SAPS, voir [*SAP Business Suite on IBM X6 Systems Reference Architecture*![Icône de lien externe]](../../icons/launch-glyph.svg "Icône de lien externe")](https://lenovopress.com/redp5073.pdf){: new_window}.

Bien que la méthode du dimensionnement puisse être considérée comme prudente, tenez compte du fait que les valeurs SAPS de vos serveurs ont été calculées à partir de systèmes SAP hautes performances exécutant uniquement des charges de travail SAP SD spécifiques. En fonction du type d'application SAP (personnalisation de la configuration ou du code système), les résultats peuvent varier. De même, les exigences liées à votre projet, notamment en termes de preuve de concept (PoC), de performances ou de temps de réponse, peuvent être différentes.

## Choisir un serveur {{site.data.keyword.cloud_notm}} bare metal
{: #choose_server}

Une fois que vous avez identifié vos applications SAP et calculé les valeurs SAPS à l'aide de l'outil SAP Quick Sizer, ou en fonction de votre paysage actuel, vous pouvez choisir un serveur parmi les modèles proposés. Le tableau 1 répertorie les valeurs SAPS associées aux serveurs Bare Metal certifiés pour SAP NetWeaver. Voir [SAP Standard Application Benchmarks![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")]](https://go.sap.com/solution/benchmark.html){: new_window} pour consulter les documents de la certification. 

Tous les types de serveurs pris en charge qui figurent dans le tableau 1 correspondent à ceux ayant été certifiés par SAP avec les noms sous lesquels ils ont été publiés et peuvent être vérifiés dans la [note SAP 2414097![Icône de lien externe]](../../icons/launch-glyph.svg "Icône de lien externe")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}. Cliquez [ici ![Icône de lien externe]](../../icons/launch-glyph.svg "Icône de lien externe")](https://sap.com/solution/benchmark/appbm/cloud.html){: new_window} pour obtenir la liste complète. Notez que les noms publiés sont susceptibles d'être modifiés.

Tableau 1. Serveurs Bare Metal {{site.data.keyword.cloud_notm}} certifiés pour SAP NetWeaver

| Type de serveur | Document de certification | SAPS | RAM |
| --- | --- | --- | --- |
| BI.S1.NW32 | Cert16048 | 10 980 | 32 Go |
| BI.S1.NW128 | Cert16063 | 54 130 | 128 Go |
| BI.S1.NW256 | Cert17005 | 55 020 | 256 Go |
| BI.S1.NW512 | Cert17027 | 65 520 | 512 Go |

## Migrer vers un système SAP existant 
{: #migrating}

Si vous envisagez de procéder à la migration d'un système SAP existant depuis une source quelconque vers votre environnement {{site.data.keyword.cloud_notm}}, vous pouvez déterminer les valeurs SAPS à partir de celles de votre environnement actuel. Utilisez les informations relatives à votre charge de travail actuelle (unités CPU et mémoire RAM utilisées), et recherchez les valeurs SAPS correspondantes pour votre CPU à partir des [résultats du benchmark SAP SD![Icône de lien externe]](../../icons/launch-glyph.svg "Icône de lien externe")](https://go.sap.com/solution/benchmark.html){: new_window}.

## Etapes suivantes

 [5. Déterminer votre configuration](/docs/infrastructure/sap-netweaver/sap-determine-configuration.html)
