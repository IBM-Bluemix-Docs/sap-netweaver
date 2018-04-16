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

# 2. Infrastruktur einrichten
{: #set_up_infrastructure}

Im folgenden Abschnitt finden Sie Anweisungen zum Einrichten der {{site.data.keyword.baremetal_long}}, des Netzes, der Sicherheit, des Speichers und des Betriebssystems für SAP NetWeaver. Bei Fragen wenden Sie sich an den [{{site.data.keyword.cloud_notm}}-Support](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support).

## Server bestellen
{: order-server}

Führen Sie die folgenden Schritte aus, um {{site.data.keyword.baremetal_short}} zu bestellen. Weitere Informationen finden Sie unter [Bare-Metal-Server konfigurieren](https://console.bluemix.net/docs/bare-metal/configuring.html#configuring-your-bare-metal-server).

1. Melden Sie sich beim [Kundenportal der {{site.data.keyword.cloud_notm}}-Infrastruktur](https://control.softlayer.com) mit Ihren eindeutigen Berechtigungsnachweisen an.
2. Klicken Sie auf der Seite mit der Kontozusammenfassung auf das Symbol **Geräte**.
3. Klicken Sie auf der Seite 'Geräte' unter '{{site.data.keyword.baremetal_short}}' auf den Link **Monatlich**. Das Dialogfeld 'Serverliste' wird angezeigt.
4. Die von SAP zertifizierten Server befinden sich ganz oben in der Liste. Klicken Sie unter **STARTPREIS PRO MONAT** auf den Hyperlink, um den entsprechenden Server auszuwählen und zur Konfigurations-/Bestellseite zu gelangen. 

   SAP NetWeaver-zertifizierte Server sind unter 'CPU-Modell' durch **-NW** gekennzeichnet. Die Konfiguration für Red Hat-basierte Server ist im Schritt 7 und Schritt 1 unter 'Serveroptionen auswählen' beschrieben; diese Schritte gelten auch für Microsoft Windows. Beachten Sie, dass für VMWare die Auswahl zwar begrenzt ist, die Schritte jedoch gleich sind.
   
5. Geben Sie die Anzahl der Server, die Sie bestellen, im Feld **Menge** ein und wählen Sie das **Rechenzentrum** aus.
6. Basierend auf Ihrer Serverauswahl nehmen die Werte für **Server**, **RAM** und die Option für privaten Speicher jeweils einen bestimmten Standardwert an und können nicht geändert werden. {{site.data.keyword.IBM_notm}} {{site.data.keyword.blockstorageshort}} for {{site.data.keyword.cloud_notm}} oder {{site.data.keyword.filestorage_full_notm}} und Network Attached Storage (NAS) werden nach dem Bestellen des Servers bestellt.
7. Wählen Sie als **Betriebssystem** entweder Red Hat oder Microsoft und das entsprechende Betriebssystem oder den VMware-Hypervisor für den Server aus.

## Serveroptionen auswählen
{: #select_options}

Im nächsten Schritt wählen Sie den Typ und die Anzahl der Platten für Ihre Konfiguration aus. Sie können auch verschiedene Optionen für RAID-Speichergruppen (RAID, Redundant Array of Independent Disks) und Partitionslayouts für diese Gruppen auswählen. Weitere Informationen erhalten Sie unter [Informationen zu RAID](https://console.bluemix.net/docs/bare-metal/what-raid.html#about-raid) oder vom [{{site.data.keyword.cloud_notm}}-Support](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support).

1. Treffen Sie unter **Von SAP zertifizierte Server** basierend auf der geplanten Verwendung des Servers Ihre Auswahl. Detaillierte Informationen zu den einzelnen Optionen finden Sie unter [Bare-Metal-Server einrichten](https://console.bluemix.net/docs/bare-metal/configuring.html#setting-up-your-bare-metal-servers). Weitere Unterstützung erhalten Sie über das [Design Decision Tool](https://github.com/ibm-cloud-architecture/infrastructure-design-decision-tool) (blättern Sie nach unten zu dem Tool) oder den [{{site.data.keyword.cloud_notm}}-Support](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support).
2. Klicken Sie unten auf der Seite auf **Zur Bestellung hinzufügen**.

## Erweiterte Systemkonfigurationen einrichten
{: #adv_config}

1. Befolgen Sie die Anweisungen unter [Erweitere Systemkonfiguration](https://console.bluemix.net/docs/bare-metal/configuring.html#advanced-system-configuration) als Richtlinie für die Werte im Fenster **Erweiterte Systemkonfiguration**.

SAP-Hostnamen müssen aus mindestens 13 alphanumerischen Zeichen bestehen. Weitere Informationen zu SAP-Hostnamen finden Sie in den [SAP-Hinweisen 611361](https://launchpad.support.sap.com/#/611361) und [129997](https://launchpad.support.sap.com/#/129997). 

Wenn Sie sich für ein öffentliches/privates Setup für die Umgebung entschieden haben und
  * mehrere SAP-Systeme installieren möchten, die miteinander kommunizieren müssen *oder*
  * ein dreischichtiges SAP-Setup wählen (Datenbank- und Anwendungsinstanzen auf unterschiedlicher Hardware)
  
stellen Sie sicher, dass die Namensauflösung die internen und externen Adressen widerspiegelt. Die externe Adresse entspricht dem Hostnamen der Servers, aufgelöst durch den vollständig qualifizierten Domänennamen (FQDN, Fully Qualified Domain Name). 

Die internen Adressen erscheinen nicht im Domain Name System (DNS). Da interne IPs für die Kommunikation zwischen den Servern verwendet werden sollten, stellen Sie sicher, dass Sie die Datei `/etc/hosts` oder entsprechend die Microsoft Windows-'host'-Datei erweitern. Diese Informationen können auch für das Gastbetriebssystem der VMware ESXi-basierten Bereitstellungen gelten.

## Auswahl bestätigen
{: #confirm_selections}

1. Bestätigen Sie Ihre Auswahl auf der Kassenseite und aktivieren Sie die Kontrollkästchen für **Bedingungen für den Cloud-Service** und **Vereinbarung zu Drittanbietersoftware**.
2. Blättern Sie nach unten zu 'Konto erstellen: Rechnungsdetails eingeben' und geben Sie **Zahlungsart, Name, Kartentyp** und das **Ablaufdatum** für die Kreditkarte an, die für die Rechnungsstellung verwendet werden soll.
3. Klicken Sie auf die Schaltfläche **Bestellung abschicken**. Sie werden an einen Bildschirm mit Ihrer Bestellnummer weitergeleitet. Sie können diese Information ausdrucken, da es sich hierbei auch um den Bestelleingang für Ihre Unterlagen handelt.

Es wird eine Bestätigungs-E-Mail mit dem Betreff 'Ihre _{{site.data.keyword.cloud_notm}}-Bestellung ## wurde genehmigt_' an die E-Mail-Adresse in Ihrem Profil gesendet. Diese E-Mail ist eine Benachrichtigung darüber, dass Ihr Server genehmigt wurde und demnächst bereitgestellt wird. Nach der Bereitstellung erhalten Sie eine weitere Benachrichtigung darüber, dass der Server verfügbar ist und über das [Kundenportal für die {{site.data.keyword.cloud_notm}}-Infrastruktur](https://control.softlayer.com) verwaltet werden kann.

## Nächste Schritte

Sie können nun mit der Verwaltung der {{site.data.keyword.baremetal_short}}-Instanzen beginnen. Informationen zu diesen nächsten Schritten finden Sie unter [SAP NetWeaver-Umgebung verwalten](/docs/infrastructure/sap-netweaver/sap-manage-environment.html).
