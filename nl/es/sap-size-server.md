---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, SAP Application Performance Standard, SAPS, SAP Quick Sizer

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 4. Dimensionamiento del servidor
{: #size_the_server}

Después de decidir qué soluciones SAP tiene previsto utilizar, el siguiente paso consiste en determinar el número de {{site.data.keyword.baremetal_long}} que necesita para dar soporte a su entorno SAP y garantizar que los servidores estén correctamente dimensionados.
{: shortdesc}

## Descripción de la metodología de dimensionamiento de SAP
{: #size_method}

La metodología de dimensionamiento de SAP para aplicaciones centradas en SAP NetWeaver se basa en pruebas de referencia de SAP, como información de SAP y de las experiencias de clientes reales. La unidad de carga de trabajo de SAP base es SAPS (SAP Application Performance Standard). SAPS es una definición de rendimiento que se extrae de personal de pruebas de rendimiento y planificación de capacidad de SAP. Por ejemplo, 100 SAPS se definen como 2.000 artículos de pedido procesados comercialmente por hora en la prueba de referencia de la aplicación SAP Sales and Distribution (SAP SD) estándar. Esto equivale a 2.400 transacciones SAP por hora con la solución SAP Enterprise Resource Planning (SAP ERP). La capacidad de los procesadores se mide durante la prueba de referencia (SAP SD) estándar, certificada por SAP. Para obtener más detalles sobre la prueba de referencia que está certificado por SAP, consulte [*SAP Business Suite sobre la arquitectura de referencia de IBM X6 Systems* ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://lenovopress.com/redp5073.pdf){: new_window}. La prueba evalúa el proceso según su capacidad de procesar trabajo a casi el 100% de carga de CPU con un tiempo de respuesta inferior a 1 segundo.

## Uso de SAP Quick Sizer
{: #quicksizer}

[SAP Quick Sizer ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://service.sap.com/quicksizer){: new_window} es una herramienta web que SAP proporciona a todos sus socios y clientes. La información de dimensionamiento se introduce directamente en la herramienta, donde esta dimensiona las aplicaciones basadas en SAP NetWeaver y las aplicaciones no basadas en SAP NetWeaver. Requiere un ID S-user de SAP.

Calcula la carga de trabajo (en SAPS) y la ajusta para permitir el uso adecuado del procesador. Así, si se necesita una carga trabajo de 4.800 transacciones de prueba de referencia de SAP SD por hora, la herramienta calcula esto como 200 SAPS. Si se permite una carga de procesador de destino del 33%, ajústela para encontrar un procesador con capacidad de 600 SAPS al 100% (=200 al 33%). Para obtener información detalla sobre el cálculo de SAPS, consulte [*SAP Business Suite sobre la arquitectura de referencia de IBM X6 Systems* ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://lenovopress.com/redp5073.pdf){: new_window}.

Aunque el método de dimensionamiento podría considerarse conservador, tenga en cuenta que los números de SAPS para los servidores se han calculado basándose en sistemas SAP muy ajustados que ejecutan únicamente cargas de trabajo SAP SD específicas. En función del tipo de aplicación SAP, cualquier configuración personalizada o código personalizado del sistema, los resultados podrían variar. Además, los requisitos del proyecto, como las pruebas de concepto (PoC) o referentes al rendimiento y el tiempo de respuesta, podrían diferir.

## Elección de un servidor nativo de {{site.data.keyword.cloud_notm}}
{: #choose_server}

Una vez determinadas las aplicaciones SAP y tras haber realizado los cálculos de los números SAPS mediante SAP Quick Sizer, o sobre la base de su entorno actual, ya puede elegir un servidor entre los modelos ofrecidos. La Tabla 1 contiene los números SAPS para los {{site.data.keyword.baremetal_short}} certificados para SAP NetWeaver. Consulte [SAP Standard Application Benchmarks ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.sap.com/about/benchmark.html){: new_window} para obtener los documentos de certificación.

Todos los tipos de servidor soportados que se listan en la Tabla 1 coinciden con los tipos certificados por SAP con el nombre publicado y verificados en la [Nota de SAP 2414097 ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}; pulse [aquí ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.sap.com/dmc/exp/2014-09-02-hana-hardware/enEN/power-systems.html){: new_window} para ver la lista completa. Tenga en cuenta que los nombres publicados están sujetos a cambios.

Tabla 1. {{site.data.keyword.baremetal_short}} de {{site.data.keyword.cloud_notm}} certificados para SAP NetWeaver

| Tipo de servidor | SAPS | RAM |
| --- | --- | --- |
| BI.S1.NW32 | 10980 | 32 GB |
| BI.S1.NW128 | 54130 | 128 GB |
| BI.S1.NW256 | 55020 | 256 GB |
| BI.S2.NW512 | 65520 | 512 GB |
| BI.S3.NW32 | 11970 | 32 GB |
| BI.S3.NW64 | 12750 | 64 GB |
| BI.S3.NW192 | 78850 | 192 GB |
| BI.S3.NW384 | 79430 | 384 GB |
| BI.S3.NW768 | 79630 | 768 GB |

## Migración de un sistema SAP existente
{: #migrating}

Si tiene previsto migrar un sistema SAP existente desde cualquier origen a su entorno {{site.data.keyword.cloud_notm}}, puede determinar los números SAPS del entorno actual. Utilice la información sobre su carga de trabajo actual (las CPU y RAM utilizadas) y obtenga los SAPS equivalentes para su CPU a partir de los [resultados de la prueba de referencia de SAP SD![Icono de enlace externo]](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.sap.com/about/benchmark.html){: new_window}.

## Siguientes pasos

 [5. Determinación de la configuración](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration)
