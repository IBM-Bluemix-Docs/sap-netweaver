---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, high availability, highly available, HA, disaster recovery, DR, Microsft Windows Server Failover Clustering, WFSC, bring your own license, BYOL, single point of failure, SPOF, Link Aggregation Control Protocol, LACP, VLANs, SAP Certified, database, Linux Pacemaker

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# IBM Cloud-Unterstützung für Hochverfügbarkeit
{: #ha}

Die {{site.data.keyword.cloud}}-IaaS (Infrastructure as a Service) bietet Ihnen eine leistungsfähige Datenverarbeitungsumgebung mit optionaler Betriebssystembereitstellung, die HA-Lösungen (HA - High Availability, Hochverfügbarkeit) unterstützt. Die Lösung basiert auf der unterstützten Betriebssystemversion, wie in [SAP Note 2414097 ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} beschrieben. Die HA-Lösung ist auf die bestellten Betriebssystemlizenzen, die mit Ihrer Bereitstellung geliefert werden, oder auf Lizenzen von Drittanbietern (z. B. BYOL - Bring Your Own License) beschränkt. Besprechen Sie die HA-Details auf jeden Fall vor der Bereitstellung mit dem {{site.data.keyword.cloud_notm}}-Support. 

Für {{site.data.keyword.cloud_notm}} for SAP werden die folgenden Betriebssysteme unterstützt und bereitgestellt: 
* Linux [Red Hat Enterprise Linux (RHEL) oder SUSE Enterprise Linux Server (SLES)] unterstützt HA-Lösungen mit sowohl SAP NetWeaver als auch SAP HANA. In der {{site.data.keyword.cloud_notm}}-Umgebung gibt es geringfügige Einschränkungen, die in [SAP NetWeaver-Hochverfügbarkeitskonfigurationen - Übersicht](#overview-configs) erläutert sind. 
* Microsoft Windows unterstützt nur SAP NetWeaver-HA-Lösungen (aufgrund von Einschränkungen der SAP HANA-Datenbank). 

## SAP NetWeaver-Hochverfügbarkeitskonfigurationen - Übersicht
{: #overview-configs}

In zahlreichen Dokumenten werden detaillierte Hilfeinformationen zur Planung und Installation einer HA-Umgebung für SAP-Services zur Verfügung gestellt. Die Dokumente enthalten Informationen zu Failover, Replikation, Scale-out und Disaster-Recovery (DR). An geeigneter Stelle wird auf bestimmte Dokumente verwiesen. 

Alle Betriebssysteme und Distributionen, die von {{site.data.keyword.cloud_notm}} für eine SAP-Bereitstellung unterstützt werden (Windows sowie Linux RHEL und SLES), enthalten Hochverfügbarkeitssoftware und spezifische Erweiterungen. Die folgenden Betriebssysteme und Distributionen werden unterstützt. 

* In [New Failover Clustering Improvements in Windows Server 2012 and Its Benefits for SAP NetWeaver High Availability ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://blogs.sap.com/2013/10/16/new-failover-clustering-improvements-in-windows-server-2012-and-its-benefits-for-sap-netweaver-high-availability/){: new_window} finden Sie eine Beschreibung auf der Basis von Microsoft Windows Server Failover Clustering (WFSC) unter dem Betriebssystem Windows mit SAP NetWeaver. 

* Anleitungen zur Bereitstellung von SAP NetWeaver in einer Linux-basierten HA-Umgebung mit Linux Pacemaker sind in zwei Dokumenten enthalten: 
  * SUSE SAP NetWeaver High Availability Cluster 7.40 Setup Guide
  * Deploying Highly Available SAP NetWeaver-based Servers Using Red Hat Enterprise Linux HA add-on with Pacemaker

* [Building High Availability for SAP NetWeaver and SAP HANA on Linux ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://support.sap.com/content/dam/SAAP/SAP_Activate/AGS_70.pdf){: new_window} ist ein SAP-Dokument mit bewährten Verfahren, das eine umfassende technische Beschreibung mit starkem Fokus auf SAP HANA beinhaltet. 

* [SAP NetWeaver High Availability and Business Continuity in Virtual Environments with VMware and Hyper-V on Microsoft Windows ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.sap.com/documents/2015/07/508b62bc-5b7c-0010-82c7-eda71af511fa.html){: new_window} behandelt die Virtualisierungsaspekte, wenn Sie Hochverfügbarkeit auf virtualisierten Servern implementieren möchten. 

Weitere Hochverfügbarkeitsprodukte, die von SAP-Partnern für Hochverfügbarkeitsszenarios zertifiziert wurden, finden Sie in [High Availability Partner Information ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://wiki.scn.sap.com/wiki/display/SI/High+Availability+Partner+Information){: new_window}.
Für andere Datenbanken als SAP HANA finden Sie weitere Informationen zu Failover bei Hochverfügbarkeit und zu DR-Konfigurationen in der Datenbankdokumentation. 

Beachten Sie, dass für die Unterstützung des Failover von Systemen in der Regel gemeinsamer Zugriff auf NFS-/CIFS-Speicher (Network File System/Common Internet File System) oder gemeinsamer Zugriff auf iSCSI-basierten LUNS-Speicher (Logical Unit Number Storage) erforderlich ist. Für die Unterstützung einer DR-ähnlichen Konfiguration ist normalerweise lokaler Speicher kombiniert mit einer Replikationsmethode erforderlich. Überprüfen Sie bei der Planung Ihrer Bereitstellung die Leistungs- und Latenzanforderungen des Datenbankprodukts ebenso wie bei lokalen Installationen. 

## Weitere Anleitung
{: #extra-guide}

Die Abschnitte [Quorumbasierter Speicher](#quorum) und [Netzhinweise](#network) enthalten Informationen, die Sie bei Ihrer Bereitstellung beachten müssen. Abgesehen von den Hinweisen in diesen Abschnitten unterscheidet sich die Installation von SAP NetWeaver und des zugehörigen Datenbanksystems in einer HA-Umgebung nicht von anderen lokalen Installationen. 

### Quorumbasierter Speicher
{: #quorum}

Aufgrund von Sicherheitsbeschränkungen in der {{site.data.keyword.cloud_notm}}-Umgebung ist kein netzbasierter Zugriff auf Remote-Management-Geräte über IPMI (Intelligent Platform Management Interface) verfügbar. In Clusterumgebungen werden im Allgemeinen IPMI-basierte Komponenten für die Abschirmung von Clusterknoten verwendet, damit ein Quorum jederzeit gewährleistet ist. Wenn kein IPMI-fähiges Gerät vorhanden ist, werden gemeinsam genutzte Speichergeräte verwendet. In einer {{site.data.keyword.cloud_notm}}-Umgebung werden gemeinsam genutzte Speichergeräte implementiert, indem eine iSCSI-LUN als Quorumeinheit auf Ihren Servern bereitgestellt wird. Beispiele sind ein FSW (File Share Witness) in einem Microsoft-Cluster und SDB (Storage-Based Death) für Stonith unter Linux Pacemaker. 
* Klicken Sie [hier ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://linux-ha.org/wiki/Cluster_Concepts){: new_window}, um weitere Informationen zu Konzepten bei Linux-Hochverfügbarkeitsclustern aufzurufen. 
* Klicken Sie [hier ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://docs.microsoft.com/en-us/windows-server/failover-clustering/manage-cluster-quorum){: new_window}, um weitere Informationen zum Konfigurieren und Verwalten von Quorumservern für Windows Server 2012 und Windows Server 2012 R2 aufzurufen. 

{{site.data.keyword.cloud_notm}}-Speicher verfügt über integrierte HA-Leistungsmerkmale. Aus diesem Grund entsteht durch eine einzige gemeinsam genutzte iSCSI-LUN kein Single Point of Failure (SPOF), da das Netzlayout redundant ist. Je nach den technischen Daten Ihres Clusterprodukts können jedoch mehrere Quorumeinheiten erforderlich sein. 

### Netzhinweise
{: #network}

Eine {{site.data.keyword.cloud_notm}}-basierte Installation umfasst eine der folgenden Netzkonfigurationen: 
* Privates Netz
* Öffentliches Netz
* Öffentliches und privates Netz
* Zwei private Netze (auf Sonderanforderung)

Wie bei lokalen Installationen können zusätzliche Netzadapter in Abhängigkeit von den physischen Einschränkungen der Hardware bestellt werden. Die Einschränkungen sind dieselben wie bei lokalen Installationen. Die Bestellung von redundanten Netzadaptern bei Hardwarebereitstellungen trägt zur Vermeidung von SPOFs in der gesamten Netztopologie bei. Redundante Adapter werden in einer Failover-Konfiguration mit LACP (Link Aggregation Control Protocol) konfiguriert. Für Linux werden bei dieser Konfiguration Bonding-Schnittstellen verwendet, für Microsoft Windows Teaming-Adapter. Die {{site.data.keyword.cloud_notm}}-Switchinfrastruktur, mit der diese Adapter verbunden sind, ist redundant. Daher entstehen keine neuen SPOFs. Die redundante Infrastruktur kann von den bestellten VLANs verwendet werden. 

Abhängig von den Netzanforderungen, z. B. für Replikationsszenarios in einer DR-Konfiguration, müssen Sie die Position der verbundenen Geräte und alle neuen, für das jeweilige Produkt spezifischen Netzanforderungen überprüfen. In einigen Fällen kann die speicherbasierte Momentaufnahmereplikation von {{site.data.keyword.cloud_notm}} Ihre Anforderungen erfüllen. Besprechen Sie mit dem {{site.data.keyword.cloud_notm}}-Support, welche Lösung sich für Ihre Geschäftsprozessanforderungen am besten eignet. 
