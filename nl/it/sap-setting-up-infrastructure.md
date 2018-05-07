---



copyright:
  years: 2017, 2018
lastupdated: "2010-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 2. Configurazione della tua infrastruttura
{: #set_up_infrastructure}

La seguente sezione contiene le indicazioni per configurare i tuoi {{site.data.keyword.baremetal_long}}, rete, sicurezza, archiviazione e sistema operativo di SAP NetWeaver. Per eventuali domande, rivolgiti al [supporto di {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support).

## Ordinazione del tuo server
{: order-server}

Per ordinare il tuo {{site.data.keyword.baremetal_short}}, attieniti alla seguente procedura. Ulteriori informazioni sono disponibili nel documento relativo alla [configurazione del tuo server bare metal](https://console.bluemix.net/docs/bare-metal/configuring.html#configuring-your-bare-metal-server).

1. Accedi al [Portale del cliente dell'infrastruttura {{site.data.keyword.cloud_notm}}](https://control.softlayer.com) utilizzando le tue credenziali univoche.
2. Fai clic sull'icona **Devices** nella pagina Account Summary.
3. Fai clic sul link **Monthly** sotto {{site.data.keyword.baremetal_short}} nella pagina Devices. Viene visualizzata la casella di dialogo Server List.
4. I server con certificazione SAP sono in cima all'elenco. Fai clic sul collegamento ipertestuale sotto **STARTING PRICE PER MONTH** per selezionare il server appropriato e andare alla pagina Configure/Order. 

   I server con certificazione SAP NetWeaver sono identificati con **-NW** sotto CPU Model. La configurazione server basata su Red Hat è descritta nel passo 7 e nel passo 1 in Selezione delle tue opzioni server; la procedura è la stessa per Microsoft Windows. Nota: per VMWare, la tua scelta è limitata; tuttavia, la procedura è la stessa.
   
5. Immetti il numero di server che stai ordinando nel campo **Quality** e seleziona il tuo **Data Center**.
6. **Server**, **RAM** e la tua opzione di archiviazione privata sono impostati su valori predefiniti in base alla tua selezione del server e non possono essere modificati. {{site.data.keyword.IBM_notm}} {{site.data.keyword.blockstorageshort}} per {{site.data.keyword.cloud_notm}} o {{site.data.keyword.filestorage_full_notm}} e NAS (Network Attached Storage) vengono ordinati dopo che hai ordinato il tuo server.
7. Seleziona il tuo sistema operativo (**Operating System**) da Red Hat o Microsoft e seleziona lo specifico sistema operativo o hypervisor VMware per il tuo server.

## Selezione delle tue opzioni server
{: #select_options}

Nel passo successivo, selezionerai il tipo e il numero di dischi che vuoi aggiungere alla tua configurazione. Puoi anche selezionare delle opzioni differenti per i gruppi di archiviazione RAID (Redundant Array of Independent) e i layout di partizionamento sui gruppi di archiviazione RAID. Per ulteriori informazioni, consulta [About RAID](https://console.bluemix.net/docs/bare-metal/what-raid.html#about-raid) oppure il [supporto di {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support).

1. In **SAP Certified Servers**, effettua la tua selezione in base a come intendi utilizzare il tuo server. I dettagli relativi a ciascuna opzione sono disponibili in [Configurazione dei tuoi server bare metal](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers). Per ulteriori informazioni, puoi anche consultare il [Design Decision Tool](https://github.com/ibm-cloud-architecture/infrastructure-design-decision-tool) (scorri in basso fino allo strumento) oppure il [supporto di {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support).
2. Fai clic sul pulsante **Add to order** in fondo alla pagina.

## Impostazione delle configurazioni di sistema avanzate
{: #adv_config}

1. Attieniti alle linee guida di [Configurazione di sistema avanzata](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration) per un aiuto con i valori nella finestra **Advanced System Configuration**.

I nomi SAP devono essere formati da un massimo di 13 caratteri alfanumerici. Consulta le [note SAP 611361](https://launchpad.support.sap.com/#/611361) e [129997](https://launchpad.support.sap.com/#/129997) per ulteriori dettagli sui nomi host SAP. 

Se hai deciso in merito a una configurazione pubblica/privata per il tuo ambiente e intendi
  * Installare più sistemi SAP che devono comunicare tra di loro *oppure*
  * Scegliere una configurazione SAP a tre livelli (istanze database e applicazione su hardware differente)
  
assicurati che la tua risoluzione dei nomi rifletta gli indirizzi interni ed esterni. L'indirizzo esterno corrisponde al nome host del server risolto in base al suo nome dominio completo (FDQN, fully-qualified domain name). 

Gli indirizzi interni non appariranno nel DNS (domain name system). Poiché si devono utilizzare gli IP interni per le comunicazioni tra i server, assicurati di estendere il tuo file `/etc/hosts` oppure "host" di Microsoft Windows ci conseguenza. Queste informazioni possono essere valide anche per il sistema operativo guest delle tue distribuzioni basate su VMware ESXi.

## Conferma delle tue selezioni
{: #confirm_selections}

1. Conferma le tue selezioni nella pagina Checkout e fai clic sulle caselle di spunta **Cloud Service terms** e **3rd Party Software Agreement**.
2. Scorri verso il basso fino a Create Account; accedi a Billing e immetti i valori per **Payment Type, Name, Card** e **Expiration** (data) per la carta di credito da utilizzare per la fatturazione.
3. Fai clic sul pulsante **Submit Order**. Vieni reindirizzato a una schermata con il tuo numero di ordine. Puoi stampare la schermata perché è anche la tua ricevuta dell'ordine.

Una email di conferma con l'oggetto Your _{{site.data.keyword.cloud_notm}} Order ## has been approved_ viene inviata all'indirizzo email nel tuo profilo. Questa email segnala che il tuo server è stato approvato ed è in fase di distribuzione. Dopo che è il server è stato distribuito, ti viene inviato un altro avviso che ti informa che il server è disponibile e che può essere gestito tramite il [Porta del cliente dell'infrastruttura {{site.data.keyword.cloud_notm}}](https://control.softlayer.com).

## Passi successivi

Sei ora pronto a iniziare a gestire il tuo {{site.data.keyword.baremetal_short}}. Vedi [Gestione del tuo landscape SAP NetWeaver](/docs/infrastructure/sap-netweaver/sap-manage-environment.html) per i tuoi passi successivi.
