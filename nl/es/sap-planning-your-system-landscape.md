---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, SAP landscape, SAP Business Suite, SAP Business Warehouse, SAP BW

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: .faq}

# Planificación del entorno de sistemas
{: #planning-your-system-landscape}

Un *entorno* SAP es un grupo de dos o más *sistemas* SAP, que normalmente incluyen desarrollo, calidad y pruebas y producción. Un sistema SAP consta de una o más *instancias de SAP*, que son un grupo de procesos que se inician y detienen al mismo tiempo. Para obtener más información sobre los entornos SAP, consulte [*SAP Business Suite sobre la arquitectura de referencia de IBM X6 Systems* ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://lenovopress.com/redp5073.pdf){: new_window}.
{: shortdesc}

Existen varias posibles configuraciones de entorno, como servidor (tamaño)/almacenamiento (tamaño), para todas las soluciones SAP del mercado. Estas soluciones incluyen productos basados en SAP NetWeaver, como [SAP Business Suite ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://open.sap.com/courses/suitehana1){: new_window}, SAP Business Warehouse y todos los complementos específicos de SAP, que admiten los servidores de {{site.data.keyword.cloud}} SAP-Certified Infrastructure. Otras soluciones a tener en cuenta son las soluciones SAP no basadas en SAP NetWeaver y software de terceros que puedan integrarse con SAP. Póngase en contacto con el [Soporte de SAP ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://support.sap.com/en/index.html){: new_window} si tiene previsto desplegar software no basado en SAP NetWeaver o de terceros en su entorno de IaaS de {{site.data.keyword.cloud}}.

Intente ser lo más detallado posible al determinar el tamaño de su servidor sobre la base de las aplicaciones que tiene previsto ejecutar, el crecimiento potencial y el rendimiento. Además, tenga en cuenta los requisitos de memoria y almacenamiento para sus aplicaciones. Los sistemas SAP en un entorno tienen requisitos específicos para la conectividad, ya sea entre ellos o bien con sistemas externos. Para obtener más información, consulte [Aspectos a considerar cuando planifique su entorno SAP](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations).

La Tabla 1 contiene los pasos del proceso de planificación. Aplíquela para crear su entorno SAP de destino.

Tabla 1. Visión general del proceso de planificación

| Paso | Detalles |
| --- | --- |
| 1 | [Obtención de credenciales de SAP y {{site.data.keyword.cloud_notm}} y creación de cuentas](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-get_sap_ibm_credentials#get_sap_ibm_credentials) |
| 2 | [Revisión de la documentación de SAP y {{site.data.keyword.cloud_notm}} relevante](/docs/infrastructure/sap-netweaver/sap-review-doc.html) |
| 3 | [Determinación de sus aplicaciones SAP NetWeaver](/docs/infrastructure/sap-netweaver/sap-determine-apps.html) |
| 4 | [Dimensionamiento del servidor](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server) |
| 5 | [Determinación de la configuración](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration) |

## Siguientes pasos

Seleccione el paso correspondiente en la Tabla 1 para empezar a planificar su entorno SAP.
