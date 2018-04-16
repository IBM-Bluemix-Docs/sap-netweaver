---



copyright:
  years: 2017, 2018
lastupdated: "2018-01-25"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# IaaS für SAP NetWeaver on IBM Cloud - Übersicht
Eine IaaS-Umgebung (IaaS, Infrastructure-as-a-Server) setzt sich aus vielen Komponenten zusammen: Rechenzentrum, Berechnung, Konnektivität, Speicher und Netz. 

## Rechenzentren

Über Rechenzentren in Nord- und Südamerika, Europa, Asien und Australien können Sie Cloudressourcen überall (und jederzeit) bereitstellen. Jedes Rechenzentrum ist mit dem globalen privaten {{site.data.keyword.cloud_notm}}-Netz verbunden, wodurch Datenübertragungen weltweit schneller und effizienter werden.

Weitere Informationen zu den {{site.data.keyword.cloud_notm}}-Rechenzentren und Bereitstellungspunkten finden Sie unter [Rechenzentren](https://www.ibm.com/cloud-computing/bluemix/data-centers){: new_window}.

## Bare-Metal-Server

{{site.data.keyword.baremetal_long}}-Instanzen sind physische Server mit begrenzten Anpassungsfunktionen. Die Server sind speziell auf Ihre Bedürfnisse (oder die Ihres Kunden) zugeschnitten und werden nicht, einschließlich der Serverressourcen, mit anderen {{site.data.keyword.cloud_notm}}-Kunden gemeinsam genutzt. Diese Server werden von Ihnen oder Ihren Kunden verwaltet und ohne Hypervisor bereitgestellt.

Da die Anpassungsmöglichkeiten bei Bare-Metal-Servern begrenzt sind, können schnellere Bereitstellungszeiten zwischen 1 bis 4 Stunden erreicht werden. Eine schnelle Bereitstellung ist hilfreich, wenn Sie versuchen, eine App vor der Konkurrenz auf den Markt zu bringen.

Es stehen eine Reihe von RAM- und CPU-Kombinationen zur Auswahl, da die von SAP zertifizierten Server einen vordefinierten Umfang an RAM und eine bestimmte Anzahl von CPUs aufweist. Die Kombination kann *nicht* während des Bestellprozesses oder nach der Bereitstellung der Server durch ein Support-Ticket geändert werden.

Wenn für Ihr Projekt eine Virtualisierungsebene erforderlich ist, können Sie im Rahmen des SAP NetWeaver-Angebots {{site.data.keyword.baremetal_short}} bestellen, die mit VMware ESXi bereitgestellt werden. Die ESX-Instanz kann vollständig von Ihnen gesteuert werden, da sie ihn Ihrem Rechenzentrum bereitgestellt wird. Das System ist hinsichtlich des Netzbetriebs vollständig konfiguriert (jegliche weitere Konfiguration, wie das Festlegen von Speicher, muss von Ihnen vorgenommen werden). Es wird dringend empfohlen, dass eine Person mit Kenntnissen zur ESX-Verwaltung an Ihrem Projekt mitarbeitet, um dieses erfolgreich zu starten.

Weitere Inforationen zu Bare-Metal-Servern finden Sie unter [Informationen zu Bare-Metal-Servern](https://console.bluemix.net/docs/bare-metal/index.html#about-bare-metal-servers). 

## Betriebssysteme

Im [SAP-Hinweis 2414097](https://launchpad.support.sap.com/#/notes/2414097){: new window} finden Sie eine Liste der Betriebssysteme für die Bereitstellung von SAP NetWeaver-basierten Systemen. Für den Zugriff auf den SAP-Hinweis ist eine S-User-ID von SAP erforderlich. Die Lizenzierung für das Gastbetriebssystem wird von Ihnen abgedeckt.

## Netzkonnektivität

VPN-Konnektivität (VPN, Virtual Private Network) zum VCN-Netz (VCN, Virtual Cloud Network) von {{site.data.keyword.cloud_notm}} Virtual Cloud Network wird beim Einrichten des {{site.data.keyword.cloud_notm}}-Kontos automatisch eingeräumt. Standardmäßig verfügt der Server über eine öffentliche und eine private IP-Adresse. Soll der Server nicht öffentlich zugänglich sein, können Sie entweder die öffentliche Schnittstelle nach der Bereitstellung des Servers inaktivieren oder den Server als privaten Server bestellen. Weitere Informationen zum {{site.data.keyword.cloud_notm}}-VPN finden Sie unter [Einführung in Virtual Private Network](https://console.bluemix.net/docs/infrastructure/iaas-vpn/getting-started.html#getting-started-with-virtual-private-networking-vpn-).

## Speicher
{: #storage}

Lokaler Speicher wird mit {{site.data.keyword.baremetal_short}} bereitgestellt und verwendet das VLAN des privaten {{site.data.keyword.cloud_notm}}-Netzes für die Implementierung von auf das Unternehmen abgestimmte Sicherheitsmechanismen, ohne dabei den Zugriff von Administratoren zu behindern. Dies ist ideal für speicherintensive Anwendungen mit hohen Anforderungen an Ein-/Ausgabe, wie ein Betriebssystem und Datenbank- und Anwendungssoftware. Der Festplattenspeicher eines SAP NetWeaver-Servers hängt davon ab, wie der Server konfiguriert ist. Wenden Sie sich für Erweiterungsoptionen an den [{{site.data.keyword.cloud_notm}}-Support](https://console.bluemix.net/docs/support/index.html#getting-customer-support), wenn der lokale Speicher des Servers für Ihre Arbeitslasten nicht ausreicht.

Bei {{site.data.keyword.cloud_notm}} stehen zwei Speichertypen zur Auswahl, die Sie zum Durchführen von Backups und Wiederherstellungen für NetWeaver verwenden können: Blockspeicher und Dateispeicher. Beide Typen verwenden E/A-Operationen pro Sekunde (IOPS) zum Erfassen der Speicheranforderungen. IOPS werden basierend auf einer Blockgröße von 16 KB mit einer Kombination aus 50/50 Lese-/Schreiboperationen gemessen. Um für einen Datenträger einen maximalen Wert für IOPS zu erreichen, müssen geeignete Netzressourcen implementiert sein. Zu den weiteren Aspekten, die berücksichtigt werden müssen, zählen die private Netzauslastung außerhalb des Speichers und hostseitig und anwendungsspezifische Optimierungen (z. B. IP-Stacks und Warteschlangenlängen). Weitere Informationen zu Speichertiers und Leistung finden Sie unter [Einführung in Blockspeicher](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) und [Einführung in Dateispeicher](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage).

{{site.data.keyword.cloud_notm}} bietet auch Network Attached Storage (NAS), wenn Sie nach einer schnellen und kosteneffizienten Backuplösung für Ihre Geräte suchen. NAS ist mit folgenden Programmen und Lösungen kompatibel:
  * Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X OS
  * File Transfer Protocol (FTP) mit Parallels Plesk Panel und cPanel@WHM
  * Microsoft Windows Server über Windows-Standardverfahren unter Verwendung des CIFS-Protokolls (CIFS, Common Internet File System
  
NAS- und FTP-Speicher werden monatlich in Rechnung gestellt und sind in verschiedenen Speichergrößen verfügbar. Die Interaktion mit dem NAS- und FTP-Speicher ist primär über die Befehlszeile oder den Terminal unter dem Betriebssystem oder über Point-and-click-Interaktionen in den Anzeigen des Kundenportals der {{site.data.keyword.cloud_notm}}-Infrastruktur möglich.

Weitere Informationen zu NAS in einer {{site.data.keyword.cloud_notm}}-Umgebung finden Sie unter [Einführung in NAS](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#getting-started-with-nas).

## Bereitstellung und Management

{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} sind über das Kundenportal oder die API der {{site.data.keyword.cloud_notm}}-Infrastruktur verfügbar, sobald Sie Ihr {{site.data.keyword.cloud_notm}}-Kundenkonto erstellt haben. Die Server können über das Kundenportal, die API oder die Befehlszeilenschnittstelle (CLI) verwaltet werden. Weitere Informationen hierzu finden Sie unter [Informationen zu Bare-Metal-Servern](https://console.bluemix.net/docs/bare-metal/index.html#about-bare-metal-servers).

## Support

Der [{{site.data.keyword.cloud_notm}}-Kundendienst](https://console.bluemix.net/docs/support/index.html#getting-customer-support) beschäftigt sich mit allen Supportfragen und möglichen Problemen über eine Vielzahl von Kanälen, darunter Chat, Telefon und ticketbasierter Support. Dieser Service ist für alle {{site.data.keyword.cloud_notm}}-Kunden kostenlos und deckt die meisten Tickets ab, die täglich geöffnet werden. Weitere Informationen finden Sie unter [Kundenunterstützung anfordern](https://console.bluemix.net./docs/support/index.html#getting-customer-support).
