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

# Aspectos a considerar cuando planifique su entorno SAP
{: #considerations}

Los sistemas SAP en un entorno tienen requisitos específicos para la conectividad, ya sea entre ellos o bien con sistemas externos. También debe tener en cuenta el almacenamiento externo para su entorno, y qué hacer si decide desplegar VMware en el servidor.

## Conectividad de red
{: #network_connectivity}

[Red {{site.data.keyword.cloud_notm}} ](/docs/infrastructure/sap-netweaver/sap-about.html#ibm_cloud_network) proporciona una visión general del enfoque de {{site.data.keyword.cloud}} a la conectividad de red. Los problemas relacionados con la conectividad de red pueden provocar retrasos importantes en su proyecto si no los planifica correctamente, independientemente de cómo tenga previsto utilizar el sistema. 

En general, tiene dos opciones de interfaz para los servidores de {{site.data.keyword.cloud_notm}} suministrados por IaaS, la primera es una interfaz externa con una IP pública. La segunda es una interfaz interna suministrada con una “IP privada” de conformidad con Request for Comment (RFC) 1918. También puede elegir una única interfaz interna con una “IP privada”. Ambas opciones pueden hacerse redundantes mediante una “interfaz de acoplamiento” Linux o mediante Windows Network Interface Card (NIC) Teaming, y estar disponibles a una velocidad de 100 Mb/s, 1 Gb/s y 10 Gb/s.

En función de su caso de uso, una IP pública es aceptable para entornos de pruebas (PoC) porque la IP externa podría resultar más sencilla de utilizar. Existe un riesgo de seguridad potencial aunque se instale y configure previamente un cortafuegos básico. Si desea utilizar una interfaz pública, asegúrese de elegir un valor suficientemente alto para **Ancho de banda público** al realizar el pedido del servidor. Este valor determina la cantidad total de datos que pueden transferirse a través de la interfaz durante un período de un mes. Mientras que la comunicación de red normal, la interfaz gráfica de usuario (GUI) SAP o el tráfico de llamada a función remota (RFC) SAP pueden sumar unos pocos megabytes al día, las cargas masivas de datos pueden superar fácilmente los 1.000 GB al mes. Necesita saber la cantidad de datos que se transfieren al menos por el orden de magnitud o bien cambiar a la segunda opción.

La segunda opción accede a la red privada virtual (VPN) de {{site.data.keyword.cloud_notm}} a través del portal de clientes de infraestructura de {{site.data.keyword.cloud_notm}}, o despliega un dispositivo de seguridad en su entorno. Los dispositivos de seguridad se ofrecen para cortafuegos, la conversión de la dirección de red, el acceso VPN y otras funciones de red. Además, estos dispositivos de seguridad pueden proporcionarle un ancho de banda superior, que le ayudará a transferir cantidades de datos mayores en un centro de datos {{site.data.keyword.cloud_notm}}. Se recomienda que el departamento de redes hable con [{{site.data.keyword.cloud_notm}} Soporte](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support) después de determinar el diseño del entorno y la conectividad necesarios en la capa de aplicación SAP.

### Redes VLAN
{: #vlans}

Si desea separar distintos tipos de tráfico de red en su entorno, puede solicitar más LAN virtual (VLAN). Tenga en cuenta que las VLAN adicionales sólo generan segregación de tráfico, no mayor rendimiento. La segregación de tráfico se considera en caso de despliegues basados en VMware, donde podría necesitar separar más estrictamente los distintos tipos de tráfico de red por motivos de seguridad.

Para los siguientes casos de uso, debería asegurarse de que todos los servidores estén en la misma VLAN durante el despliegue:
  *	Múltiples servidores que intercambian datos, como una configuración SAP de tres capas —instancias de aplicación SAP y base de datos en distinto servidores
  *	Múltiples sistemas que intercambian grandes cantidades de datos

Para un despliegue de SAP con almacenamiento local, incluso para configuraciones de tres capas, bastara con redes basadas en 1 Gb. Deberían considerarse más factores, consulte [Almacenamiento externo](/docs/infrastructure/sap-netweaver/sap-considerations.html#external_storage) para obtener más información sobre las opciones de almacenamiento de red.

### Configuraciones híbridas
{: #hybrid}

La oferta de {{site.data.keyword.cloud_notm}} para aplicaciones SAP puede considerarse como un centro de datos externo, especialmente si está pensando en implementar un entorno híbrido con algunos sistemas SAP en un centro de datos {{site.data.keyword.cloud_notm}} y otros sistemas en el sitio. Algunos elementos de configuración específicos que deben considerarse como parte de la fase de planificación del proyecto con una configuración híbrida:

  *	[SAP Transport Management System (STMS)](https://help.sap.com/saphelp_me60/helpdata/en/c4/6045377b52253de10000009b38f889/frameset.htm). Configúrelo sobre la base de los Grupos de transporte para impedir el uso compartido de archivos entre centros de datos.
  *	[SAProuter](https://support.sap.com/en/tools/connectivity-tools/saprouter.html). Proporciona acceso a SAP On-Line Service System (OSS). Utilice SAProuter en local, que ya está disponible, para acceder a OSS. Este SAProuter se puede utilizar a través de hops de SAProuter si no se permite el direccionamiento basado en IP entre sus sistemas basados en {{site.data.keyword.cloud_notm}} y SAProuter en local. Como alternativa, puede configurar otro SAProuter que se basa en un servidor basado en {{site.data.keyword.cloud_notm}} con una IP pública y conectarlo al sistema SAP OSS a través de Internet.
  *	[SAP Solution Manager](https://support.sap.com/en/solution-manager.html). El acceso a SAP Solution Manager tiene varios requisitos de conectividad entre SAP Solution Manager y sus sistemas gestionados, en función del caso de uso. Estos casos de uso requieren saber la conectividad de red necesaria.  

## Almacenamiento externo
{: #external_storage}

El almacenamiento local proporciona el mejor rendimiento para el despliegue de base de datos. Además del almacenamiento local, podría requerir más almacenamiento externo para realizar copias de seguridad, o la base de datos de los sistemas SAP podrían superar la capacidad de almacenamiento de los discos internos. Otro ejemplo es que los requisitos del proyecto exijan más almacenamiento externo, como para múltiples servidores basados ESX, que quieren compartir máquinas virtuales. Para estos requisitos, puede solicitar almacenamiento en bloque o almacenamiento adjunto en red (NAS), como se describe en [Almacenamiento](/docs/infrastructure/sap-netweaver/sap-general-iaas-concepts.html#storage). Como los datos adicionales de NAS y almacenamiento en bloque se transfieren a través de los mismos adaptadores físicos que todo el tráfico de red, deberá tener en cuenta su posible impacto. Los números de rendimiento comparables con los números calculados en las pruebas de referencia de la certificación podrían simplemente alcanzarse.

Se recomienda utilizar un centro de datos basado en 10 Gb para el despliegue si tiene previsto utilizar principalmente almacenamiento externo en lugar de almacenamiento local. Por ejemplo, el almacenamiento externo se utiliza para la copia de seguridad y para la base de datos, y si tiene previsto poner una carga alta en el sistema SAP. Si está a punto de sobrecargar una red de 1 Gb con una carga de E/S de 90 MB/s.

Otra recomendación es que utilice como mínimo 4 IOPS/GB si la base de datos reside principalmente en almacenamiento externo. Un almacenamiento más lento solo debería utilizarse si el rendimiento de la base de datos no es crítico para el proyecto o para la copia de seguridad.

Si tiene previsto utilizar almacenamiento externo como almacén de datos para VMware ESX, siga las directrices de [Almacenamiento para utilizar con sistemas VMware](https://console.bluemix.net/docs/infrastructure/vmware/select-storage-option-use-vmware.html#storage-to-use-with-vmware-systems) para determinar el tipo de almacenamiento óptimo para su caso de uso.

## Despliegues de servidor VMware ESXi
{: #vmware_server}

Los despliegues basados en VMware ESXi en {{site.data.keyword.cloud_notm}} son distintos de otros despliegues basados en nube. {{site.data.keyword.cloud_notm}} no proporciona a sus clientes máquinas virtuales en ejecución, si no que estos toman el control de su entorno y lo configuran para cubrir sus requisitos. Recibirá un servidor configurado al realizar el pedido de un servidor VMware ESX. Los siguientes enlaces proporcionan información sobre el almacenamiento adicional y las máquinas virtuales de invitado en ejecución.

  *	[Almacenamiento para utilizar con sistemas VMware](https://console.bluemix.net/docs/infrastructure/vmware/select-storage-option-use-vmware.html#storage-to-use-with-vmware-systems) ofrece más orientación sobre cómo integrar el almacenamiento en un entorno ESX.
  * [Montaje de iSCSI en VMware ESXi](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi) describe los pasos para integrar almacenamiento basado en iSCSI en ESX.
  * [Creación de una máquina virtual de VMware ESX](https://console.bluemix.net/docs/infrastructure/vmware/vmware-esx-create-virtual-machine.html#creating-a-vmware-esx-virtual-machine) le guía en el proceso de desplegar su primera máquina virtual.

Tenga en cuenta que para desplegar software basado en SAP NetWeaver en el sistema operativo invitado, debe elegir el sistema operativo invitado de los sistemas operativos mencionados en la [Nota de SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097).
