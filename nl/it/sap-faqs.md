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

# Domande frequenti: SAP su IBM Cloud
{: #faqs}

## Mi serve DB2 per eseguire SAP NetWeaver su {{site.data.keyword.cloud_notm}}?

Controlla regolarmente la [nota SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) e fai anche riferimento alla [PAM (Product Availability Matrix) di SAP](https://apps.support.sap.com/sap/support/pam). Tieni presente il sistema operativo fornito nella nota SAP poiché il tuo database ha bisogno di serie differenti di service pack.

## Perché è stato scelto {{site.data.keyword.Db2_on_Cloud_short}} per la certificazione per {{site.data.keyword.cloud_notm}}?

È stato scelto per la nostra certificazione poiché {{site.data.keyword.Db2_on_Cloud_long_notm}} è un prodotto {{site.data.keyword.IBM_notm}} e {{site.data.keyword.cloud_notm}} fa parte di {{site.data.keyword.IBM_notm}}.

## Posso suddividere il mio ambiente SAP distribuito tra diversi data center?

Per un'installazione SAP distribuita, è meglio avere tutti i nodi nello stesso data center e nello stesso segmento della VLAN. Configurazioni di altro tipo possono produrre latenza e condizioni di timeout a causa dei quali il tuo sistema SAP smetterebbe di rispondere.

## Posso raggiungere l'alta disponibilità come definito dall'architettura SAP?

La sola architettura di alta disponibilità supportata è il ridimensionamento dei server delle applicazioni. Attualmente, non c'è alcun hardware abilitato per il supporto dell'alta disponibilità.

## Posso scaricare il software di distribuzione SAP direttamente da {{site.data.keyword.cloud_notm}}?

Attualmente, non offriamo un collegamento diretto al [SAP Service Marketplace](https://websmp201.sap-ag.de/). Devi pertanto scaricare i DVD di distribuzione proprio come fai attualmente per una distribuzione in loco.
