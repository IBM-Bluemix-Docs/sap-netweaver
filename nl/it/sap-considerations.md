---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, network connectivity, VLANs, hybrid, STMS, SAProuter, SAP Solution Manager, SAP certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Elementi da considerare quando pianifichi il tuo landscape SAP
{: #considerations}

I sistemi SAP in un landscape hanno degli specifici requisiti per la connettività, tra di loro oppure a sistemi esterni. Devi anche pensare all'archiviazione esterna per il tuo landscape e cosa fare se decidi di distribuire VMware sul tuo server.

## Connettività di rete
{: #network_connectivity}

[Rete {{site.data.keyword.cloud_notm}}](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-ibm_cloud_network#ibm_cloud_network) ha fornito una panoramica dell'approccio {{site.data.keyword.cloud}} alla connettività di rete. I problemi con la connettività di rete possono causare dei notevoli ritardi per il tuo progetto, se la tua pianificazione non è appropriata, indipendentemente da come intendi utilizzare il tuo sistema.

In generale, abbiamo due scelte di interfaccia per i server {{site.data.keyword.cloud_notm}} con provisioning IaaS; il primo è un'interfaccia esterna con un IP pubblico. Il secondo è un'interfaccia interna che viene fornita con un “IP privato” in conformità a RFC (Request for Comment) 1918. Puoi anche scegliere una singola interfaccia interna con un “IP privato”. Entrambe le opzioni possono essere rese ridondanti mediante una "interfaccia di bonding" Linux o mediante un gruppo NIC (Network Interface Card) Windows e possono essere rese disponibili a una velocità di 100 Mb/s, 1 Gb/s e 10 Gb/s.

A seconda del tuo caso d'uso, un IP pubblico potrebbe essere accettabile per landscape PoC (proof-of-concept) perché l'IP esterno potrebbe essere più facile da usare. Esiste un potenziale rischio di sicurezza anche se è installato e preconfigurato un firewall di base. Se vuoi utilizzare un'interfaccia pubblica, assicurati di scegliere un valore sufficientemente alto per la **larghezza di banda pubblica** quando ordini il tuo server. Questo valore determina la quantità totale di dati che può essere trasferita attraverso l'interfaccia durante un periodo di un mese. Mentre il traffico delle normali comunicazioni di rete, della GUI (graphical user interface) SAP e di RFC (remote function call) SAP può tutto insieme arrivare a pochi megabyte al giorno, degli upload di dati di grandi dimensioni possono facilmente superare i 1.000 GB al mese. Devi conoscere la quantità di dati che viene trasferita almeno dell'ordine di magnitudine o passare alla seconda opzione.

La seconda opzione accede alla VPN (Virtual Private Network) {{site.data.keyword.cloud_notm}} tramite il Portale del cliente dell'infrastruttura {{site.data.keyword.cloud_notm}} oppure distribuisce un dispositivo di sicurezza nel tuo landscape. I dispositivi di sicurezza sono offerti per i firewall, la conversione degli indirizzi di rete, l'accesso VPN e altre funzioni di rete. Inoltre, questi dispositivi di sicurezza possono offrirti una larghezza di banda più elevata, che ti aiuta a trasferire quantità di dati più grandi in un data center {{site.data.keyword.cloud_notm}}. È consigliabile che il tuo reparto responsabile della rete parli con il [supporto di {{site.data.keyword.cloud_notm}}](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) dopo che sono stati determinati il tuo landscape e la connettività richiesta sul livello delle applicazioni SAP.

### VLAN
{: #vlans}

Se vuoi separare i diversi tipi di traffico di rete nel tuo landscape, puoi ordinare altre VLAN (virtual LAN). Tieni presente che le VLAN aggiuntive determinano solo una segregazione del traffico, non un aumento delle prestazioni. La segregazione del traffico deve essere presa in considerazione con elaborate distribuzioni basate su VMware, in cui tipi diversi di traffico di rete potrebbero richiedere una netta separazione per motivi di sicurezza.

Per i seguenti casi d'uso, assicurati che tutti i server siano sulla stessa VLAN durante la distribuzione.
  *	Più server scambiano dati, come ad esempio una configurazione SAP a tre livelli, con il database e le istanze delle applicazioni SAP su server differenti
  *	Più sistemi che scambiano grandi quantità di dati

Per una distribuzione SAP con l'archiviazione locale, anche per le configurazioni a tre livelli, delle reti a base di 1 Gb sono sufficienti. Potrebbe essere necessario valutare altri fattori; consulta [Archiviazione esterna](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations#external_storage) per ulteriori informazioni sulle tue scelte di archiviazione di rete.

### Configurazioni ibride
{: #hybrid}

Si può pensare all'offerta {{site.data.keyword.cloud_notm}} for SAP Applications come un data center esterno, soprattutto se stai pensando di implementare un landscape ibrido con qualche sistema SAP in un data center {{site.data.keyword.cloud_notm}} e altri sistemi in loco. Alcuni degli elementi di configurazione specifici che devono essere valutati come parte della fase di pianificazione del tuo progetto con una configurazione ibrida:

  *	[SAP Transport Management System (STMS) ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.sap.com/products/transportation-logistics.html){: new_window}. Configuralo in base ai gruppi di trasporto per evitare la condivisione di file tra i data center.
  *	[SAProuter ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://support.sap.com/en/tools/connectivity-tools/saprouter.html){: new_window}. Fornisce l'accesso a OSS (On-Line Service System) SAP. Utilizza il tuo SAProuter in loco, che è già disponibile, per accedere a OSS. Questo SAProuter può essere utilizzato tramite ulteriori passaggi (hop) SAProuter se l'instradamento basato su IP non è consentito tra i tuoi sistemi basati su {{site.data.keyword.cloud_notm}} e il tuo SAProuter in loco. In alternativa, puoi valutare la configurazione di un altro SAProuter basato su un server basato su {{site.data.keyword.cloud_notm}} con un IP pubblico e connetterlo al sistema OSS SAP tramite Internet.
  *	[SAP Solution Manager ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://support.sap.com/en/solution-manager.html){: new_window}. L'accesso a SAP Solution Manager ha requisiti di connettività differenti tra un SAP Solution Manager e i suoi sistemi gestiti, a seconda del tuo scenario di utilizzo. Questi scenari richiedono una comprensione della connettività di rete richiesta.  

## Archiviazione esterna
{: #external_storage}

L'archiviazione locale fornisce le prestazioni migliori per la tua distribuzione del database. Oltre all'archiviazione locale, potresti aver bisogno di ulteriore archiviazione esterna per eseguire dei backup, altrimenti il database dei tuoi sistemi SAP potrebbe superare la capacità di archiviazione dei dischi interni. Come altro esempio, i tuoi requisiti di progetto potrebbero richiedere l'archiviazione esterna, come per più server basati su ESX che vogliono condividere delle VM (virtual machine). Per questi requisiti, puoi ordinare l'archiviazione a blocchi o NAS (Network Attached Storage) come descritto in [Storage](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-storage#storage). Poiché l'archiviazione a blocchi supplementare e i dati NAS vengono trasferiti attraverso gli stessi adattatori fisici di tutto l'altro traffico di rete, bisogna tenere presente l'impatto. Dei numeri delle prestazioni paragonabili ai numeri misurati nei benchmark di certificazione potrebbero solo essere raggiungibili.

Ti consigliamo di scegliere un data center basato su 10 Gb per la tua distribuzione, se intendi utilizzare principalmente l'archiviazione esterna invece dell'archiviazione locale. Ad esempio, l'archiviazione esterna viene utilizzata sia per il backup che per il tuo database e intendi mettere un carico elevato sul tuo sistema SAP. Se sei prossimo a sovraccaricare una rete da 1 Gb con un carico I/O da 90 MB/s.

Un altro suggerimento è quello di utilizzare almeno 4 IOPS/GB se il tuo database risiede principalmente sull'archiviazione esterna. Un'archiviazione più lenta deve essere utilizzata solo se le prestazioni del database non sono critiche per il tuo progetto o per scopi di backup.

Se intendi utilizzare l'archiviazione esterna come archivi di dati per VMware ESX, attieniti alle linee guida relative alle decisioni in [Storage to use with VMware Systems](/docs/infrastructure/vmware?topic=VMware-storage-to-use-with-vmware-systems#storage-to-use-with-vmware-systems) per determinare il tipo di archiviazione ottimale per il tuo caso d'uso.

## Distribuzioni del server VMware ESXi
{: #vmware_server}

Le distribuzioni basate su VMware ESXi in {{site.data.keyword.cloud_notm}} sono diverse dalle altre distribuzioni basate sul cloud. {{site.data.keyword.cloud_notm}} non fornisce ai suoi clienti delle VM in esecuzione; tu prendi il controllo del tuo ambiente e lo configuri per soddisfare i tuoi requisiti. Quando ordini un server VMware ESX, ricevi un server configurato. I seguenti link forniscono informazioni sull'archiviazione aggiuntiva e l'esecuzione di VM guest.

  *	[Storage to use with VMware Systems](/docs/infrastructure/vmware?topic=VMware-storage-to-use-with-vmware-systems#storage-to-use-with-vmware-systems) fornisce ulteriori indicazioni su come integrare l'archiviazione in un ambiente ESX.
  * [Mounting iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mounting-iscsi-vmware-esxi#mounting-iscsi-vmware-esxi) descrive la procedura per integrare l'archiviazione basata su iSCSI con ESX.
  * [Creating a VMware ESX Virtual Machine](/docs/infrastructure/vmware?topic=VMware-creating-a-vmware-esx-virtual-machine#creating-a-vmware-esx-virtual-machine) ti guida attraverso il processo di distribuzione della tua prima VM.

Tieni presente che, per distribuire software basato su SAP NetWeaver nel sistema operativo guest, devi scegliere il sistema operativo guest dai sistemi operativi menzionati nella [nota SAP 2414097 ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}.
