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

# Zu berücksichtigende Aspekte bei der Planung der SAP-Landschaft
{: #considerations}

Die SAP-Systeme in einer Landschaft haben bestimmte Anforderungen an die Konnektivität, entweder untereinander oder zu externen Systemen. Außerdem müssen Sie externen Speicher für die Systemlandschaft in Betracht ziehen und über die möglichen Maßnahmen bei der Bereitstellung von VMware auf dem Server nachdenken.

## Netzkonnektivität
{: #network_connectivity}

Im Abschnitt zum[{{site.data.keyword.cloud_notm}}-Netz](/docs/infrastructure/sap-netweaver/sap-about.html#ibm_cloud_network) finden Sie eine Übersicht zum {{site.data.keyword.cloud}}-Ansatz für die Netzkonnektivität. Probleme mit der Netzkonnektivität können zu bedeutenden Verzögerungen bei Ihren Projekten führen, wenn Ihre Planung ungenau ist, ganz gleich, wie Sie Ihr System einsetzen möchten. 

Im Allgemeinen stehen Ihnen zwei Auswahlmöglichkeiten für Schnittstellen für die mit IaaS bereitgestellten {{site.data.keyword.cloud_notm}}-Server zur Verfügung. Die erste Möglichkeit ist eine externe Schnittstelle mit einer öffentlichen IP. Bei der zweiten Möglichkeit handelt es sich um eine interne Schnittstelle, die unter Einhaltung des Request for Comment (RFC) 1918 mit einer 'privaten IP' bereitgestellt wird. Sie können auch eine einzelne interne Schnittstelle mit einer 'privaten IP' auswählen. Beide Optionen können mit einer 'Bonding-Schnittstelle' unter Linux oder dem Einrichten des NIC-Teaming (NIC, Network Interface Card) unter Windows redundant gemacht werden; die Bereitstellung erfolgt mit einer Geschwindigkeit von 100 Mb/s, 1 Gb/s und 10 Gb/s.

Je nach Anwendungsfall kann eine öffentliche IP für PoC-Landschaften (Proof-of-Concept) passend sein, da die externe IP leichter zu verwenden sein kann. Es besteht jedoch trotz installierter und vorkonfigurierter Firewall ein potenzielles Sicherheitsrisiko. Wenn Sie eine öffentliche Schnittstelle verwenden möchten, stellen Sie sicher, dass Sie beim Bestellen des Servers einen ausreichend hohen Wert für die **öffentliche Bandbreite** auswählen. Mit diesem Wert wird das Gesamtdatenvolumen festgelegt, das während eines Zeitraums von einem Monat über die Schnittstelle übertragen werden kann. Während sich der Datenverkehr bei normaler Netzkommunikation, über die SAP-GUI oder SAP-RFC-Schnittstelle auf nur etwa wenige Megabyte pro Tag summiert, können umfangreiche Datenuploads leicht 1.000 GB pro Monat übersteigen. Sie müssen daher entweder in etwa die Größenordnung des zu übertragenden Datenvolumens kennen oder die zweite Option wählen.

Bei der zweiten Option erfolgt ein Zugriff auf das {{site.data.keyword.cloud_notm}} Virtual Private Network (VPN) über das Kundenportal der {{site.data.keyword.cloud_notm}}-Infrastruktur oder eine Bereitstellung einer Sicherheitskomponente in Ihrer Systemlandschaft. Solche Sicherheitskomponenten werden für Firewalls, Netzadresskonvertierung, VPN-Zugriff und weitere Netzfunktionen angeboten. Sie können eine höhere Bandbreite liefern, die Ihnen bei der Übertragung umfangreicher Datenvolumen an ein {{site.data.keyword.cloud_notm}}-Rechenzentrum helfen kann. Es empfiehlt sich, dass sich Ihre Networking-Abteilung an den [{{site.data.keyword.cloud_notm}}-Support](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support) wendet, sobald das Layout Ihrer Systemlandschaft und die erforderliche Konnektivität für die SAP-Anwendungsschicht festgelegt wurden.

### VLANs
{: #vlans}

Wenn Sie unterschiedlichen Typen von Netzverkehr in Ihrer Umgebung voneinander trennen möchten, können Sie mehr virtuelle LANs (VLANs) bestellen. Beachten Sie, dass die zusätzlichen VLANs nur für die Trennung des Datenverkehrs sorgen und nicht zu einer höheren Leistung führen. Die Trennung des Datenverkehrs sollte für umfangreiche VMware-basierte Bereitstellungen in Betracht gezogen werden, bei denen aus Sicherheitsgründen verschiedene Typen von Netzverkehr strenger getrennt werden müssen.

Bei den folgenden Anwendungsfällen sollten Sie sicherstellen, dass sich während der Bereitstellung alle Server im selben VLAN befinden:
  *	Mehrere Server, die Daten austauschen, wie eine Datenbank in einem dreischichtigen SAP-Setup und SAP-Anwendungsinstanzen auf verschiedenen Servern
  *	Mehrere Systeme, die untereinander umfangreiche Datenvolumen austauschen

Für eine SAP-Bereitstellung mit lokalem Speicher, selbst in dreischichtigen Setups, sind 1 GB-basierte Netze ausreichend. Möglicherweise müssen weitere Faktoren berücksichtigt werden. Weitere Informationen zu den Auswahlmöglichkeiten für Ihren Netzspeicher finden Sie unter [Externer Speicher](/docs/infrastructure/sap-netweaver/sap-considerations.html#external_storage).

### Hybrid-Setups
{: #hybrid}

Das Angebot '{{site.data.keyword.cloud_notm}} for SAP Applications' kann als ein externes Rechenzentrum betrachtet werden, insbesondere dann, wenn Sie in Betracht ziehen, eine Hybrid-Umgebung mit einigen SAP-Systemen in einem {{site.data.keyword.cloud_notm}}-Rechenzentrum und weitere Systeme vor Ort zu implementieren. Nachfolgend finden Sie einige Aspekte für die Konfiguration, die Sie bei einem Hybrid-Setup während der Planungsphase des Projekts berücksichtigen müssen:

  *	[SAP Transport Management System (STMS)](https://help.sap.com/saphelp_me60/helpdata/en/c4/6045377b52253de10000009b38f889/frameset.htm). Konfigurieren Sie das System basierend auf Transportgruppen, um die Dateifreigabe über Rechenzentren hinweg zu verhindern.
  *	[SAProuter](https://support.sap.com/en/tools/connectivity-tools/saprouter.html). Das Programm bietet Zugriff auf das SAP On-Line Service System (OSS). Verwenden Sie die lokale SAProuter-Instanz, die bereits verfügbar ist, um auf das OSS zuzugreifen. SAProuter kann über weitere SAProuter-Hops verwendet werden, falls das IP-basierte Routing zwischen den {{site.data.keyword.cloud_notm}}-basierten Systemen und der lokalen SAProuter-Instanz nicht zulässig ist. Alternativ können Sie eine weitere SAProuter-Instanz einrichten, die auf einem {{site.data.keyword.cloud_notm}}-basierten Server mit einer öffentlichen IP basiert, und diese über das Internet mit dem SAP OSS-System verbinden.
  *	[SAP Solution Manager](https://support.sap.com/en/solution-manager.html). Je nach dem Einsatzszenario gelten für den Zugriff auf den SAP Solution Manager unterschiedliche Verbindungsvoraussetzungen zwischen einem SAP Solution Manager und den zugehörigen verwalteten Systemen. Für diese Szenarios ist es wichtig, dass Sie die erforderliche Netzkonnektivität kennen.  

## Externer Speicher
{: #external_storage}

Mit lokalem Speicher erzielen Sie die beste Leistung bei der Bereitstellung von Datenbanken. Neben dem lokalen Speicher kann weiterer externer Speicher für das Durchführen von Backups erforderlich sein oder es kann sein, dass die Datenbank des SAP-Systems die Speicherkapazität der internen Platten überschreitet. Außerdem kann für Ihre Projektanforderungen externer Speicher erforderlich sein, beispielsweise für ESX-basierte Server für die gemeinsame Nutzung virtueller Maschinen (VMs). Für solche Anforderungen können Sie Blockspeicher oder Network Attached Storage (NAS) bestellen, wie unter [Speicher](/docs/infrastructure/sap-netweaver/sap-general-iaas-concepts.html#storage) beschrieben. Da zusätzlicher Blockspeicher und NAS-Daten über dieselben physischen Adapter wie der gesamte andere Netzverkehr übertragen werden, müssen dabei die entsprechenden Auswirkungen berücksichtigt werden. Leistungszahlen, die mit in den Zertifizierungsmaßstäben angegebenen Leistungszahlen vergleichbar sind, können dabei kaum erreicht werden.

Sie sollten ein 10 GB-basiertes Rechenzentrum für Ihre Bereitstellung auswählen, wenn Sie statt lokalem Speicher primär externen Speicher verwenden möchten. Der externe Speicher wird beispielsweise sowohl für Backups als auch für die Datenbank und für geplante hohe Lasten auf dem SAP-System verwendet. Dies empfiehlt sich, wenn Sie kurz vor der Überlastung eines 1 GB-Netzes mit einer E/A-Last mit 90 Mb/s stehen.

Des Weiteren wird empfohlen, dass Sie mindestens 4 IOPS/GB verwenden, wenn die Datenbank primär auf externen Speicher zurückgreift. Langsamere Speichersysteme sollten nur verwendet werden, wenn die Datenbankleistung für das Projekt nicht wichtig ist, oder für Backups.

Wenn Sie externen Speicher als Datenspeicher für VMware ESX verwenden möchten, befolgen Sie die Entscheidungsleitlinien unter [Zu verwendender Speicher mit VMware-Systemen](https://console.bluemix.net/docs/infrastructure/vmware/select-storage-option-use-vmware.html#storage-to-use-with-vmware-systems), um den optimalen Speichertyp für Ihren Anwendungsfall zu ermitteln.

## Bereitstellungen von VMware ESXi-Servern
{: #vmware_server}

VMware ESXi-basierte Bereitstellungen in {{site.data.keyword.cloud_notm}} unterscheiden sich von anderen cloudbasierten Bereitstellungen. {{site.data.keyword.cloud_notm}} stellt Kunden keine betriebsbereiten VMs bereit; Sie haben die Kontrolle über Ihre Umgebung und konfigurieren diese Ihren Anforderungen entsprechend. Bei der Bestellung eines VMware ESX-Servers erhalten Sie einen konfigurierten Server. Unter den folgenden Links finden Sie Informationen zu zusätzlichem Speicher und zum Ausführen von virtuellen Gastmaschinen.

  *	Unter [Zu verwendender Speicher mit VMware-Systemen](https://console.bluemix.net/docs/infrastructure/vmware/select-storage-option-use-vmware.html#storage-to-use-with-vmware-systems) finden Sie weitere Anweisungen zum Integrieren von Speicher in einer ESX-Umgebung.
  * Unter [iSCSI an VMware ESXi anhängen](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi) sind die Schritte zum Integrieren von iSCSI-basiertem Speicher mit ESX beschrieben.
  * Unter [Virtuelle VMware ESX-Maschine erstellen](https://console.bluemix.net/docs/infrastructure/vmware/vmware-esx-create-virtual-machine.html#creating-a-vmware-esx-virtual-machine) finden Sie eine Anleitung zum Bereitstellen Ihrer ersten virtuellen Maschine.

Beachten Sie, dass Sie bei der Bereitstellung von SAP NetWeaver-basierter Software unter dem Gastbetriebssystem das entsprechende Betriebssystem aus den im [SAP-Hinweis 2414097](https://launchpad.support.sap.com/#/notes/2414097) aufgeführten Betriebssystemen auswählen müssen.
