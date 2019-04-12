---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, data centers, {{site.data.keyword.baremetal_short}}, deployment, VLANs, SAP Certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Panoramica dell'IaaS SAP NetWeaver su IBM Cloud
Un ambiente IaaS (Infrastructure-as-a-server) si articola in molti componenti: data center, elaborazione, connettività, archiviazione e rete.

## Data center

Con data center distribuiti in America del Nord e del Sud, Europa, Asia e Australia, puoi eseguire il provisioning di risorse cloud dove (e quando) ti servono. Ogni data center è connesso alla rete privata globale {{site.data.keyword.cloud_notm}}, rendendo i trasferimenti dati più veloci e più efficienti ovunque nel mondo.

Consulta la pagina relativa ai [Data Center ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/cloud-computing/bluemix/data-centers){: new_window} per ulteriori informazioni sui data center {{site.data.keyword.cloud_notm}} e i PoP (Point of Presence).

## Server bare metal

I {{site.data.keyword.baremetal_long}} sono server fisici con funzionalità di personalizzazione limitate. L'uso dei server è dedicato a te o al tuo cliente, e non ne viene condivisa alcuna parte, comprese le risorse server, con altri clienti {{site.data.keyword.cloud_notm}}. Tali server sono gestiti da te, o dal tuo cliente, e ne viene eseguito il provisioning senza un hypervisor.

Poiché la personalizzazione è limitata sui server bare metal, si possono ottenere dei tempi di provisioning più rapidi, che vanno da 1 a 4 ore. Un rapido provisioning è utile quando stai tentando di mettere in commercio un'applicazione prima della concorrenza.

Ti viene offerta una gamma di combinazioni di RAM e CPU poiché i server con certificazione SAP hanno una quantità di RAM e un numero di CPU preconfigurati. La combinazione *non può* essere modificata durante il processo di ordinazione o tramite un ticket di supporto dopo che i server sono stati distribuiti.

Se il tuo progetto richiede un livello di virtualizzazione, l'offerta SAP NetWeaver include l'opzione di ordinare {{site.data.keyword.baremetal_short}} di cui viene eseguita la distribuzione con VMware ESXi. L'istanza ESX è sotto il tuo pieno controllo, mentre viene distribuita nel tuo data center. Il sistema è totalmente configurato per quanto riguarda la rete (qualsiasi ulteriore configurazione, ad esempio l'archiviazione, dipende da te). Ti consigliamo vivamente di avere nel tuo staff qualcuno che comprenda l'amministrazione di ESX per avviare correttamente il tuo progetto.

Consulta [About bare metal servers](/docs/bare-metal?topic=bare-metal-about#about) per ulteriori informazioni sui server bare metal.

## Sistemi operativi

Devi consultare la [nota SAP 2414097 ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://launchpad.support.sap.com/#/notes/2414097){: new window} per un elenco dei sistemi operativi guest per la distribuzione di sistemi basati su SAP NetWeaver. Per accedere alla nota SAP è necessario un ID S-user di SAP. Dovrai occuparti tu della licenza per il sistema operativo guest.

## Connettività di rete

La connettività VPN (virtual private network) alla rete cloud virtuale {{site.data.keyword.cloud_notm}} viene concessa automaticamente quando viene configurato il tuo account {{site.data.keyword.cloud_notm}}. Per impostazione predefinita, il tuo server ha un indirizzo IP pubblico e uno privato. Se vuoi che il tuo server sia privato, puoi disattivare l'interfaccia pubblica dopo che è stato eseguito il provisioning del tuo server oppure ordinare il tuo server come privato. Consulta [Getting started with Virtual Private Networking](/docs/infrastructure/iaas-vpn?topic=VPN-gettingstarted-with-virtual-private-networking#gettingstarted-with-virtual-private-networking) per ulteriori informazioni sulla VPN {{site.data.keyword.cloud_notm}}.

## Archiviazione
{: #storage}

L'archiviazione locale viene fornita con il tuo {{site.data.keyword.baremetal_short}} e utilizza la VLAN (virtual LAN) di rete privata {{site.data.keyword.cloud_notm}} per aiutare a fornire una sicurezza di livello aziendale senza però ostacolare l'accesso dell'amministratore. È ideale per le applicazioni che utilizzano molta archiviazione e con elevate esigenze di I/O, come un sistema operativo, un database e del software applicativo. Lo spazio su disco del server SAP NetWeaver dipende da come è configurato il tuo server. Contatta il [supporto di {{site.data.keyword.cloud_notm}}](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) per le opzioni di estensione se l'archiviazione locale sul tuo server non è sufficiente per il tuo carico di lavoro.

Ci sono due tipi di archiviazione per {{site.data.keyword.cloud_notm}}, a blocchi e file, da cui scegliere per eseguire i backup e i ripristini per SAP NetWeaver. Entrambi i tipi utilizzano IOPS (input/output operations per second), di cui si fa uso per determinare le esigenze di archiviazione. La misurazione di IOPS è basata su una dimensione in blocchi da 16 KB con una combinazione 50/50 di letture e scritture. Per ottenere il massimo IOPS su un volume, devono essere implementate risorse di rete adeguate. Altre considerazioni includono l'utilizzo della rete privata esternamente al lato archiviazione e host e le regolazioni specifiche per le applicazioni (stack di IP e profondità di coda). Consulta il documento di [introduzione all'archiviazione a blocchi](/docs/infrastructure/BlockStorage?topic=BlockStorage-getting-started#getting-started) e quello di [introduzione all'archiviazione file](/docs/infrastructure/FileStorage?topic=FileStorage-getting-started#getting-started) per ulteriori informazioni sui livelli di archiviazione e sulle prestazioni.

## Distribuzione e gestione

I {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} sono distribuiti tramite l'API o il Portale del cliente dell'infrastruttura {{site.data.keyword.cloud_notm}} dopo che hai creato il tuo account cliente {{site.data.keyword.cloud_notm}}. I server possono essere gestiti tramite il Portale del cliente, l'API o l'interfaccia riga di comando (CLI, command-line interface). Ulteriori informazioni sono disponibili in [About bare metal servers](/docs/bare-metal?topic=bare-metal-about#about).

## Supporto

[Il supporto clienti di {{site.data.keyword.cloud_notm}}](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) gestisce qualsiasi domanda e problema di supporto che potrebbe presentarsi utilizzando una gamma di canali di comunicazione, tra cui chat, telefono e supporto basato sui ticket. Il supporto clienti è gratuito per tutti i clienti di {{site.data.keyword.cloud_notm}} e copre la maggior parte dei ticket inviati ogni giorno. Per ulteriori informazioni, consulta [Getting Customer Support](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support).
