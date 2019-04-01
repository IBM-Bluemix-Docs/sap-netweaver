---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.blockstorageshort}}, {{site.data.keyword.filestorage_full_notm}}, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.baremetal_short}}

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. Realización del pedido de almacenamiento
{: #order_storage}

El pedido de {{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}} y el almacenamiento adjunto en red (NAS) se realiza después de desplegar {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}.

## Realización del pedido de almacenamiento de {{site.data.keyword.cloud_notm}}
{: #ibm_storage}

Puede seguir los pasos indicados en [Suministro y gestión de {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted#GettingStarted) o [Suministro y gestión de {{site.data.keyword.filestorage_full_notm}}](/docs/infrastructure/FileStorage?topic=FileStorage-orderingConsole#orderingConsole) para realizar el pedido de su solución de almacenamiento de copia de seguridad y restauración. Se le guiará en el proceso de decidir qué tipo de almacenamiento utilizar, cómo realizar el pedido y cómo desplegarlo en el servidor.

Las *Guías de consulta rápida de SAP NetWeaver (para Microsoft Windows* o *Red Hat Enterprise Linux*) describen una configuración y despliegue completos del servidor, incluyendo los pasos de configuración del {{site.data.keyword.blockstorageshort}} {{site.data.keyword.cloud_notm}} e iSCSI sobre la base del despliegue de ejemplo para Linux y Windows.

Para VMware ESXi, se puede utilizar el tipo de almacenamiento {{site.data.keyword.cloud_notm}} como almacenes de datos, en cuyo caso, se correlaciona con ESXi como dispositivo iSCSI. Siga los pasos indicados en [Montaje de iSCSI en VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mounting-iscsi-vmware-esxi#mounting-iscsi-vmware-esxi) para correlacionar dispositivos iSCSI con ESXi.

## Siguientes pasos

  [2. Protección del entorno](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. Instalación del sistema operativo de invitado en el hipervisor ESX (opcional)](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. Descarga e instalación de software y aplicaciones SAP](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
