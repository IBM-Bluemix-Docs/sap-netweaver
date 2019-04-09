---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, SAP certified servers, SAP Certified, database,

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Tutoriel d'initiation
{: #getting-started}

{{site.data.keyword.IBM_notm}} et SAP collaborent depuis plus de 40 ans sur différentes solutions (matériel, logiciel, cloud, services et financement). Aujourd'hui, leur travail porte sur le développement d'applications SAP NetWeaver à exécuter sur des serveurs IBM Bare Metal. L'offre comporte quatre options de mémoire, un socket unique (32 Go) et des sockets doubles (128 Go, 256 Go et 512 Go).
Ces options de mémoire sont disponibles dans plus de 60 centres de données {{site.data.keyword.cloud_notm}} dans le monde entier.
{: shortdesc}

La présente section offre des conseils sur les procédures de mise à disposition et d'installation de l'infrastructure de manière à prendre en charge les produits SAP NetWeaver, et d'inscription sur {{site.data.keyword.cloud_notm}}. Celle-ci ne remplace pas la documentation relative à l'implémentation de SAP NetWeaver. Elle a pour but de vous assister lorsque vous planifiez votre infrastructure et la mettez à disposition, pour que vous puissiez lancer l'installation de SAP. Celle-ci (avec l'installation de la base de données) est identique aux installations pour les environnements locaux. Les recommandations et les bonnes pratiques sont fournies pour vous aider à exécuter votre système SAP dans l'environnement {{site.data.keyword.cloud_notm}}.

Le tableau 1 contient des étapes permettant de générer votre produit {{site.data.keyword.cloud_notm}} Infrastructure rapidement.
<table>
   <CAPTION>Tableau 1. Etapes de démarrage rapide</CAPTION>
   <THEAD>
   <TR>
   <th>Tâche</th>
   <th>Détails</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>1. Lisez la documentation IBM Cloud et SAP relative à votre implémentation</td>
   <td>Si votre organisation découvre IBM Cloud, lisez les informations ci-dessous avant la phase de planification :
   <li><a href="https://ibm.com/cloud-computing/">Qu'est-ce qu'IBM Cloud ?</a></li>
   <li><a href="https://ibm.com/cloud/get-started">Get started with IBM Cloud</a></li>
   <li><a href="https://help.sap.com/nw75#section2">SAP NetWeaver 7.5 installation and upgrade information</a> : guide d'installation à télécharger (en anglais)</li>

   La documentation SAP suivante peut également vous être utile :
   <li><a href="https://www.youtube.com/watch?v=4wICiRTP8u0/">How to create an SAP S-user ID</a>. Notez que seuls les administrateurs centraux ou les utilisateurs S-user possédant les droits requis sont autorisés à créer des identifiants SAP S-user. </li>
   <li><a href="https://help.sap.com/netweaver">SAP NetWeaver Help</a></li>
   <li><a href="https://support.sap.com">SAP Notes through the SAP Support Portal</a> ; requiert un identifiant SAP S-user.</li>
   </td>
   <tr>
   <td>2. Inscrivez-vous à IBM Cloud</td>
   <td>Voir <a href="https://cloud.ibm.com/docs/account/adminpublic.html#signing-up-for-ibm-cloud">Signing up for IBM Cloud</a> pour les étapes à suivre pour configurer votre compte IBM Cloud.</td>
 <tr>
   <td>3. Accédez au portail IBM Cloud Infrastructure Customer Portal.</td>
   <td>Le portail <a href="https://control.softlayer.com">IBM Cloud Infrastructure Customer Portal</a> constitue votre passerelle graphique vers vos composants d'infrastructure (calcul, connectivité, stockage, réseau et centres de données). Vous avez besoin d'un <a href="https://console.bluemix.net/docs/customer-portal/getting-started.html#getting-started">IBMid et d'un mot de passe</a> pour accéder au portail client.</td>
   <tr>
   <td>4. Planifiez le paysage de votre système</td>
   <td>Utilisez les informations de la rubrique <a href="sap-netweaver?topic=sap-netweaver-planning-your-system-landscape#planning-your-system-landscape">Planification de votre paysage système</a> pour créer l'architecture, définir la taille et mettre à disposition votre environnement IBM Cloud en vue de prendre en charge votre charge de travail SAP NetWeaver.</td>  
 <tr>
   <td>5. Mettez à disposition votre système</td>
   <td>Utilisez les étapes et les informations de la rubrique <a href="sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment">Mise à disposition de votre environnement SAP NetWeaver</a> pour configurer votre infrastructure IBM Cloud. Vous pouvez également suivre les étapes expliquées dans l'aide-mémoire.</td>
   <tr>
   <td>6. Installez SAP NetWeaver</td>
   <td>Installez SAP NetWeaver sur votre infrastructure IBM Cloud comme vous le feriez si les serveurs se trouvaient sur site. Pour plus d'informations sur l'installation de SAP NetWeaver, voir <a href="sap-netweaver?topic=sap-netweaver-install_sap#install_sap">Téléchargement et installation des logiciels et des applications SAP</a>. </td>
   </td>
   </tr>
   </TBODY>
   </table>
