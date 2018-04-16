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


# Acerca de IBM Cloud para aplicaciones SAP
{: #about_ibmcloud_for_sap}

IBM y SAP llevan más de 45 años asociándose y colaborando en áreas como hardware, software, nube, servicios y financiación. La primera colaboración fue en 1972 y ha seguido creciendo gracias a cientos de clientes de SAP que utilizan {{site.data.keyword.cloud}} como solución de infraestructura como servicio(IaaS). {{site.data.keyword.IBM_notm}} ha seguido optimizando sus productos de infraestructura en nube para incluir soporte para la plataforma informática SAP NetWeaver. 

Gracias a esta relación, y a otras funcionalidades de {{site.data.keyword.cloud_notm}}, {{site.data.keyword.IBM_notm}} ha sido elegido como uno de los principales proveedores estratégicos de SAP en servicios de infraestructura en nube para sus aplicaciones críticas de negocio. El soporte para la suite de productos SAP NetWeaver está disponible a través de una {{site.data.keyword.cloud_notm}} altamente segura, abierta y escalable. Esta asociación permite que las aplicaciones basadas en SAP NetWeaver se expandan a los principales mercados, posibilitado por más de 60 centros de datos {{site.data.keyword.IBM_notm}} en todo el mundo.

La oferta presenta {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} con cuatro opciones de memoria:
  * 32 GB con un solo socket
  * 128 GB con socket dual
  * 256 GB con socket dual
  * 512 GB con socket dual

Las cuatro opciones están certificadas para SAP NetWeaver y proporcionan una plataforma en la nube de tipo empresarial, global, altamente segura y escalable para el despliegue rápido de aplicaciones SAP.

Puede utilizar sus servidores para entornos de producción, no producción o de pruebas (PoC). Todos los productos del servidor de aplicaciones SAP NetWeaver basados en ABAP y los productos del servidor de aplicaciones SAP NetWeaver basados en Java están soportados en {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}. Para los demás componentes de software, productos SAP no basados en SAP NetWeaver o productos de terceros, póngase en contacto con el [Soporte de SAP](https://support.sap.com/home.html), si los productos están soportados en las ofertas de IaaS.

## Modelo de oferta de {{site.data.keyword.cloud_notm}} para SAP NetWeaver
{: #offer_model}

La oferta de {{site.data.keyword.cloud_notm}} para aplicaciones SAP es ideal para prácticamente todos los casos de uso de SAP NetWeaver soportados en {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} sobre la red de {{site.data.keyword.cloud_notm}}.

La oferta consta de los siguientes servidores, sistemas operativos y bases de datos:
  * {{site.data.keyword.baremetal_short}} de {{site.data.keyword.cloud_notm}} en cuatro tamaños y el software que viene con cada servidor.
      * 4 núcleos con 32 GB de RAM
      * 24 núcleos con 128 GB de RAM
      * 24 núcleos con 256 GB de RAM
      * 28 núcleos con 512 GB de RAM
      
  * Sistema operativo o hipervisor
      * VMware vSphere ESXi 6.0 o 6.5 en el servidor
      * Sistema operativo Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X [SAP Business Warehouse (SAP BW) se soporta en producción en {{site.data.keyword.baremetal_short}} de {{site.data.keyword.cloud_notm}}]
      * Microsoft Windows Server (consulte la [Nota de SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) para obtener detalles de la versión)
      
  * Las bases de datos que se ofrecen son
      * Microsoft SQL Server for Windows (consulte la [Nota de SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) para obtener detalles de la versión)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Linux (consulte la [Nota de SAP 101809](https://launchpad.support.sap.com/#/notes/101809): Versiones soportadas y niveles de fixpack)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Windows (consulte la [Nota de SAP 101809-DB6](https://launchpad.support.sap.com/#/notes/101809): Versiones soportadas y niveles de fixpack)
      
Los {{site.data.keyword.baremetal_short}} de {{site.data.keyword.cloud_notm}} desplegados con VMware ESXi pueden ejecutar las versiones listadas de RHEL y Windows, las bases de datos de referencia y los productos de software basados en SAP NetWeaver. Los servidores no se pueden ejecutar en ningún otro sistema operativo o productos SAP no basados en SAP NetWeaver.

Consulte [SAP HANA en {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/doc/infrastructure/sap-hana/hana-index.html#getting-started) para obtener información sobre el despliegue de SAP HANA. Las futuras versiones de la oferta de {{site.data.keyword.cloud_notm}} para aplicaciones SAP incluyen soporte para otras bases de datos, alta disponibilidad y recuperación tras desastre.

Consulte la [Matriz de disponibilidad de productos SAP (PAM)](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630) para ver los requisitos específicos de SAP NetWeaver, sistema operativo y bases de datos para {{site.data.keyword.cloud_notm}}. Se necesita un ID S-user de SAP para acceder a SAP PAM.

## Red de {{site.data.keyword.cloud_notm}}
{: #ibm_cloud_network}

La {{site.data.keyword.cloud_notm}} proporciona más de 2.000 GB de conectividad en un espacio global de más de 60 centros de datos {{site.data.keyword.cloud_notm}} y 28 puntos de presencia (PoP). {{site.data.keyword.cloud_notm}} tiene conexiones de red de 20 Gbps en sus ubicaciones. Estas conexiones son proporcionadas por los principales proveedores de red del mundo e incluyen múltiples enlaces públicos de interconexión a docenas de redes de acceso a Internet adicionales.

La red tiene tres arquitecturas de red de gigabit redundantes y diferentes -pública, privada y centro de datos a centro de datos- que se integran perfectamente con la topología de red dentro de red del sector. Este diseño ofrece máxima accesibilidad, seguridad y control para la infraestructura de TI. Consulte [La red de IBM Cloud](https://www.ibm.com/cloud-computing/bluemix/our-network) para obtener más información.
