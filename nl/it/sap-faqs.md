---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.Db2_on_Cloud_short}}, FAQs, VLAN, application server, SAP Certified, high availability, highly available

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Domande frequenti: SAP su IBM Cloud
{: #faqs}

## Mi serve DB2 per eseguire SAP NetWeaver su {{site.data.keyword.cloud_notm}}?
{: faq}

Vedi la [nota SAP 2414097 ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} regolarmente e fai anche riferimento alla [SAP Product Availability Matrix (PAM) ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: new_window}. Tieni presente il sistema operativo fornito nella nota SAP poiché il tuo database ha bisogno di serie differenti di service pack.

## Perché è stato scelto {{site.data.keyword.Db2_on_Cloud_short}} per la certificazione per {{site.data.keyword.cloud_notm}}?
{: faq}

È stato scelto per la nostra certificazione poiché {{site.data.keyword.Db2_on_Cloud_long_notm}} è un prodotto {{site.data.keyword.IBM_notm}} e {{site.data.keyword.cloud_notm}} fa parte di {{site.data.keyword.IBM_notm}}.

## Posso suddividere il mio ambiente SAP distribuito tra diversi data center?
{: faq}

Per un'installazione SAP distribuita, è meglio avere tutti i nodi nello stesso data center e nello stesso segmento della VLAN. Configurazioni di altro tipo possono produrre latenza e condizioni di timeout a causa dei quali il tuo sistema SAP smetterebbe di rispondere.

## Posso raggiungere l'alta disponibilità come definito dall'architettura SAP?
{: faq}

La sola architettura di alta disponibilità supportata è il ridimensionamento dei server delle applicazioni. Attualmente, non c'è alcun hardware abilitato per il supporto dell'alta disponibilità.

## Posso scaricare il software di distribuzione SAP direttamente da {{site.data.keyword.cloud_notm}}?
{: faq}

Attualmente, non offriamo un collegamento diretto al [SAP Service Marketplace ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://websmp201.sap-ag.de/){: new_window}. Devi pertanto scaricare i DVD di distribuzione proprio come fai attualmente per una distribuzione in loco.
