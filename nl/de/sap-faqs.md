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

# Häufig gestellte Fragen: SAP on IBM Cloud
{: #faqs}

## Benötige ich DB2 zum Ausführen von SAP NetWeaver on {{site.data.keyword.cloud_notm}}?

Überprüfen Sie regelmäßig den [SAP-Hinweis 2414097](https://launchpad.support.sap.com/#/notes/2414097) und konsultieren Sie zudem die [SAP Product Availability Matrix](https://apps.support.sap.com/sap/support/pam). Beachten Sie das bereitgestellte Betriebssystem im SAP-Hinweis, da für Ihre Datenbank verschiedene Sets von Service-Packs erforderlich sind.

## Warum wurde {{site.data.keyword.Db2_on_Cloud_short}} für die Zertifizierung für {{site.data.keyword.cloud_notm}} ausgewählt?

Da es sich bei {{site.data.keyword.Db2_on_Cloud_long_notm}} um ein {{site.data.keyword.IBM_notm}} Produkt handelt und {{site.data.keyword.cloud_notm}} eine Komponente von {{site.data.keyword.IBM_notm}} ist, wurde es für die Zertifizierung ausgewählt.

## Kann ich meine verteilte SAP-Umgebung zwischen verschiedenen Rechenzentren aufteilen?

Bei einer verteilten SAP-Installation ist es am besten, wenn sich alle Knoten im selben Rechenzentrum und VLAN-Segment befinden. Abweichungen hiervon können Latenz und Zeitlimitüberschreitungen hevorrufen, was wiederum dazu führen kann, dass Ihre SAP-Systeme nicht reagieren.

## Kann ich die durch die SAP-Architektur definierte Hochverfügbarkeit von SAP erreichen?

Die einzige unterstützte Hochverfügbarkeitsarchitektur ist die Skalierung von Anwendungsservern. Aktuell ist keine Hardware für die Unterstützung von Hochverfügbarkeit geeignet.

## Kann ich die SAP-Verteilungssoftware direkt aus {{site.data.keyword.cloud_notm}} herunterladen?

Aktuell gibt es keine direkte Verbindung zum [SAP Service Marketplace](https://websmp201.sap-ag.de/). Daher sollten Sie die Verteilungs-DVDs wie momentan für eine lokale Bereitstellung herunterladen.
