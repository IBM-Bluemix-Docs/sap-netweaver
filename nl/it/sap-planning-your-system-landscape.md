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

# Pianificazione del tuo landscape di sistema
{: #planning-your-system-landscape}

Un *landscape* SAP è un gruppo di due o più *sistemi* SAP che di norma includono sviluppo, qualità e test e produzione. Un sistema SAP consiste in una o più *istanze SAP*, che sono un gruppo di processi che vengono avviati e arrestati contemporaneamente. Per ulteriori informazioni sui landscape SAP, consulta [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://lenovopress.com/redp5073.pdf){: new_window}.
{: shortdesc}

Ci sono diverse possibili configurazioni del landscape, come ad esempio server (dimensione)/archiviazione (dimensione), per tutte le soluzioni SAP sul mercato. Queste soluzioni includono i prodotti basati su SAP NetWeaver, come [SAP Business Suite ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://open.sap.com/courses/suitehana1){: new_window}, SAP Business Warehouse  e tutti gli specifici componenti aggiuntivi SAP, che sono supportati dai server nel supporto {{site.data.keyword.cloud}} SAP-Certified Infrastructure. Altre soluzioni da tenere presente sono le soluzioni SAP non basate su SAP NetWeaver e il software di terze parti che potrebbe integrarsi con SAP. Contatta il [supporto di SAP ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://support.sap.com/en/index.html){: new_window} se intendi distribuire software non basato su SAP NetWeaver o di terze parti nel tuo landscape IaaS {{site.data.keyword.cloud}}.

Devi essere il più dettagliato possibile quando determini la dimensione del tuo server in base alle applicazioni che intendi eseguire, alla crescita potenziale e alle prestazioni. Tieni inoltre presente i tuoi requisiti di archiviazione e memoria per le tue applicazioni. I sistemi SAP in un landscape hanno dei requisiti specifici per la connettività, tra di loro oppure a sistemi esterni. Per ulteriori informazioni, consulta [Elementi da considerare quando pianifichi il tuo landscape SAP](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations).

La Tabella 1 contiene la procedura contenuta nel processo di pianificazione. Utilizzala come ausilio nella creazione del tuo landscape SAP di destinazione.

Tabella 1. Panoramica del processo di pianificazione

| Passo | Dettagli |
| --- | --- |
| 1 | [Ottieni SAP e le credenziali {{site.data.keyword.cloud_notm}} e crea gli account](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-get_sap_ibm_credentials#get_sap_ibm_credentials) |
| 2 | [Esamina l'eventuale documentazione di SAP {{site.data.keyword.cloud_notm}}](/docs/infrastructure/sap-netweaver/sap-review-doc.html) pertinente |
| 3 | [Determina le tue applicazioni SAP NetWeaver](/docs/infrastructure/sap-netweaver/sap-determine-apps.html) |
| 4 | [Dimensiona il server](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server) |
| 5 | [Determina la tua configurazione](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration) |

## Passi successivi

Seleziona il passo appropriato nella Tabella 1 per iniziare a pianificare il tuo landscape SAP.
