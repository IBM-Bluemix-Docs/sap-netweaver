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


# 5. Determinación de la configuración
{: #determine_configuration}

Con un sistema SAP NetWeaver, tiene dos opciones de despliegue:
  * Sistema central, que es una instalación de un único host (dos capas)
  * Sistema distribuido, que es una instalación de múltiples hosts (tres capas)
  
Las opciones influyen en la elección de servidor. Es posible que desee distribuir la carga de trabajo a distintos servidores o mantener la carga de trabajo en un servidor para simplificar. Consulte [Configuración de la infraestructura](/docs/infrastructure/sap-netweaver/sap-setting-up-infrastructure.html#set_up_infrastructure) para obtener una orientación paso a paso sobre cómo desplegar el servidor.

## Configuración del almacenamiento
{: #storage_config}

La Tabla 1 es una configuración de almacenamiento de ejemplo para un servidor de 256 GB con 50.000 [SAPS](/docs/infrastructure/sap-netweaver/sap-size-server.html), 1,5 TB a 6.000 IOPS para un sistema central con SAP, que utiliza una base de datos {{site.data.keyword.Db2_on_Cloud_long}} con [{{site.data.keyword.blockstorageshort}} {{site.data.keyword.cloud_notm}} ](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) externo o [{{site.data.keyword.filestorage_short}} {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage) (4 IOPS/GB). El cálculo para IOPS es

  * 6.000 IOPS/1.500 GG = 4 IOPS/GB necesarios para el almacenamiento externo. Se suponen 3.000 GB para copia de seguridad a 2 IOPS/GB (rendimiento medio).
  
Tabla 1. Diseño de almacenamiento de ejemplo sobre la base del cálculo de IOPS

| Sistema de archivos | # de volúmenes | Tipo de almacenamiento | IOPS/GB | GB | Núm. IOPS |
| --- | --- | --- | --- | --- | --- |
| / | 1 | Interno | N/D | 150 GB | N/D |
| /boot | 1 | Interno | N/D | 0,25 GB | N/D |
| swap | 1 | Interno | N/D | 256 GB | N/D |
| /db2 (incluyendo registros) | 1 | Interno | N/D | 250 GB | N/D |
| sapdata | 1 | Externo | 4 IOPS/GB | 1.500 GB | 6.000 IOPS |
| backup/log y backup | 1 | Externo | 2 IOPS/GB | 3.000 GB | 6.000 IOPS |

## Configuración de alta disponibilidad
{: #ha_config}

El entorno {{site.data.keyword.cloud_notm}} no admite ningún escenario de alta disponibilidad (HA) preconfigurado. Sin embargo, puede configurar escenarios de alta disponibilidad sobre la base de la extensión de HA para el sistema operativo que elija. Agrega la extensión de alta disponibilidad añadiendo el hardware necesario y los componentes de software requeridos a sus entornos. Si necesita licencias de software adicionales, acceso a distintos repositorios de software o ambos, póngase en contacto con [Soporte de {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support) para obtener ayuda sobre la configuración de los requisitos adicionales.

Esta información no se aplica únicamente al software de alta disponibilidad de SAP NetWeaver, sino también al software de alta disponibilidad para el sistema de gestión de bases de datos relacionales (RDBMS) que elija. Esto incluye los requisitos de alta disponibilidad y recuperación tras desastre para el RDBMS, por ejemplo, la réplica. Los procedimientos de configuración no difieren de los procesos de configuración en un entorno local y requieren los mismos pasos de configuración de hardware y software.

## Siguientes pasos

Ahora está listo para comenzar el Suministro de {{site.data.keyword.baremetal_short}}. Consulte [Suministro del entorno SAP NetWeaver](/docs/infrastructure/sap-netweaver/sap-provision-environment.html) para conocer los pasos a seguir.
  
  


