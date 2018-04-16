---



copyright:
  years: 2017, 2018
lastupdated: "2018-02-27"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Guía de aprendizaje de iniciación a IBM Cloud para aplicaciones SAP
{: #getting-started}

{{site.data.keyword.IBM_notm}} y SAP llevan más de 40 años colaborando en muchas áreas, incluyendo hardware, software, nube, servicios y finanzas. Ahora están colaborando para ejecutar aplicaciones basadas en SAP NetWeaver en {{site.data.keyword.baremetal_long}}. La oferta presenta cuatro opciones de memoria, un solo socket (32 GB) y sockets duales (128 GB, 256 GB y 512 GB), que están disponibles en los más de 60 centros de datos {{site.data.keyword.cloud_notm}} en todo el mundo.
{: shortdesc}

Este contenido le brinda recomendaciones para el suministro y la instalación de la infraestructura para dar soporte a los productos SAP basados en SAP NetWeaver y la suscripción en {{site.data.keyword.cloud_notm}}. No sustituye a ninguna documentación relacionada con la implementación de SAP NetWeaver. Su finalidad es ayudarle con la planificación y el suministro de la infraestructura para que pueda iniciar la instalación de SAP. La instalación de SAP (incluyendo la instalación de la base de datos) no varía entre instalaciones para entornos en local. Se proporcionan recomendaciones y directrices para ayudarle a operar el sistema SAP en el entorno {{site.data.keyword.cloud_notm}}.

La Tabla 1 contiene los pasos para construir rápidamente la infraestructura de {{site.data.keyword.cloud_notm}}.
<table>
   <CAPTION>Tabla 1. Pasos de inicio rápido</CAPTION>
   <THEAD>
   <TR>
   <th>Tarea</th>
   <th>Detalles</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>1. Lea el contenido de IBM Cloud y SAP relacionado con su implementación</td>
   <td>Si su empresa es nueva en IBM Cloud, la siguiente información puede ser útil y debe leerse antes de la fase de planificación.
   <li><a href="https://ibm.com/cloud-computing/">Qué es IBM Cloud</a></li>
   <li><a href="https://ibm.com/cloud/get-started">Iniciación a IBM Cloud</a></li>
   <li><a href="https://help.sap.com/nw75#section2">Información de instalación y actualización de SAP NetWeaver 7.5</a>: descargar la guía de instalación</li>
   
   La siguiente documentación de SAP también le puede resultar útil:
   <li><a href="https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77/">Cómo configurar un ID S-user de SAP</a></li>
   <li><a href="https://help.sap.com/netweaver">Ayuda de SAP NetWeaver</a></li>
   <li><a href="https://support.sap.com">Notas de SAP</a>; requiere un ID S-user de SAP</li>
   </td>
   <tr>
   <td>2. Regístrese en IBM Cloud</td>
   <td>Visite <a href="https://console.bluemix.net/docs/admin/adminpublic.html#signing-up-for-ibm-cloud">Registro de IBM Cloud</a> para conocer los pasos sobre cómo configurar su cuenta de IBM Cloud.</td>
 <tr>
   <td>3. Acceda al portal del cliente de infraestructura de IBM Cloud</td>
   <td>El <a href="https://control.softlayer.com">portal del cliente de infraestructura de IBM Cloud</a> es su pasarela gráfica a todos los componentes de la infraestructura: cálculo, conectividad, almacenamiento, red y centros de datos. Necesita un <a href="https://console.bluemix.net/docs/customer-portal/getting-started.html#getting-started">IBMid y contraseña</a> para acceder al portal del cliente.</td> 
   <tr>
   <td>4. Planifique su entorno de sistemas</td>
   <td>Utilice la información de <a href="sap-planning-your-system-landscape.html#planning-your-system-landscape">Planificación de su entorno de sistemas</a> para determinar la arquitectura y el tamaño y suministrar su entorno IBM Cloud para dar soporte a la carga de trabajo de SAP NetWeaver.</td>  
 <tr>
   <td>5. Suministre su sistema</td>
   <td>Utilice los pasos y la información de <a href="sap-provision-environment.html#provision_environment">Suministro de su entorno SAP NetWeaver</a> para configurar su infraestructura de IBM Cloud. También puede utilizar los pasos de las Guías de consulta rápida.</td>
   <tr>
   <td>6. Instale SAP NetWeaver</td>
   <td>Instale SAP NetWeaver en su infraestructura de IBM Cloud como si los servidores estuvieran en local. Consulte <a href="sap-installing-SAP-landscape.html#install_sap">Descarga e instalación de software y aplicaciones SAP</a> para obtener más información.</td>
   </td>
   </tr>
   </TBODY>
   </table>
