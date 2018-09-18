---



copyright:
  years: 2017, 2018
lastupdated: "2018-05-30"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# Informationen zu der von SAP zertifizierten IBM Cloud-Infrastruktur
{: #about_ibmcloud_for_sap}

Seit über 45 Jahren verbindet IBM und SAP in Bereichen wie Hardware, Software, Cloud, Services und Finanzen eine enge Partnerschaft, Teambildung und Zusammenarbeit. Die erste Zusammenarbeit reicht bis ins Jahr 1972 zurück und wächst seitdem stetig; mittlerweile verwenden hunderte von SAP-Kunden {{site.data.keyword.cloud}} als ihre IaaS-Lösung (IaaS, Infrastructure as a Service). {{site.data.keyword.IBM_notm}} optimiert dabei fortlaufend seine Cloudinfrastruktur-Produkte, die nun auch Unterstützung für die SAP NetWeaver-IT-Plattform bieten. 

Aufgrund dieser Beziehung und weiterer {{site.data.keyword.cloud_notm}}-Funktionen wurde {{site.data.keyword.IBM_notm}} als einer von SAPs wichtigsten strategischen Anbietern von Cloudinfrastrukturservices für geschäftskritische SAP-Anwendungen ausgewählt. Unterstützung für die Produktsuite von SAP NetWeaver ist über die hoch skalierbare, offene und extrem sichere {{site.data.keyword.cloud_notm}}-Lösung verfügbar. Dank mehr als 60 {{site.data.keyword.IBM_notm}} Rechenzentren können sich im Rahmen dieser Partnerschaft SAP NetWeaver-basierte Anwendungen weltweit auf den wichtigsten Märkten etablieren.

Das Angebot umfasst {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} mit acht Speicheroptionen:
  * Single-Socket 32 GB
  * Single-Socket 64 GB
  * Dual-Socket 128 GB
  * Dual-Socket 256 GB
  * Dual-Socket 512 GB
  * Dual-Socket 192 GB
  * Dual-Socket 384 GB
  * Dual-Socket 768 GB

Alle acht Optionen sind für SAP NetWeaver zertifiziert und bieten eine skalierbare, sichere, offene, globale Cloudplattform für Unternehmen für eine schnelle Bereitstellung von SAP-Anwendungen.

Sie können die Server für Produktionsumgebungen, Nicht-Produktionsumgebungen oder POC-Umgebungen (POC, Proof of Concept) verwenden. Alle ABAP-basierten und Java-basierten SAP NetWeaver Application Server-Produkte werden für {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} unterstützt. Für alle anderen Softwarekomponenten, SAP-Produkte, die nicht auf SAP NetWeaver basieren, oder Produkte anderer Anbieter wenden Sie sich an den [SAP-Support](https://support.sap.com/home.html), wenn die Produkte im Rahmen der IaaS-Angebote unterstützt werden.

## Angebotsmodell '{{site.data.keyword.cloud_notm}} for SAP NetWeaver'
{: #offer_model}

Das Angebot '{{site.data.keyword.cloud_notm}} for SAP Applications' ist ideal für nahezu alle SAP NetWeaver-Anwendungsfallszenarios für {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} über das {{site.data.keyword.cloud_notm}}-Netz.

Das Angebot umfasst die folgenden Server, Betriebssysteme und Datenbanken:
  * {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} ist in acht Größen mit der entsprechenden Software für die einzelnen Server verfügbar.
      * 4 Cores mit 32 GB RAM
      * 4 Cores mit 64 GB RAM
      * 24 Cores mit 128 GB RAM
      * 24 Cores mit 256 GB RAM
      * 28 Cores mit 512 GB RAM
      * 36 Cores mit 192 GB RAM
      * 36 Cores mit 384 GB RAM
      * 36 Cores mit 768 GB RAM
      
  * Betriebssystem oder Hypervisor
      * VMware vSphere ESXi 6.0 oder 6.5 auf dem Server
      * Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X OS [SAP Business Warehouse (SAP BW) wird in Produktionsumgebung für {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}] unterstützt
      * Microsoft Windows Server (siehe [SAP-Hinweis 2414097](https://launchpad.support.sap.com/#/notes/2414097) für Versionsdetails)
      
  * Angebotene Datenbanken
      * Microsoft SQL Server for Windows (siehe [SAP-Hinweis 2414097](https://launchpad.support.sap.com/#/notes/2414097) für Versionsdetails)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Linux (siehe [SAP-Hinweis 101809](https://launchpad.support.sap.com/#/notes/101809) für unterstützte Versionen und Fixpackstufen)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Windows (siehe [SAP Note 101809-DB6](https://launchpad.support.sap.com/#/notes/101809) für unterstützte Versionen und Fixpackstufen)
      
{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}-Instanzen, die mit VMware ESXi bereitgestellt werden, können die aufgeführten Versionen von RHEL und Windows, die referenzierten Datenbanken und die SAP NetWeaver-basierten Softwareprodukte ausführen. Auf den Servern können keine anderen Betriebssysteme oder SAP-Produkte, die nicht auf SAP NetWeaver basieren, ausgeführt werden.

Informationen zur Bereitstellung von SAP HANA finden Sie unter [SAP HANA for {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/infrastructure/sap-hana/hana-index.html#getting-started). Für zukünftige Versionen von {{site.data.keyword.cloud_notm}} for SAP Applications ist die Unterstützung für weitere Datenbanken, Hochverfügbarkeit und Disaster-Recovery geplant.

In der [SAP Product Availability Matrix (PAM)](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630) finden Sie die speziellen Anforderungen an Datenbanken, Betriebssystem und SAP NetWeaver für {{site.data.keyword.cloud_notm}}. Für den Zugriff auf SAP PAM ist eine S-User-ID von SAP erforderlich.

## {{site.data.keyword.cloud_notm}}-Netz
{: #ibm_cloud_network}

{{site.data.keyword.cloud_notm}} bietet mehr als 2.000 GB Konnektivität bei einer globalen Präsenz von mehr als 60 {{site.data.keyword.cloud_notm}}-Rechenzentren und 28 Bereitstellungspunkten. {{site.data.keyword.cloud_notm}} verfügt verteilt an allen Standorten über Netzverbindungen mit einer Geschwindigkeit von 20 Gb/s. Diese Verbindungen werden von führenden globalen Netzanbietern bereitgestellt und umfassen mehrere öffentliche Peering-Links zu Dutzenden zusätzlicher Internetzugangsnetzen.

Das Netz besteht aus drei verschiedenen und redundanten Gigabit-Netzarchitekturen (öffentlich, privat und Rechenzentrum-zu-Rechenzentrum), die nahtlos in die erste branchenspezifische Netzwerk-innerhalb-eines-Netzwerks-Topologie integriert sind. Dieses Design bietet ein Höchstmaß an Zugänglichkeit, Sicherheit und Steuerung für Ihre IT-Infrastruktur. Weitere Informationen finden Sie im Abschnitt [Das IBM Cloud-Netz](https://www.ibm.com/cloud-computing/bluemix/our-network).
