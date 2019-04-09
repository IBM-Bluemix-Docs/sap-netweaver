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

# Häufig gestellte Fragen: SAP on IBM Cloud
{: #faqs}

## Benötige ich DB2 zum Ausführen von SAP NetWeaver on {{site.data.keyword.cloud_notm}}?
{: faq}

Überprüfen Sie [SAP Note 2414097 ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} regelmäßig und beachten Sie auch die [SAP Product Availability Matrix ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: new_window}. Bei der SAP Note ist es wichtig, welches Betriebssystem bereitgestellt wurde, da für Ihre Datenbank verschiedene Sets von Service-Packs erforderlich sind. 

## Warum wurde {{site.data.keyword.Db2_on_Cloud_short}} für die Zertifizierung für {{site.data.keyword.cloud_notm}} ausgewählt?
{: faq}

Da es sich bei {{site.data.keyword.Db2_on_Cloud_long_notm}} um ein {{site.data.keyword.IBM_notm}} Produkt handelt und {{site.data.keyword.cloud_notm}} eine Komponente von {{site.data.keyword.IBM_notm}} ist, wurde es für die Zertifizierung ausgewählt.

## Kann ich meine verteilte SAP-Umgebung zwischen verschiedenen Rechenzentren aufteilen?
{: faq}

Bei einer verteilten SAP-Installation ist es am besten, wenn sich alle Knoten im selben Rechenzentrum und VLAN-Segment befinden. Abweichungen hiervon können Latenz und Zeitlimitüberschreitungen hevorrufen, was wiederum dazu führen kann, dass Ihre SAP-Systeme nicht reagieren.

## Kann ich die durch die SAP-Architektur definierte Hochverfügbarkeit von SAP erreichen?
{: faq}

Die einzige unterstützte Hochverfügbarkeitsarchitektur ist die Skalierung von Anwendungsservern. Aktuell ist keine Hardware für die Unterstützung von Hochverfügbarkeit geeignet.

## Kann ich die SAP-Verteilungssoftware direkt aus {{site.data.keyword.cloud_notm}} herunterladen?
{: faq}

Zurzeit bieten wir keine direkte Verbindung zu [SAP Service Marketplace ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://websmp201.sap-ag.de/){: new_window} an. Daher sollten Sie die Verteilungs-DVDs wie momentan für eine lokale Bereitstellung herunterladen.
