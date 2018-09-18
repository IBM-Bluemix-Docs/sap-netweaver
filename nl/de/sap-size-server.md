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


# 4. Dimensionierung des Servers
{: #size_the_server}

Nachdem Sie sich entschieden haben, welche SAP-Lösungen Sie verwenden möchten, müssen Sie als Nächstes die Anzahl der {{site.data.keyword.baremetal_long}}-Instanzen bestimmen, die Sie in Ihrer SAP-Landschaft benötigen, und sicherstellen, dass die Kapazitäten der Server ausreichend sind.
{: shortdesc}

## Methodik der SAP-Dimensionierung verstehen
{: #size_method}

Die Methodik der SAP-Dimensionierung für SAP NetWeaver-orientierte Anwendungen basiert auf SAP-Benchmarks, wie Informationen von SAP und tatsächlichen Erfahrungswerten von Kunden. Die Basiseinheit für die SAP-Auslastung ist ein SAP Application Performance Standard (SAPS). Die SAPS-Standards sind Durchsatzdefinitionen, die von SAP-Mitarbeitern in den Bereichen Kapazitätsplanung und Leistungstests geprägt werden. Beispielsweise werden 100 SAPS als 2.000 vollständig verarbeitete Auftragspositionen pro Stunde in der SAP SD-Benchmark (SD, Sales and Distribution) definiert. Dies entspricht 2.400 SAP-Transaktionen pro Stunde mit der SAP ERP-Lösung (ERP, Enterprise Resource Planning). Die Funktionalität von Prozessoren wird im Rahmen des Standard-Benchmarktests (SAP SD) gemessen, der von SAP zertifiziert ist. Weitere Informationen zu dem von SAP zertifizierten Benchmarktest finden Sie in der Veröffentlichung [*SAP Business Suite on IBM X6 Systems Reference Architecture*](https://lenovopress.com/redp5073.pdf). Der Test bewertet den Prozess anhand seiner Fähigkeit, Arbeitslasten mit einer CPU-Auslastung von nahezu 100 % bei einer Antwortzeit von unter einer Sekunde zu verarbeiten.

## SAP Quick Sizer verwenden
{: #quicksizer}
  
Der [SAP Quick Sizer](https://service.sap.com/quicksizer) ist ein webbasiertes Tool und wird von SAP für alle Partner und Kunden bereitgestellt. Dimensionierungsinformationen werden direkt in das Tool eingegeben, wo sie für SAP NetWeaver-basierte Anwendungen und für Anwendungen, die nicht auf SAP NetWeaver basieren, verarbeitet werden. Für dieses Tool ist eine SAP S-User-ID erforderlich.
  
Das Tool berechnet die Auslastung (in SAPS) und passt diese für eine entsprechende Prozessorverwendung an. Wenn beispielsweise eine Auslastung von 4.800 SAP SD-Benchmark-Transaktionen pro Stunde erforderlich war, berechnet das Tool dies als 200 SAPS. Wenn eine Zielprozessorlast von 33 % zulässig ist, passen Sie dies so an, um einen Prozessor zu finden, der 600 SAPS bei 100 % (=200 bei 33 %). Nähere Informationen zur SAPS-Berechnung finden Sie in der Veröffentlichung [*SAP Business Suite on IBM X6 Systems Reference Architecture*![Symbol für externen Link]](../../icons/launch-glyph.svg "Symbol für externen Link")](https://lenovopress.com/redp5073.pdf){: new_window}.

Obwohl diese Dimensionierungsmethode als konservativ angesehen werden kann, sollten Sie die Tatsache berücksichtigen, dass die SAPS-Zahlen für die Server basierend auf in hohem Maße optimierte SAP-Systeme berechnet wurden, auf denen nur bestimmte SAP SD-Auslastungen ausgeführt werden. Je nach Typ der SAP-Anwendung oder wenn eine benutzerdefinierte Konfiguration oder benutzerdefinierter Code im System verwendet wird, können die Ergebnisse abweichen. Auch können sich Anforderungen für das Projekt, wie Proof-of-Concept (PoC), oder Anforderungen bezüglich der Leistung und Antwortzeit unterscheiden.

## {{site.data.keyword.cloud_notm}}-Bare-Metal-Server auswählen
{: #choose_server}

Nachdem Sie Ihre SAP-Anwendungen festgelegt haben und die SAPS-Zahlen mithilfe des SAP Quick Sizer oder basierend auf Ihrer aktuellen Umgebung berechnet wurden, können Sie nun einen Server aus den angebotenen Modellen auswählen. Tabelle 1 enthält die SAPS-Zahlen für die {{site.data.keyword.baremetal_short}}, die für SAP NetWeaver zertifiziert sind. Die Zertifizierungsdokumente finden Sie unter [SAP Standard Application Benchmarks![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")]](https://www.sap.com/about/benchmark.html){: new_window}. 

Alle in Tabelle 1 aufgeführten unterstützten Servertypen entsprechen den von SAP zertifizierten Servern mit dem publizierten Namen und werden im [SAP-Hinweis 2414097![Symbol für externen Link]](../../icons/launch-glyph.svg "Symbol für externen Link")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} verifiziert; für eine vollständige Liste klicken Sie auf [hier![Symbol für externen Link]](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.sap.com/dmc/exp/2014-09-02-hana-hardware/enEN/power-systems.html){: new_window}. Beachten Sie, dass bei publizierten Namen Änderungen vorbehalten sind.

Tabelle 1. Fpr SAP NetWeaver zertifizierte {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}

| Servertyp | SAPS | RAM |
| --- | --- | --- |
| BI.S1.NW32 | 10980 | 32 GB |
| BI.S1.NW128 | 54130 | 128 GB |
| BI.S1.NW256 | 55020 | 256 GB |
| BI.S2.NW512 | 65520 | 512 GB |
| BI.S3.NW32 | 11970 | 32 GB |
| BI.S3.NW64 | 12750 | 64 GB |
| BI.S3.NW192 | 78850 | 192 GB |
| BI.S3.NW384 | 79430 | 384 GB |
| BI.S3.SW768 | 79630 | 768 GB |

## Migration eines vorhandenen SAP-Systems 
{: #migrating}

Wenn Sie ein vorhandenes SAP-System von einer beliebigen Quelle auf Ihre {{site.data.keyword.cloud_notm}}-Umgebung migrieren möchten, können Sie die SAPS-Zahlen anhand der SAPS-Zahlen der aktuellen Umgebung ermitteln. Verwenden Sie die Informationen zu Ihrer aktuellen Auslastung (CPU-Auslastung und belegter RAM) und rufen Sie die SAPS-Entsprechungen für die CPU aus den [SAP SD-Benchmarkergebnissen![Symbol für externen Link]](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.sap.com/about/benchmark.html){: new_window} ab.

## Nächste Schritte

 [5. Konfiguration festlegen](/docs/infrastructure/sap-netweaver/sap-determine-configuration.html)
