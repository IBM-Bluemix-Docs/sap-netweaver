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


# Soporte de alta disponibilidad de IBM Cloud
{: #ha}

La infraestructura como servicio (IaaS) de {{site.data.keyword.cloud}} ofrece un sólido entorno de cálculo con un despliegue de sistema operativo (SO) opcional sobre él que admite soluciones de alta disponibilidad (HA). La solución se basa en la versión soportada de sistema operativo, que se describe en la [Nota de SAP 2414097 ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}. La solución de alta disponibilidad está restringida a las licencias de sistema operativo solicitadas que se incluyen con el despliegue, o a las licencias de terceros, como BYOL (traiga su propia licencia). Comente los detalles de la alta disponibilidad con el Soporte de {{site.data.keyword.cloud_notm}} antes del despliegue.

Los sistemas operativos admitidos y desplegados por {{site.data.keyword.cloud_notm}} para SAP son:
* Linux [Red Hat Enterprise Linux (RHEL) o SUSE Enterprise Linux Server (SLES)] es compatible con las soluciones de alta disponibilidad de SAP NetWeaver y SAP HANA. Existen restricciones menores en el entorno de {{site.data.keyword.cloud_notm}}, que se describen en [Visión general de las configuraciones de alta disponibilidad de SAP NetWeaver](#overview-configs).
* Microsoft Windows sólo admite la solución de alta disponibilidad de SAP NetWeaver (debido a las limitaciones de base de datos SAP HANA).

## Visión general de las configuraciones de alta disponibilidad de SAP NetWeaver
{: #overview-configs}

Existen muchos documentos que proporcionan ayuda detallada sobre la planificación y la instalación de un entorno de alta disponibilidad para servicios SAP. Los documentos incluyen información sobre la migración tras error, la réplica, el escalado y la recuperación tras desastre (DR). Se proporcionan referencias a determinados documentos si corresponde.

Todos los sistemas operativos y las distribuciones admitidas por {{site.data.keyword.cloud_notm}} para los despliegues de SAP (Windows, Linux RHEL y SLES) incluyen extensiones específicas y software de alta disponibilidad. A continuación, se indican los sistemas operativos y las distribuciones admitidas.

* En [Nuevas mejoras de clústeres de migración tras error en Windows Server 2012 y sus ventajas para SAP NetWeaver de alta disponibilidad ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://blogs.sap.com/2013/10/16/new-failover-clustering-improvements-in-windows-server-2012-and-its-benefits-for-sap-netweaver-high-availability/){: new_window} se ofrece una descripción basada en los clústeres de migración tras error de Microsoft Windows Server (WFSC) sobre el sistema operativo Windows con SAP NetWeaver.

* Hay dos referencias de instrucciones de despliegue de SAP NetWeaver en un entorno de alta disponibilidad basado en Linux con Linux Pacemaker:
  * Guía de configuración del clúster de alta disponibilidad de SUSE SAP NetWeaver 7.40
  * Despliegue de servidores basados en SAP NetWeaver de alta disponibilidad mediante el complemento de alta disponibilidad de Red Hat Enterprise Linux con Pacemaker

* El documento [Alta disponibilidad para SAP NetWeaver y SAP HANA en Linux ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://support.sap.com/content/dam/SAAP/SAP_Activate/AGS_70.pdf){: new_window} de prácticas recomendadas ofrece una descripción técnica detallada especialmente para SAP HANA.

* En [Alta disponibilidad y continuidad de negocio de SAP NetWeaver en entornos virtuales con VMware e Hyper-V en Microsoft Windows ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.sap.com/documents/2015/07/508b62bc-5b7c-0010-82c7-eda71af511fa.html){: new_window} se tratan cuestiones de virtualización útiles si tiene previsto implementar la alta disponibilidad en servidores virtualizados.

Para conocer más productos de alta disponibilidad certificados por partners de SAP para casos de alta disponibilidad, consulte [Información de socios de alta disponibilidad ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://wiki.scn.sap.com/wiki/display/SI/High+Availability+Partner+Information){: new_window}.
Para bases de datos que no sean SAP HANA, la documentación de la base de datos contiene más información sobre la migración tras error de alta disponibilidad y las configuraciones de DR.

Tenga en cuenta que suele ser necesario el acceso compartido a almacenamiento Network File System (NFS)/Common Internet File System (CIFS) o a almacenamiento Logical Unique Number (LUNS) basado en iSCSI para poder disponer de migración tras error del sistema. Por lo general, para una configuración de tipo DR, es necesario almacenamiento local combinado con un método de réplica. Del mismo modo que con las instalaciones locales, cuando planifique el despliegue, compruebe los requisitos de rendimiento y latencia del producto de base de datos.

## Instrucciones adicionales
{: #extra-guide}

En [Almacenamiento basado en quórum](#quorum) y [Consideraciones de red](#network) se incluyen instrucciones que debe tener en cuenta durante el despliegue. Aparte de las consideraciones descritas en estas secciones, la instalación de SAP NetWeaver y su sistema de base de datos en un entorno de alta disponibilidad no varía con respecto a otras instalaciones locales.

### Almacenamiento basado en quórum
{: #quorum}

A causa de las restricciones de seguridad del entorno de {{site.data.keyword.cloud_notm}} IBM Cloud, el acceso basado en red a los dispositivos gestión remota mediante Intelligent Platform Management Interface (IPMI) no está disponible. Los entornos de clúster suelen utilizar componentes basados en IPMI para las “barreras de nodos de clúster” para garantizar siempre un quórum. A falta de dispositivos habilitados para IPMI, se utilizan dispositivos de almacenamiento compartido. En un entorno de {{site.data.keyword.cloud_notm}}, los dispositivos de almacenamiento compartido se implementan desplegando un LUN iSCSI en los servidores como dispositivo de quórum. Por ejemplo, un FSW (File Share Witness) en un clúster de Microsoft, y SBD (Storage-Based Death) para Stonith de Linux Pacemaker.
* Pulse [aquí ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://linux-ha.org/wiki/Cluster_Concepts){: new_window} para obtener más información sobre los conceptos de clúster de alta disponibilidad de Linux.
* Pulse [aquí ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://docs.microsoft.com/en-us/windows-server/failover-clustering/manage-cluster-quorum){: new_window} para obtener más información sobre la configuración y la gestión de los servidores de quórum para Windows Server 2012 y Windows Server 2012 R2.

El almacenamiento de {{site.data.keyword.cloud_notm}} tiene funciones de alta disponibilidad incorporadas, de modo que un único LUN iSCSI compartido no introducirá ningún punto único de anomalía (SPOF), porque el diseño de red es redundante. No obstante, las características específicas del producto de clúster pueden requerir varios dispositivos de quórum.

### Consideraciones de red
{: #network}

Las instalaciones basadas en {{site.data.keyword.cloud_notm}} incluyen una de las siguientes configuraciones de red:
* Red privada
* Red pública
* Una red pública y una red privada
* Dos redes privadas (como solicitud especial)

Del mismo modo que las instalaciones locales, se pueden solicitar adaptadores de red adicionales en función de las restricciones físicas del hardware. La restricción es la misma para las instalaciones locales. Solicitar adaptadores de red redundantes durante los despliegues de hardware permite evitar los SPOF en la topología de red. Los adaptadores redundantes se configuran con migración tras error con Link Aggregation Control Protocol (LACP). Para Linux, la configuración utiliza interfaces de acoplamiento, y se utilizan adaptadores de agrupación para Microsoft Windows. La infraestructura de conmutador de {{site.data.keyword.cloud_notm}} a la que están conectados estos adaptadores es redundante, por lo que no se introducen nuevos SPOF. La infraestructura redundante se puede utilizar en las VLAN solicitadas.

En función de los requisitos de red, como los casos de réplica de una configuración de DR, debe comprobar la ubicación de los dispositivos conectados y los requisitos nuevos de red específicos del producto en cuestión. En algunos casos, puede que la réplica basada en almacenamiento de instantánea de {{site.data.keyword.cloud_notm}} cumpla los requisitos que necesite. Consulte con el Soporte de {{site.data.keyword.cloud_notm}} para determinar la solución más apropiada para su proceso de negocio.
