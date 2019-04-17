---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, deployment, BYOL, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:note: .note}

# 2. Infrastruktur einrichten
{: #set_up_infrastructure}

Im folgenden Abschnitt finden Sie Anweisungen zum Einrichten der {{site.data.keyword.baremetal_long}}, des Netzes, der Sicherheit, des Speichers und des Betriebssystems für SAP NetWeaver. Bei Fragen wenden Sie sich an den [{{site.data.keyword.cloud_notm}}-Support](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support).

## Server bestellen
{: order-server}

Führen Sie die folgenden Schritte aus, um {{site.data.keyword.baremetal_short}} zu bestellen. Weitere Informationen finden Sie in [Bare-Metal-Server erstellen](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server#ordering-baremetal-server).

1. Melden Sie sich beim [Kundenportal für die {{site.data.keyword.cloud_notm}}-Infrastruktur ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com){: new_window} mit Ihren eindeutigen Berechtigungsnachweisen an. 
2. Klicken Sie auf **Konto** > **Bestellen** auf der Kontozusammenfassungsseite.
3. Klicken Sie auf der Seite 'Geräte' unter '{{site.data.keyword.baremetal_short}}' auf den Link **Monatlich**. Das Dialogfenster 'Serverliste' wird angezeigt. Die von SAP zertifizierten Server befinden sich ganz oben in der Liste. 
4. Klicken Sie unter **STARTPREIS PRO MONAT** auf den Hyperlink, um den entsprechenden Server auszuwählen und zur Konfigurations-/Bestellseite zu gelangen.

Der Server BI.S3.NW32 (Betriebssystemoptionen) ist auch für die Abrechnung **Stündlich** verfügbar.
{: note}

   SAP NetWeaver-zertifizierte Server sind unter 'CPU-Modell' durch **-NW** gekennzeichnet. Die Red Hat-basierte Serverkonfiguration ist in Schritt 7 und Schritt 1 unter [Serveroptionen auswählen](#select_options) beschrieben; diese Schritte gelten auch für Microsoft Windows. Beachten Sie, dass für VMWare die Auswahl zwar begrenzt ist, die Schritte jedoch gleich sind.

   Im Folgenden finden Sie ein Beispiel für die Entschlüsselung der SAP NetWeaver-Servernamen. 

| Servername  | Komponente der Namenskonvention | Bedeutung |
| --- | --- | --- |
| BI.S3.NW768 | BI | Bluemix Interface (Bluemix-Schnittstelle) |
| | S3 | Serie 2 (Prozessorgeneration) |
| | | S1 ist Ivy Bridge/Haswell |
| | | S2 ist Broadwell |
| | | S3 ist Skylake/Kaby Lake |
| | NW | NetWeaver-zertifizierter Server |
| | 768 | RAM-Größe |

5. Geben Sie die Anzahl der Server, die Sie bestellen, im Feld **Menge** ein und wählen Sie das **Rechenzentrum** aus.
6. Basierend auf Ihrer Serverauswahl nehmen die Werte für **Server**, **RAM** und die Option für privaten Speicher jeweils einen bestimmten Standardwert an und können nicht geändert werden. {{site.data.keyword.IBM_notm}} {{site.data.keyword.blockstorageshort}} for {{site.data.keyword.cloud_notm}} oder {{site.data.keyword.filestorage_full_notm}} werden nach der Bestellung des Servers bestellt. 
7. Wählen Sie Ihr **Betriebssystem** aus - Microsoft, Red Hat oder SUSE - und wählen Sie das spezifische Betriebssystem bzw. den VMware-Hypervisor für Ihren Server aus.

Wenn Sie eine eigene Lizenz für Ihr Betriebssystem verwenden (BYOL, Bring Your Own License), wählen Sie **Sonstige** > **Kein Betriebssystem** aus. Weitere Informationen finden Sie in [BYOL (Bring Your Own License)](#byol).
{: note}

## Serveroptionen auswählen
{: #select_options}

Im nächsten Schritt wählen Sie den Typ und die Anzahl der Platten für Ihre Konfiguration aus. Sie können auch verschiedene Optionen für RAID-Speichergruppen (RAID, Redundant Array of Independent Disks) und Partitionslayouts für diese Gruppen auswählen. Weitere Informationen erhalten Sie unter [Informationen zu RAID](/docs/bare-metal?topic=bare-metal-about-raid#about-raid) oder vom [{{site.data.keyword.cloud_notm}}-Support](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support).

1. Treffen Sie unter **Von SAP zertifizierte Server** basierend auf der geplanten Verwendung des Servers Ihre Auswahl. Weitere Informationen erhalten Sie auch über das [Tool für Designentscheidungen ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/ibm-cloud-architecture/infrastructure-design-decision-tool){: new_window} (blättern Sie abwärts bis zu dem Tool) oder den [{{site.data.keyword.cloud_notm}}-Support](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support). 
2. Klicken Sie unten auf der Seite auf **Zur Bestellung hinzufügen**.

## Erweiterte Systemkonfigurationen einrichten
{: #adv_config}

1. Befolgen Sie die Anweisungen unter [Erweitere Systemkonfiguration](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server#ordering-baremetal-server) als Richtlinie für die Werte im Fenster **Erweiterte Systemkonfiguration**.

SAP-Hostnamen müssen aus mindestens 13 alphanumerischen Zeichen bestehen. Weitere Details zu SAP-Hostnamen finden Sie in den [SAP Notes 611361 ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://launchpad.support.sap.com/#/611361){: new_window} und [129997 ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://launchpad.support.sap.com/#/129997){: new_window}. 

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

Es wird eine Bestätigungs-E-Mail mit dem Betreff 'Ihre _{{site.data.keyword.cloud_notm}}-Bestellung ## wurde genehmigt_' an die E-Mail-Adresse in Ihrem Profil gesendet. Diese E-Mail ist eine Benachrichtigung darüber, dass Ihr Server genehmigt wurde und demnächst bereitgestellt wird. Nach der Bereitstellung erhalten Sie eine weitere Benachrichtigung darüber, dass der Server verfügbar ist und über das [Kundenportal für die {{site.data.keyword.cloud_notm}}-Infrastruktur ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com){: new_window} verwaltet werden kann. 

## Bring your own license (BYOL)
{: #byol}

Wenn Sie über eine eigene Betriebssystemlizenz verfügen, installieren Sie sie auf dem {{site.data.keyword.baremetal_short}} anhand der Herstelleranweisungen. Weitere Informationen finden Sie in [Option 'Kein Betriebssystem'](/docs/bare-metal?topic=bare-metal-bm-no-os#bm-no-os).

## Nächste Schritte

Sie können nun mit der Verwaltung der {{site.data.keyword.baremetal_short}}-Instanzen beginnen. Informationen zu diesen nächsten Schritten finden Sie unter [SAP NetWeaver-Umgebung verwalten](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-manage_environment#manage_environment).
