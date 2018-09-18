---



copyright:
  years: 2018
lastupdated: "2018-05-18"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 5. Konfiguration festlegen
{: #determine_configuration}

Bei einem SAP NetWeaver-System stehen Ihnen zwei Bereitstellungsoptionen zur Verfügung:
  * Ein zentrales System, bei dem es sich um eine Installation mit einem einzigen Host (zweischichtig) handelt
  * Ein verteiltes System, bei dem es sich um eine Installation mit mehreren Hosts (dreischichtig) handelt
  
Die Optionen wirken sich auf die Wahl des Servers aus. Sie können die Arbeitslast entweder auf mehrere Server verteilen oder einfachheitshalber auf einem Server behalten. Eine schrittweise Anleitung zum Bereitstellen des Servers finden Sie unter [Infrastruktur einrichten](/docs/infrastructure/sap-netweaver/sap-setting-up-infrastructure.html#set_up_infrastructure).

## Speicherkonfiguration
{: #storage_config}

Tabelle 1 zeigt eine Beispielspeicherkonfiguration für einen 256 GB-Server mit 50.000 [SAPS](/docs/infrastructure/sap-netweaver/sap-size-server.html), 1,5 TB bei 6.000 IOPS für ein zentrales System mit SAP unter Verwendung einer {{site.data.keyword.Db2_on_Cloud_long}}-Datenbank mit externem [{{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) oder [{{site.data.keyword.cloud_notm}} {{site.data.keyword.filestorage_short}}](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage) (4 IOPS/GB). Die Berechnung für IOPS lautet

  * 6.000 IOPS/1.500 GG = 4 IOPS/GB wird für externen Speicher benötigt. Es gilt die Annahme von 3.000 GB für Backup-Operationen bei 2 IOPS/GB (mittlere Leistung).
  
Tabelle 1. Beispielspeicherbelegung basierend auf einer IOPS-Berechnung

| Dateisystem | Anzahl der Datenträger | Speichertyp | IOPS/GB | GB | Anzahl IOPS |
| --- | --- | --- | --- | --- | --- |
| / | 1 | Intern | n. z. | 150 GB | n. z. |
| /boot | 1 | Intern | n. z. | 0,25 GB | n. z. |
| swap | 1 | Intern | n. z. | 256 GB | n. z. |
| /db2 (einschl. Protokolle) | 1 | Intern | n. z. | 250 GB | n. z. |
| sapdata | 1 | Extern | 4 IOPS/GB | 1.500 GB | 6.000 IOPS |
| backup/log and backup | 1 | Extern | 2 IOPS/GB | 3.000 GB | 6.000 IOPS |

## Hochverfügbarkeitskonfiguration
{: #ha_config}

Die {{site.data.keyword.cloud_notm}}-Umgebung unterstützt keine vorkonfigurierten Szenarios für Hochverfügbarkeit. Sie können solche Szenarios jedoch basierend auf der Hochverfügbarkeitserweiterung für das von Ihnen ausgewählte Betriebssystem konfigurieren. Sie können diese Erweiterung durch das Hinzufügen der erforderlichen Hardware- und Softwarekomponenten zu Ihren Landschaften hinzufügen. Wenn Sie zusätzliche Softwarelizenzen und/oder Zugriff auf verschiedene Software-Repositorys benötigen, wenden Sie sich an den [{{site.data.keyword.cloud_notm}}-Support](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support), um Unterstützung bei der Einrichtung zusätzlicher Voraussetzungen zu erhalten.

Diese Information gilt nicht nur für HA-Software (HA, High Availability) für SAP NetWeaver, sondern auch für HA-Software für das von Ihnen ausgewählte Managementsystem für relationale Datenbanken (RDBMS). Dies umfasst die Mechanismen für Hochverfügbarkeit und Disaster-Recovery für das RDBMS (z. B. die Replikation). Die Setup-Prozeduren unterscheiden sich nicht von anderen Setup-Prozeduren in einer lokalen Umgebung und erfordern die gleichen Schritte für die Hardware- und Softwarekonfiguration.

## Nächste Schritte

Sie können nun mit der Bereitstellung der {{site.data.keyword.baremetal_short}}-Instanzen beginnen. Informationen zu diesen nächsten Schritten finden Sie unter [SAP NetWeaver-Umgebung bereitstellen](/docs/infrastructure/sap-netweaver/sap-provision-environment.html).
  
  


