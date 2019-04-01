---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, SAP landscape, SAP Business Suite, SAP Business Warehouse, SAP BW

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: .faq}

# Systemlandschaft planen
{: #planning-your-system-landscape}

Eine SAP-*Landschaft* ist eine Gruppe von zwei oder mehreren SAP-*Systemen*, die normalerweise die Bereiche Entwicklung, Qualität und Tests und Produktion abdecken. Ein SAP-System besteht aus einer oder mehreren *SAP-Instanzen*, bei denen es sich um eine Gruppe von Prozessen handelt, die gleichzeitig gestartet und gestoppt werden. Weitere Informationen zu SAP-Landschaften finden Sie in [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://lenovopress.com/redp5073.pdf){: new_window}.
{: shortdesc}

Es gibt für alle SAP-Lösungen auf dem Markt mehrere mögliche Landschaftskonfigurationen, darunter beispielsweise Server (Größe)/Speicher (Größe). Diese Lösungen umfassen SAP NetWeaver-basierte Produkte wie [SAP Business Suite ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://open.sap.com/courses/suitehana1){: new_window}, SAP Business Warehouse und alle spezifischen SAP-Add-ons, die von den Servern in der von SAP zertifizierten {{site.data.keyword.cloud}}-Infrastruktur unterstützt werden. Weitere Lösungen, die nicht zu vergessen sind, sind alle SAP-Lösungen, die nicht auf SAP NetWeaver basieren, und Software anderer Anbieter, die mit SAP integriert werden kann. Wenden Sie sich an den [SAP-Support ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://support.sap.com/en/index.html){: new_window}, wenn Sie nicht auf SAP NetWeaver basierende Software oder Software anderer Anbieter in Ihrer IaaS-Landschaft in {{site.data.keyword.cloud}} bereitstellen möchten. 

Sie müssen beim Festlegen der Größe des Servers die Anwendungen, die Sie ausführen möchten, das potenzielle Wachstum und die Leistung berücksichtigen. Beachten Sie zudem Ihren Speicherbedarf für die Anwendungen. SAP-Systeme in einer Landschaft haben bestimmte Anforderungen an die Konnektivität, entweder untereinander oder zu externen Systemen. Weitere Informationen finden Sie im Abschnitt [Zu berücksichtigende Aspekte bei der Planung der SAP-Landschaft](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations).

Tabelle 1 enthält die Schritte im Planungsprozess. Verwenden Sie diese Informationen zum Erstellen der SAP-Ziellandschaft.

Tabelle 1. Planungsprozess - Übersicht

| Schritt | Details |
| --- | --- |
| 1 | [SAP- und {{site.data.keyword.cloud_notm}}-Berechtigungsnachweise abrufen und Konten erstellen](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-get_sap_ibm_credentials#get_sap_ibm_credentials) |
| 2 | [Relevante SAP- und {{site.data.keyword.cloud_notm}}-Dokumentation zurate ziehen](/docs/infrastructure/sap-netweaver/sap-review-doc.html) |
| 3 | [SAP NetWeaver-Anwendungen festlegen](/docs/infrastructure/sap-netweaver/sap-determine-apps.html) |
| 4 | [Server dimensionieren](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server) |
| 5 | [Konfiguration festlegen](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration) |

## Nächste Schritte

Wählen Sie den entsprechenden Schritt in Tabelle 1 aus, um mit der Planung der SAP-Landschaft zu beginnen.
