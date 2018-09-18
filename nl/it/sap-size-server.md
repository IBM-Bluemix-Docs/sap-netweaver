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


# 4. Dimensionamento del server
{: #size_the_server}

Dopo che hai deciso quali soluzioni SAP intendi utilizzare, prosegui determinando il numero di {{site.data.keyword.baremetal_long}} di cui hai bisogno per supportare il tuo landscape SAP e assicurarti che i server siano dimensionati in modo corretto.
{: shortdesc}

## Descrizione della metodologia di dimensionamento di SAP
{: #size_method}

La metodologia di dimensionamento di SAP per le applicazioni basate su SAP NetWeaver è basata sui benchmark SAP, quali le informazioni da SAP e le effettive esperienze dei clienti. L'unità di carico di lavoro SAP di base è un SAPS (SAP Application Performance Standard). SAPS è una definizione di velocità effettiva coniata dal personale che di occupa dei test delle prestazioni e della pianificazione della capacità di SAP. Ad esempio, 100 SAPS sono definiti come 2.000 elementi di riga di ordine aziendale pienamente elaborati all'ora nel benchmark delle applicazioni SAP SD (SAP Sales and Distribution) standard. È equivalente a 2.400 transazioni SAP all'ora con la soluzione SAP ERP (SAP Enterprise Resource Planning). La funzionalità dei processori è misurata durante il test di benchmark standard (SAP SD) certificato da SAP. Per ulteriori dettagli sul test di benchmark certificato da SAP, consulta [*SAP Business Suite on IBM X6 Systems Reference Architecture*](https://lenovopress.com/redp5073.pdf). Il test valuta il processo in merito alla sua capacità di elaborare il lavoro quando il carico sulla CPU è prossimo al 100% con un tempo di risposta inferiore a 1 secondo.

## Utilizzo di SAP Quick Sizer
{: #quicksizer}
  
Il [SAP Quick Sizer](https://service.sap.com/quicksizer) è uno strumento basato sul web ed è fornito da SAP per tutti i partner e i clienti. Le informazioni di dimensionamento vengono immesse direttamente nello strumento, dove vengono dimensionate le applicazioni basate su SAP NetWeaver e quelle non basate su SAP NetWeaver. Richiede un ID S-user SAP.
  
Calcola il carico di lavoro (in SAPS) e lo regola per consentire un utilizzo del processore adatto. Quindi, se era richiesto un carico di lavoro di 4.800 transazioni di benchmark SAP SD all'ora, lo strumento lo calcola come 200 SAPS. Se è consentito un carico del processore di destinazione del 33% , regolare questo valore per trovare un processore capace di 600 SAPS al 100% (=200 al 33%). Per ulteriori dettagli sul calcolo SAPS, consulta [*SAP Business Suite on IBM X6 Systems Reference Architecture*![Icona link esterno]](../../icons/launch-glyph.svg "Icona link esterno")](https://lenovopress.com/redp5073.pdf){: new_window}.

Sebbene il metodo di dimensionamento possa essere considerato conservativo, considera il fatto che i numeri SAPS per i tuoi server sono stati calcolati in base a sistemi SAP altamente ottimizzati che eseguono solo specifici carichi di lavoro SAP SD. A seconda del tipo di applicazione SAP e dell'eventuale configurazione personalizzata o codifica personalizzata nel tuo sistema, i risultati potrebbero variare. Inoltre, i requisiti per il tuo progetto, come PoC (proof-of-concept) o quelli relativi a prestazioni e tempo di risposta, potrebbero essere differenti.

## Scelta di un server bare metal {{site.data.keyword.cloud_notm}}
{: #choose_server}

Dopo che hai determinato le tue applicazioni SAP e dopo che i numeri SAPS sono stati calcolati utilizzando il SAP Quick Sizer, o in base al tuo landscape attuale, sei pronto a scegliere un server dai modelli offerti. La Tabella 1 contiene i numeri SAPS per i {{site.data.keyword.baremetal_short}} che sono stati certificati per SAP NetWeaver. Vedi [SAP Standard Application Benchmarks![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")]](https://www.sap.com/about/benchmark.html){: new_window} per i documenti di certificazione. 

Tutti i tipi di server supportati elencati nella Tabella 1 corrispondono a quelli che sono stati certificati da SAP con lo stesso nome pubblicato. I server sono verificati nella[nota SAP 2414097![Icona link esterno]](../../icons/launch-glyph.svg "Icona link esterno")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}; fai clic [qui![Icona link esterno]](../../icons/launch-glyph.svg "Icona link esterno")](https://www.sap.com/dmc/exp/2014-09-02-hana-hardware/enEN/power-systems.html){: new_window} per un elenco completo. Nota: i nomi pubblicati sono soggetti a modifica.

Tabella 1. {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} certificato per SAP NetWeaver

| Tipo di server | SAPS | RAM |
| --- | --- | --- |
| BI.S1.NW32 | 10980 | 32 GB |
| BI.S1.NW128 | 54130 | 128 GB |
| BI.S1.NW256 | 55020 | 256 GB |
| BI.S2.NW512 | 65520 | 512 GB |
| BI.S3.NW32 | 11970 | 32 GB |
| BI.S3.NW64 | 12750 | 64 GB |
| BI.S3.NW192 | 78850 | 192 GB |
| BI.S3.NW384 | 79430 | 384 GB |
| BI.S3.SW768 | 79630 | 768 GB |

## Migrazione di un sistema SAP esistente 
{: #migrating}

Se intendi migrare un sistema SAP esistente da qualsiasi origine al tuo ambiente {{site.data.keyword.cloud_notm}}, puoi determinare i numeri SAPS dai numeri SAPS del tuo ambiente attuale. Utilizza le informazioni sul tuo carico di lavoro attuale (le CPU e la RAM utilizzati) e ottieni gli equivalenti SAPS per la tua CPU dai [risultati del benchmark SAP SD![Icona link esterno]](../../icons/launch-glyph.svg "Icona link esterno")](https://www.sap.com/about/benchmark.html){: new_window}.

## Passi successivi

 [5. Determinazione della tua configurazione](/docs/infrastructure/sap-netweaver/sap-determine-configuration.html)
