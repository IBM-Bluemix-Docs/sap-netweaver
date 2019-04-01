---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.Db2_on_Cloud_short}}, FAQs, VLAN, application server, SAP Certified, high availability, highly available

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Preguntas más frecuentes: SAP on IBM Cloud
{: #faqs}

## ¿Necesito DB2 para ejecutar SAP NetWeaver en {{site.data.keyword.cloud_notm}}?
{: faq}

Consulte la [Nota de SAP 2414097 ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} con regularidad, así como la [Matriz de disponibilidad de productos SAP ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: new_window}. Tenga en cuenta el sistema operativo proporcionado en la Nota de SAP, ya que la base de datos requiere distintos conjuntos de Service Packs.

## ¿Por qué se ha elegido {{site.data.keyword.Db2_on_Cloud_short}} para la certificación de {{site.data.keyword.cloud_notm}}?
{: faq}

Porque {{site.data.keyword.Db2_on_Cloud_long_notm}} es un producto de {{site.data.keyword.IBM_notm}} y {{site.data.keyword.cloud_notm}} forma parte de {{site.data.keyword.IBM_notm}} elegido para nuestra certificación.

## ¿Puedo dividir mi entorno SAP distribuido entre distintos centros de datos?
{: faq}

Para una instalación SAP distribuida, es mejor tener todos los nodos en el mismo centro de datos y segmento VLAN. De lo contrario, podría generarse latencia y tiempos de espera excedidos, afectando a la capacidad de respuesta del sistema SAP.

## ¿Puedo conseguir la alta disponibilidad de SAP como se define en la arquitectura SAP?
{: faq}

La única arquitectura de alta disponibilidad soportada es el escalado de servidores de aplicaciones. Actualmente, no hay hardware habilitado para dar soporte a alta disponibilidad.

## ¿Puedo descargar el software de distribución de SAP directamente desde {{site.data.keyword.cloud_notm}}?
{: faq}

Actualmente, no ofrecemos un enlace directo con [SAP Service Marketplace ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono enlace externo")](https://websmp201.sap-ag.de/){: new_window}. Por tanto, tiene que descargarse los DVD de distribución como si se tratara de un despliegue en local.
