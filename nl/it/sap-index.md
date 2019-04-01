---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, SAP certified servers, SAP Certified, database,

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Esercitazione introduttiva
{: #getting-started}

{{site.data.keyword.IBM_notm}} e SAP collaborano da più di 40 anni in molteplici aree, tra cui hardware, software, cloud, servizi e finanza. Stanno ora collaborando per eseguire applicazioni basate su SAP NetWeaver su {{site.data.keyword.baremetal_long}}. L'offerta presenta quatto opzioni di memoria, singolo socket (32 GB) e doppio socket (128 GB, 256 GB e 512 GB). Queste opzioni di memoria sono tutte disponibili nei più di 60 data center {{site.data.keyword.cloud_notm}} in tutto il mondo.
{: shortdesc}

Questo contenuto ti fornisce i consigli per il provisioning e l'installazione dell'infrastruttura per supportare i prodotti SAP basati su SAP NetWeaver e la sottoscrizione su {{site.data.keyword.cloud_notm}}. Non sostituisce alcuna documentazione correlata all'implementazione di SAP NetWeaver. Il suo scopo è quello di aiutarti con la pianificazione e il provisioning dell'infrastruttura in modo che tu possa iniziare la tua installazione SAP. L'installazione SAP (compresa l'installazione del database) non è diversa dalle installazioni per gli ambienti in loco. I consigli e le linee guida vengono forniti per aiutarti a utilizzare il tuo sistema SAP nell'ambiente {{site.data.keyword.cloud_notm}}.

La Tabella 1 contiene la procedura per aiutarti a mettere rapidamente a punto la tua infrastruttura {{site.data.keyword.cloud_notm}}.
<table>
   <CAPTION>Tabella 1. Passi di introduzione rapida</CAPTION>
   <THEAD>
   <TR>
   <th>Attività</th>
   <th>Dettagli</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>1. Leggi il contenuto IBM Cloud e SAP correlato alla tua implementazione</td>
   <td>Se la tua organizzazione non ha esperienza pregressa con IBM Cloud, leggi le seguenti informazioni prima della tua fase di pianificazione.
   <li><a href="https://ibm.com/cloud-computing/">Che cos'è IBM Cloud</a></li>
   <li><a href="https://ibm.com/cloud/get-started">Introduzione a IBM Cloud</a></li>
   <li><a href="https://help.sap.com/nw75#section2">Informazioni sull'installazione e sull'upgrade di SAP NetWeaver 7.5</a>: scarica la guida all'installazione</li>

   Potresti trovare utile anche la seguente documentazione di SAP:
   <li><a href="https://www.youtube.com/watch?v=4wICiRTP8u0/">Come creare un ID S-user SAP</a>. Tieni presente che solo gli amministratori con privilegi avanzati o S-user con l'autorizzazione richiesta possono creare ID S-user.</li>
   <li><a href="https://help.sap.com/netweaver">Guida di SAP NetWeaver</a></li>
   <li><a href="https://support.sap.com">Note SAP tramite il SAP Support Portal</a>; richiede un ID S-user SAP</li>
   </td>
   <tr>
   <td>2. Registrati per IBM Cloud</td>
   <td>Consulta <a href="https://cloud.ibm.com/docs/account/adminpublic.html#signing-up-for-ibm-cloud">Signing up for IBM Cloud</a> per la procedura su come configurare il tuo account IBM Cloud.</td>
 <tr>
   <td>3. Accedi al Portale del cliente dell'infrastruttura IBM Cloud</td>
   <td>Il <a href="https://control.softlayer.com">Portale del cliente dell'infrastruttura IBM Cloud</a> è il gateway grafico a tutti i tuoi componenti dell'infrastruttura: calcolo, connettività, archiviazione, rete e data center. Per accedere al Portale del cliente ti servono un <a href="https://console.bluemix.net/docs/customer-portal/getting-started.html#getting-started">ID IBM e password</a>.</td>
   <tr>
   <td>4. Pianifica il tuo landscape di sistema</td>
   <td>Utilizza le informazioni contenute in <a href="sap-netweaver?topic=sap-netweaver-planning-your-system-landscape#planning-your-system-landscape">Pianificazione del tuo landscape di sistema</a> per eseguire la progettazione, il dimensionamento e il provisioning del tuo ambiente IBM Cloud per supportare il tuo carico di lavoro SAP NetWeaver.</td>  
 <tr>
   <td>5. Esegui il provisioning del tuo sistema</td>
   <td>Utilizza la procedura e le informazioni in <a href="sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment">Provisioning del tuo ambiente SAP NetWeaver</a> per configurare la tua infrastruttura IBM Cloud. Puoi anche utilizzare la procedura indicata nelle guide di riferimento rapido.</td>
   <tr>
   <td>6. Installa SAP NetWeaver</td>
   <td>Installa SAP NetWeaver nella tua infrastruttura IBM Cloud come faresti se i server fossero in loco. Per ulteriori informazioni sull'installazione di SAP NetWeaver, vedi <a href="sap-netweaver?topic=sap-netweaver-install_sap#install_sap">Download e installazione di software e applicazioni SAP</a>.</td>
   </td>
   </tr>
   </TBODY>
   </table>
