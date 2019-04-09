---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, RDBMS, SAP Application Performance Standards, SAPS, SAP Certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 5. Determinazione della tua configurazione
{: #determine_configuration}

Con un sistema SAP NetWeaver, hai due opzioni di distribuzione:
  * Sistema centrale, che è un'installazione a singolo host (due livelli)
  * Sistema distribuito, che è un'installazione a più host (tre livelli)

Le opzioni influenzano la tua scelta del server. Potresti voler distribuire il tuo carico di lavoro a server differenti oppure, per semplicità, tenere il carico di lavoro su un singolo server. Consulta [Configurazione della tua infrastruttura](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-set_up_infrastructure#set_up_infrastructure) per istruzioni dettagliate su come distribuire il tuo server.

## Configurazione dell'archiviazione
{: #storage_config}

La Tabella 1 è una configurazione dell'archiviazione di esempio per un server da 256 GB con 50.000 [SAPS](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server), 1,5 TB a 6.000 IOPS per un sistema centrale con SAP, con un database {{site.data.keyword.Db2_on_Cloud_long}} con[{{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted#GettingStarted) o [{{site.data.keyword.cloud_notm}} {{site.data.keyword.filestorage_short}}](/docs/infrastructure/FileStorage?topic=FileStorage-GettingStarted#GettingStarted) esterna (4 IOPS/GB). Il calcolo per l'IOPS è

  * 6.000 IOPS/1.500 GG = 4 IOPS/GB necessari per l'archiviazione esterna. Il presupposto sono 3.000 GB per il backup a 2 IOPS/GB (prestazioni medie).

Tabella 1. Layout dell'archiviazione di esempio basato sul calcolo dell'IOPS

| File system | # di volumi | Tipo di archiviazione | IOPS/GB | GB | # di IOPS |
| --- | --- | --- | --- | --- | --- |
| `/` | 1 | Interno | N/D | 150 GB | N/D |
| `/boot` | 1 | Interno | N/D | 0,25 GB | N/D |
| `swap` | 1 | Interno | N/D | 256 GB | N/D |
| `/db2` (compresi i log) | 1 | Interno | N/D | 250 GB | N/D |
| `sapdata` | 1 | Esterno | 4 IOPS/GB | 1,500 GB | 6.000 IOPS |
| `backup/log and backup` | 1 | Esterno | 2 IOPS/GB | 3.000 GB | 6.000 IOPS |

## Configurazione ad alta disponibilità
{: #ha_config}

L'ambiente {{site.data.keyword.cloud_notm}} non supporta alcuno scenario di alta disponibilità (HA, high availability) preconfigurato. Puoi tuttavia configurare degli scenari HA in base all'estensione HA per il sistema operativo da te scelto. Aggiungi l'estensione HA aggiungendo l'hardware richiesto e i componenti software richiesti ai tuoi landscape. Se hai bisogno di ulteriori licenze software, di accedere ai vari repository software o entrambe le cose, rivolgiti al [supporto {{site.data.keyword.cloud_notm}}](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) per assistenza nella configurazione degli eventuali requisiti aggiuntivi.

Queste informazioni sono valide sia per il software HA per SAP NetWeaver che per il software HA per l'RDBMS (relational database management system) che scegli. Ciò include i meccanismi di alta disponibilità e di ripristino di emergenza per il tuo RDBMS, ad esempio la replica. Le procedure di configurazione non sono diverse da qualsiasi altra procedura di configurazione in un ambiente in loco e richiedono la stessa procedura di configurazione di hardware e software.

## Passi successivi

Ora sei pronto a iniziare ad eseguire il provisioning del tuo {{site.data.keyword.baremetal_short}}. Vedi [Provisioning del tuo landscape SAP NetWeaver
](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment) per i tuoi passi successivi.
