---



copyright:
  years: 2017, 2018
lastupdated: "2018-01-23"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Systemlandschaft planen
{: #planning-your-system-landscape}

Eine SAP-*Landschaft* ist eine Gruppe von zwei oder mehreren SAP-*Systemen*, die normalerweise die Bereiche Entwicklung, Qualität und Tests und Produktion abdecken. Ein SAP-System besteht aus einer oder mehreren *SAP-Instanzen*, bei denen es sich um eine Gruppe von Prozessen handelt, die gleichzeitig gestartet und gestoppt werden. Weitere Informationen zu SAP-Landschaften finden Sie in der Veröffentlichung [*SAP Business Suite on IBM X6 Systems Reference Architecture*](https://lenovopress.com/redp5073.pdf).
{: shortdesc}

Es gibt für alle SAP-Lösungen auf dem Markt mehrere mögliche Landschaftskonfigurationen, darunter beispielsweise Server (Größe)/Speicher (Größe). Zu den Lösungen zählen SAP NetWeaver-basierte Produkte, wie [SAP Business Suite](https://open.sap.com/courses/suitehana1), SAP Business Warehouse und alle entsprechenden SAP-Add-ons, die die Server im Angebot '{{site.data.keyword.cloud}} for SAP Applications' unterstützen. Weitere Lösungen, die nicht zu vergessen sind, sind alle SAP-Lösungen, die nicht auf SAP NetWeaver basieren, und Software anderer Anbieter, die mit SAP integriert werden kann. Wenden Sie sich an den [SAP-Support](https://support.sap.com/en/index.html), falls Sie solche Lösungen und Software in Ihrer IaaS-Landschaft in {{site.data.keyword.cloud}} bereitstellen möchten.

Sie müssen beim Festlegen der Größe des Servers die Anwendungen, die Sie ausführen möchten, das potenzielle Wachstum und die Leistung berücksichtigen. Beachten Sie zudem Ihren Speicherbedarf für die Anwendungen. SAP-Systeme in einer Landschaft haben bestimmte Anforderungen an die Konnektivität, entweder untereinander oder zu externen Systemen. Weitere Informationen finden Sie im Abschnitt [Zu berücksichtigende Aspekte bei der Planung der SAP-Landschaft](/docs/infrastructure/sap-netweaver/sap-considerations.html).

Tabelle 1 enthält die Schritte im Planungsprozess. Verwenden Sie diese Informationen zum Erstellen der SAP-Ziellandschaft.

Tabelle 1. Planungsprozess - Übersicht

| Schritt | Details |
| --- | --- |
| 1 | [SAP- und {{site.data.keyword.cloud_notm}}-Berechtigungsnachweise abrufen und Konten erstellen](/docs/infrastructure/sap-netweaver/sap-get-credentials.html) |
| 2 | [Relevante SAP- und {{site.data.keyword.cloud_notm}}-Dokumentation zurate ziehen](/docs/infrastructure/sap-netweaver/sap-review-doc.html) |
| 3 | [SAP NetWeaver-Anwendungen festlegen](sap-determine-apps.html) |
| 4 | [Dimensionierung des Servers](/docs/infrastructure/sap-netweaver/sap-size-server.html) |
| 5 | [Konfiguration festlegen](/docs/infrastructure/sap-netweaver/sap-determine-configuration.html) |

## Nächste Schritte

Wählen Sie den entsprechenden Schritt in Tabelle 1 aus, um mit der Planung der SAP-Landschaft zu beginnen.

