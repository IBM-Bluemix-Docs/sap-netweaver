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

# Getting started tutorial
{: #getting-started}

{{site.data.keyword.IBM_notm}} and SAP continue a 40-year collaboration in multiple areas, including hardware, software, cloud, services, and finance. They are now collaborating to run SAP NetWeaver-based applications on {{site.data.keyword.baremetal_long}}. The offering features four memory options, single socket (32 GB) and dual sockets (128 GB, 256 GB, and 512 GB). These memory options are all available in the more than 60 {{site.data.keyword.cloud_notm}} data centers worldwide.
{: shortdesc}

This content provides you with recommendations for the provisioning and installation of the infrastructure to support SAP NetWeaver-based SAP products and subscription on {{site.data.keyword.cloud_notm}}. It does not replace to any SAP NetWeaver implementation-related documentation. Its purpose is to help you with infrastructure planning and provisioning so you can begin your SAP installation. The SAP installation (including database installation) does not vary from installations for on-premises environments. Recommendations and guidelines are provided to help you operate your SAP system in the {{site.data.keyword.cloud_notm}} environment.

Table 1 contains steps to help you get your {{site.data.keyword.cloud_notm}} infrastructure built quickly.
<table>
   <CAPTION>Table 1. Quick start steps</CAPTION>
   <THEAD>
   <TR>
   <th>Task</th>
   <th>Details</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>1. Read IBM Cloud and SAP content that is related to your implementation</td>
   <td>If your organization is new to IBM Cloud, read the following information before your planning phase.
   <li><a href="https://ibm.com/cloud-computing/">What is IBM Cloud</a></li>
   <li><a href="https://ibm.com/cloud/get-started">Getting started with IBM Cloud</a></li>
   <li><a href="https://help.sap.com/nw75#section2">SAP NetWeaver 7.5 installation and upgrade information</a>: download the installation guide</li>

   You might also find the following SAP documentation useful:
   <li><a href="https://www.youtube.com/watch?v=4wICiRTP8u0/">How to create an SAP S-user ID</a>. Note that only super administrators or S-users with the required authorization are allowed to create S-user IDs.</li>
   <li><a href="https://help.sap.com/netweaver">SAP NetWeaver Help</a></li>
   <li><a href="https://support.sap.com">SAP Notes through the SAP Support Portal</a>; requires an SAP S-user ID</li>
   </td>
   <tr>
   <td>2. Sign up for IBM Cloud</td>
   <td>See <a href="https://cloud.ibm.com/docs/account/adminpublic.html#signing-up-for-ibm-cloud">Signing up for IBM Cloud</a> for the steps on how to set up your IBM Cloud account.</td>
 <tr>
   <td>3. Access the IBM Cloud infrastructure customer portal</td>
   <td>The <a href="https://control.softlayer.com">IBM Cloud infrastructure customer portal</a> is your graphical gateway to all your infrastructure components-compute, connectivity, storage, network, and data centers. You need an <a href="https://console.bluemix.net/docs/customer-portal/getting-started.html#getting-started">IBMid and password</a> to access the customer portal.</td>
   <tr>
   <td>4. Plan your system landscape</td>
   <td>Use the information in <a href="sap-netweaver?topic=sap-netweaver-planning-your-system-landscape#planning-your-system-landscape">Planning your system landscape</a> to architect, size, and provision your IBM Cloud environment to support your SAP NetWeaver workload.</td>  
 <tr>
   <td>5. Provision your system</td>
   <td>Use the steps and information in <a href="sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment">Provisioning your SAP NetWeaver environment</a> to set up your IBM Cloud infrastructure. You can also use the steps in the Quick Reference Guides.</td>
   <tr>
   <td>6. Install SAP NetWeaver</td>
   <td>Install SAP NetWeaver on your IBM Cloud infrastructure the same as if the servers were on-premises. For more information about installing SAP NetWeaver, see <a href="sap-netweaver?topic=sap-netweaver-install_sap#install_sap">Downloading and installing SAP software and applications</a> for more information.</td>
   </td>
   </tr>
   </TBODY>
   </table>
