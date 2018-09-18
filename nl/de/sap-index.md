---



copyright:
  years: 2017, 2018
lastupdated: "2018-08-10"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Lernprogramm zur Einführung
{: #getting-started}

Seit über 40 Jahren arbeiten {{site.data.keyword.IBM_notm}} und SAP in Bereichen wie Hardware, Software, Cloud, Services und Finanzen zusammen. Nun konzentriert sich diese Zusammenarbeit auf die Ausführung von SAP NetWeaver-basierten Anwendungen für {{site.data.keyword.baremetal_long}}. Das Angebot umfasst vier Speicheroptionen, Single-Socket (32 GB) und Dual-Sockets (128 GB, 256 GB und 512 GB), die alle in den mehr als 60 {{site.data.keyword.cloud_notm}}-Rechenzentren weltweit zur Verfügung stehen.
{: shortdesc}

In diesem Abschnitt finden Sie Empfehlungen für die Bereitstellung und Installation der nötigen Infrastruktur für die Unterstützung von SAP NetWeaver-basierten SAP-Produkten und das Abonnieren von {{site.data.keyword.cloud_notm}}. Diese Informationen sind jedoch kein Ersatz für Dokumentationen, die sich auf die Implementierung von SAP NetWeaver beziehen. Die Informationen sollen Ihnen bei der Planung und Bereitstellung der Infrastruktur helfen, damit Sie mit der SAP-Installation beginnen können. Die SAP-Installation (einschließlich Datenbankinstallation) unterscheidet sich nicht von Installationen für lokale Umgebungen. Die hier bereitgestellten Empfehlungen und Richtlinien sollen Sie beim Betrieb des SAP-Systems in der {{site.data.keyword.cloud_notm}}-Umgebung unterstützen.

Tabelle 1 enthält Schritte zum schnellen Erstellen der {{site.data.keyword.cloud_notm}}-Infrastruktur.
<table>
   <CAPTION>Tabelle 1. Schritte für den Schnelleinstieg</CAPTION>
   <THEAD>
   <TR>
   <th>Task</th>
   <th>Details</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>1. Lesen Sie sich IBM Cloud- und SAP-Inhalte durch, die für Ihre Implementierung interessant sind.</td>
   <td>Wenn Ihre Organisation noch nicht mit IBM Cloud vertraut ist, können die folgenden Informationen hilfreich sein und sollten vor der Planungsphase gelesen werden.
   <li><a href="https://ibm.com/cloud-computing/">Was ist IBM Cloud?</a></li>
   <li><a href="https://ibm.com/cloud/get-started">Einführung in IBM Cloud</a></li>
   <li><a href="https://help.sap.com/nw75#section2">Installations- und Upgradeinformationen zu SAP NetWeaver 7.5</a>: Laden Sie das Installationshandbuch herunter.</li>
   
   Zudem kann die folgende SAP-Dokumentation hilfreich sein:
   <li>Veröffentlichung zur <a href="https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77/">Vorgehensweise beim Festlegen einer SAP S-User-ID</a></li>
   <li><a href="https://help.sap.com/netweaver">Hilfe für SAP NetWeaver</a></li>
   <li><a href="https://support.sap.com">SAP-Hinweise</a>; Hierfür ist eine SAP S-User-ID erforderlich.</li>
   </td>
   <tr>
   <td>2. Bei IBM Cloud anmelden</td>
   <td>Unter <a href="https://console.bluemix.net/docs/admin/adminpublic.html#signing-up-for-ibm-cloud">Bei IBM Cloud anmelden</a> finden die Schritte zum Einrichten Ihres IBM Cloud-Kontos.</td>
 <tr>
   <td>3. Auf das Kundenportal für die IBM Cloud-Infrastruktur zugreifen</td>
   <td>Das <a href="https://control.softlayer.com">Kundenportal für die IBM Cloud-Infrastruktur</a> ist Ihr grafisch orientiertes Gateway zu allen Infrastrukturkomponenten: Berechnung, Konnektivität, Speicher, Netz und Rechenzentren. Für den Zugriff auf das Kundenportal benötigen Sie eine <a href="https://console.bluemix.net/docs/customer-portal/getting-started.html#getting-started">IBMid und ein Kennwort</a>.</td> 
   <tr>
   <td>4. Systemlandschaft planen</td>
   <td>Verwenden Sie die Informationen unter <a href="sap-planning-your-system-landscape.html#planning-your-system-landscape">Systemlandschaft planen</a>, um Ihre IBM Cloud-Umgebung zur Unterstützung der SAP NetWeaver-Arbeitslasten maßgeschneidert zu gestalten und bereitzustellen.</td>  
 <tr>
   <td>5. System bereitstellen</td>
   <td>Verwenden Sie die Schritte und Informationen unter <a href="sap-provision-environment.html#provision_environment">SAP NetWeaver-Umgebung bereitstellen</a>, um Ihre IBM Cloud-Infrastruktur einzurichten. Sie können dabei auch auf die entsprechenden Schritte in den Kurzübersichten zurückgreifen.</td>
   <tr>
   <td>6. SAP NetWeaver installieren</td>
   <td>Sie installieren SAP NetWeaver in Ihrer IBM Cloud-Infrastruktur genau so, als ob die Server sich vor Ort befänden. Weitere Informationen finden Sie unter <a href="sap-installing-SAP-landscape.html#install_sap">SAP-Software und -Anwendungen herunterladen und installieren</a>.</td>
   </td>
   </tr>
   </TBODY>
   </table>
