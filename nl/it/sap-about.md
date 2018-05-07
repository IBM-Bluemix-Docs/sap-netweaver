---



copyright:
  years: 2017, 2018
lastupdated: "2018-01-25"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# Informazioni su IBM Cloud for SAP Applications
{: #about_ibmcloud_for_sap}

Il partenariato, la collaborazione e il lavoro di squadra di IBM e SAP in aree che includono hardware, software, cloud, servizi e finanza dura da più di 45 anni. La prima collaborazione risale al 1972 ed ha continuato a crescere con centinaia di clienti SAP che usano {{site.data.keyword.cloud}} come loro soluzione IaaS (infrastructure-as-a-service). {{site.data.keyword.IBM_notm}} ha continuato a ottimizzare i suoi prodotti di infrastruttura cloud per includere il supporto per la piattaforma di elaborazione SAP NetWeaver. 

È in virtù di tale relazione, e di altre funzionalità di {{site.data.keyword.cloud_notm}}, che {{site.data.keyword.IBM_notm}} è stato selezionato come uno dei principali provider strategici di SAP di servizi di infrastruttura cloud per le sue applicazioni critiche per il business. Il supporto per la suite di prodotti di SAP NetWeaver è disponibile tramite {{site.data.keyword.cloud_notm}}, che è altamente scalabile, aperto e dotato di misure complete di protezione. Con questo partenariato, le applicazioni basate su SAP NetWeaver possono espandersi ai principali mercati grazie a più di 60 data center {{site.data.keyword.IBM_notm}} distribuiti globalmente.

L'offerta presenta {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} con quattro opzioni di memoria:
  * 32 GB a singolo socket
  * 128 GB a doppio socket
  * 256 GB a doppio socket
  * 512 GB a doppio socket

Tutte e quattro le opzioni sono certificate per SAP NetWeaver e possono fornire una piattaforma cloud aziendale globale, aperta, scalabile e completa di ogni misura di sicurezza per distribuire rapidamente applicazioni SAP.

Puoi utilizzare i tuoi server per ambienti di produzione, non di produzione o PoC (proof-of-concept) Tutti i prodotti basati su ABAP di SAP NetWeaver Application Server e tutti i prodotti basati su Java di SAP NetWeaver Application Server sono supportati su {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}. Per tutti gli altri componenti software, prodotti SAP non basati su SAP NetWeaver o prodotti di terze parti, contatta il [supporto SAP](https://support.sap.com/home.html) se i prodotti sono supportati nell'ambito delle offerte IaaS.

## Modello di offerta {{site.data.keyword.cloud_notm}} per SAP NetWeaver
{: #offer_model}

L'offerta {{site.data.keyword.cloud_notm}} for SAP Applications è ideale praticamente per tutti gli scenari supportati da casi d'uso di SAP NetWeaver su {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} nella rete {{site.data.keyword.cloud_notm}}.

L'offerta consiste nei seguenti server, sistemi operativi e database:
  * {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} in quattro dimensioni e il software fornito con ciascun server.
      * 4 core con 32 GB di RAM
      * 24 core con 128 GB di RAM
      * 24 core con 256 GB di RAM
      * 28 core con 512 GB di RAM
      
  * Sistema operativo o hypervisor
      * VMware vSphere ESXi 6.0 o 6.5 sul tuo server
      * RHEL (Red Hat Enterprise Linux) per SAP Business Applications 6.X OS [SAP BW (SAP Business Warehouse) è supportato in produzione su {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}]
      * Microsoft Windows Server (vedi la [nota SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) per i dettagli della versione)
      
  * I database offerti sono
      * Microsoft SQL Server per Windows (vedi la [nota SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) per i dettagli della versione)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} per Linux (vedi la [nota SAP 101809](https://launchpad.support.sap.com/#/notes/101809) relativa alle versioni supportate e ai livelli di fix pack)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} per Windows (vedi la [nota SAP 101809-DB6](https://launchpad.support.sap.com/#/notes/101809) relativa alle versioni supportate e ai livelli di fix pack)
      
I {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} distribuiti con VMware ESXi possono eseguire le versioni elencate dei prodotti software basati su SAP NetWeaver, quelli dei database a cui si fa riferimento e RHEL e Windows. I server non possono eseguire nessun altro sistema operativo o prodotto SAP non basato su SAP NetWeaver.

Consultare [SAP HANA su {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/doc/infrastructure/sap-hana/hana-index.html#getting-started) per informazioni sulla distribuzione di SAP HANA. Le versioni future dell'offerta {{site.data.keyword.cloud_notm}} for SAP Applications include il supporto per altri database, l'alta disponibilità e il ripristino di emergenza.

Consulta la [PAM (Product Availability Matrix) di SAP](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630) per gli specifici requisiti di database, sistema operativo e SAP NetWeaver per {{site.data.keyword.cloud_notm}}. Per accedere alla PAM di SAP è necessario un ID S-user di SAP.

## Rete {{site.data.keyword.cloud_notm}}
{: #ibm_cloud_network}

{{site.data.keyword.cloud_notm}} fornisce più di 2.000 GB di connettività distribuita in una presenza globale di più di 60 data center {{site.data.keyword.cloud_notm}} e 28 PoP (Point of Presence). {{site.data.keyword.cloud_notm}} ha delle connessioni di rete a 20 Gbps nell'ambito delle sue ubicazioni. Queste connessioni sono fornite da provider di reti globali leader nel settore e includono molteplici link di peering pubblici a dozzine di ulteriori reti di accesso a Internet.

La rete si articola in tre architetture di rete nell'ordine dei gigabit distinte e ridondanti - pubblica, privata e da data center a data center - integrate perfettamente nella prima topologia del settore di rete all'interno di una rete. Questo design offre livelli massimi di accessibilità, sicurezza e controllo per la tua infrastruttura IT. Per ulteriori informazioni, consulta la pagina relativa alla [rete IBM Cloud](https://www.ibm.com/cloud-computing/bluemix/our-network).
