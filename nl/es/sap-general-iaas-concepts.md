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

# Visión general de SAP NetWeaver on IBM Cloud IaaS
Un entorno de infraestructura como servicio (IaaS) consta de muchos componentes: centro de datos, cálculo, conectividad, almacenamiento y red. 

## Centros de datos

Con centros de datos en Norteamérica y Sudamérica, Europa, Asia y Australia, puede suministrar recursos de nube donde (y cuando) los necesite. Cada centro de datos está conectado a la red privada global de {{site.data.keyword.cloud_notm}}, realizando transferencias de datos de forma más rápida y eficiente en todo el mundo.

Consulte [Centros de datos](https://www.ibm.com/cloud-computing/bluemix/data-centers){: new_window} para obtener más información sobre los centros de datos de {{site.data.keyword.cloud_notm}} y puntos de presencia (PoP).

## Servidores nativos

{{site.data.keyword.baremetal_long}} son servidores físicos con funcionalidades de personalización limitadas. Los servidores están dedicados a su uso, o de su cliente, y no se comparten, ni los recursos de servidor, con otros clientes de {{site.data.keyword.cloud_notm}}. Usted, o su cliente, gestiona estos servidores, y se suministran sin un hipervisor.

Como la personalización está limitada en los servidores nativos, se pueden obtener tiempos de suministro entre 1 o 4 horas más rápidos. El suministro rápido es útil si intenta lanzar al mercado una app antes que la competencia.

Se le ofrece una matriz de combinaciones de RAM y CPU, ya que los servidores certificados por SAP tienen una cantidad de RAM y un número de CPU preconfigurados. La combinación *no se puede* cambiar durante el proceso de pedido o mediante una incidencia de soporte después de desplegar los servidores.

Si su proyecto requiere una capa de virtualización, la oferta de SAP NetWeaver incluye la opción de solicitar {{site.data.keyword.baremetal_short}} que se despliegan con VMware ESXi. La instancia de ESX está bajo su control, ya que se despliega en su centro de datos. El sistema está completamente configurado, en cuanto a redes (cualquier configuración adicional, como el almacenamiento, depende de usted). Se recomienda contar con un experto en administración de ESX entre el personal para iniciar el proyecto con éxito.

Consulte [Acerca de los servidores nativos](https://console.bluemix.net/docs/bare-metal/index.html#about-bare-metal-servers) para obtener más información sobre los servidores nativos. 

## Sistemas operativos

Consulte la [Nota de SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097){: new window} para obtener una lista de sistemas operativos de invitado para desplegar sistemas basados en SAP NetWeaver. Se necesita un ID S-user de SAP para acceder a la Nota de SAP. Usted cubre la licencia del sistema operativo de invitado.

## Conectividad de red

Se otorga automáticamente conectividad de red privada virtual (VPN) a la red en la nube virtual de {{site.data.keyword.cloud_notm}} cuando se configura su cuenta de {{site.data.keyword.cloud_notm}}. De forma predeterminada, el servidor tiene una dirección IP pública y privada. Si quiere que el servidor sea privado, puede desactivar la interfaz pública después de suministrar el servidor o solicitar el servidor como privado. Consulte [Iniciación a las redes privadas virtuales](https://console.bluemix.net/docs/infrastructure/iaas-vpn/getting-started.html#getting-started-with-virtual-private-networking-vpn-) para obtener más información sobre la red privada virtual de {{site.data.keyword.cloud_notm}}.

## Almacenamiento
{: #storage}

Se suministra almacenamiento local con el {{site.data.keyword.baremetal_short}} y utiliza la LAN virtual (VLAN) de red privada de {{site.data.keyword.cloud_notm}} para proporcionar seguridad empresarial sin obstruir el acceso de administrador. Es perfecta para aplicaciones con gran carga de almacenamiento y requisitos elevados de E/S, como un sistema operativo, y software de aplicación y base de datos. El espacio de disco de servidor SAP NetWeaver depende de cómo esté configurado el servidor. Póngase en contacto con [Soporte de {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/support/index.html#getting-customer-support) para consultar las opciones de ampliación si el almacenamiento local de su servidor no es suficiente para la carga de trabajo.

Existen dos tipos de almacenamiento para {{site.data.keyword.cloud_notm}}, en bloque y archivo, a elegir para realizar copias de seguridad y restauraciones para SAP NetWeaver. Ambos tipos utilizan operaciones de entrada/salida por segundo (IOPS), que se utilizan para determinar las necesidades de almacenamiento. Los IOPS se calculan sobre la base de un tamaño de bloque de 16 KB con una combinación de lectura/escritura 50/50. Para alcanzar los máximos IOPS en un volumen, se requieren los recursos de red adecuados. Otras consideraciones incluyen el uso de la red privada fuera del almacenamiento y host, y los ajustes específicos de la aplicación (por ejemplo, pilas de IP y profundidades de cola). Consulte [Iniciación al almacenamiento en bloque](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) e [Iniciación al almacenamiento de archivos](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage) para obtener más información sobre el rendimiento y los niveles de almacenamiento.

{{site.data.keyword.cloud_notm}} también ofrece almacenamiento adjunto en red (NAS), si busca una solución de copia de seguridad rápida, rentable y eficiente para sus dispositivos. NAS es compatible con
  * Sistema operativo Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X
  * File Transfer Protocol (FTP) con Parallels Plesk Panel y cPanel@WHM
  * Microsoft Windows Server a través de procedimientos estándar de Windows utilizando el protocolo Common Internet File System (CIFS)
  
El almacenamiento de NAS y FTP se factura mensualmente y está disponible en distintos tamaños de almacenamiento. Puede interactuar con el almacenamiento de NAS y FTP en la línea de mandatos o el terminal con el sistema operativo, o bien a través de interacciones de apuntar y pulsar en los paneles del portal del cliente de infraestructura de {{site.data.keyword.cloud_notm}}.

Encontrará más información sobre NAS en un entorno {{site.data.keyword.cloud_notm}} en [Iniciación a NAS](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#getting-started-with-nas).

## Despliegue y gestión

Los {{site.data.keyword.baremetal_short}} {{site.data.keyword.cloud_notm}} se despliegan a través del portal del cliente de infraestructura de {{site.data.keyword.cloud_notm}} o la API, después de crear su cuenta de cliente de {{site.data.keyword.cloud_notm}}. Los servidores se pueden gestionar a través del portal del cliente, API o interfaz de línea de mandatos (CLI). Encontrará más información en [Acerca de los servidores nativos](https://console.bluemix.net/docs/bare-metal/index.html#about-bare-metal-servers).

## Soporte

El [Soporte a clientes de {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/support/index.html#getting-customer-support) trata cualquier pregunta y problemas que puedan surgir, a través de distintos canales, como chat, teléfono o incidencias. El soporte al cliente es gratuito para todos los clientes de {{site.data.keyword.cloud_notm}} y cubre la mayoría de las incidencias que se presentan a diario. Consulte [Obtención de soporte al cliente](https://console.bluemix.net./docs/support/index.html#getting-customer-support) para obtener más información.
