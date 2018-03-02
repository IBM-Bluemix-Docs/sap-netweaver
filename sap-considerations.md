---



copyright:
  years: 2017, 2018
lastupdated: "2018-03-02"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Items to consider when planning your SAP landscape
{: #considerations}

The SAP systems in a landscape have specific requirements for connectivity, either among each other or to external systems. You also need to think about external storage for your landscape, and what to do if you decide to deploy VMware on your server.

## Network connectivity
{: #network_connectivity}

[{{site.data.keyword.cloud_notm}} network](/docs/infrastructure/sap-netweaver/sap-about.html#ibm_cloud_network) provided an overview of the {{site.data.keyword.cloud}} approach to network connectivity. Issues with network connectivity can cause significant delays for your project if you do not plan appropriately, regardless of how you plan to use your system. 

In general, you have two interface choices for your IaaS-provisioned {{site.data.keyword.cloud_notm}} servers—the first is an external interface with a public IP. The second is an internal interface that is provided with a “private IP” in compliance with Request for Comment (RFC) 1918. You can also choose a single internal interface with a “private IP.” Both options can be made redundant through a Linux “bonding interface” or through Windows Network Interface Card (NIC) Teaming, and can be made available at a speed of 100 Mb/s, 1 Gb/s, and 10 Gb/s.

Depending on your use case, a public IP might be acceptable for proof-of-concept (PoC) landscapes because the external IP might be easier to use. A potential security risk exists even though a basic firewall is installed and preconfigured. If you want to use a public interface, be sure to choose a sufficiently high value for **Public Bandwidth** when you order your server. This value determines the total amount of data that can be transferred through the interface during a one-month period. While normal network communication, SAP graphical user interface (GUI) or SAP remote function call (RFC) traffic, might only sum up to a few megabytes per day, massive data uploads can easily exceed 1,000 GB per month. You either need to know the amount of data that is transferred at least by the order of magnitude or switch to the second option.

The second option accesses the {{site.data.keyword.cloud_notm}} Virtual Private Network (VPN) through the {{site.data.keyword.cloud_notm}} infrastructure customer portal, or deploys a security device into your landscape. The security devices are offered for firewalls, network address conversion, VPN access, and other network functions. Also, these security devices can provide you with a higher bandwidth, which help you in transferring larger amounts of data into an {{site.data.keyword.cloud_notm}} data center. It is advised that your networking department speak with [{{site.data.keyword.cloud_notm}} Support](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support) after the layout of your landscape and the connectivity that is required on the SAP application layer are determined.

### VLANs
{: #vlans}

If you want to separate different types of network traffic in your landscape, you can order more virtual LANs (VLANs). Keep in mind that the additional VLANs only lead to traffic segregation, not increased performance. Traffic segregation needs to be considered with elaborate VMware-based deployments, where different kinds of network traffic might need to be more strictly separated for security reasons.

For the following use cases, you might want to make sure that all servers are on the same VLAN during deployment:
  *	Multiple servers exchanging data, such as a three-tier SAP setup—database and SAP application instances on different servers
  *	Multiple systems that exchange large amounts of data

For an SAP deployment with local storage, even for three-tier setups, 1 Gb-based networks are sufficient. More factors might have to be considered; see [External storage](/docs/infrastructure/sap-netweaver/sap-considerations.html#external_storage) for more information on your network storage choices.

### Hybrid setups
{: #hybrid}

The {{site.data.keyword.cloud_notm}} for SAP Applications offering can be thought of as an external data center,especially if you are thinking of implementing a hybrid landscape with some SAP systems at an {{site.data.keyword.cloud_notm}} data center and other systems on site. Some specific configuration items that need to be considered as part of your project’s planning phase with a hybrid setup:

  *	[SAP Transport Management System (STMS)](https://help.sap.com/saphelp_me60/helpdata/en/c4/6045377b52253de10000009b38f889/frameset.htm). Configure it based on Transport Groups to prevent file sharing across data centers.
  *	[SAProuter](https://support.sap.com/en/tools/connectivity-tools/saprouter.html). Provides access to SAP On-Line Service System (OSS). Use your on-premises SAProuter, which is already available, to access the OSS. This SAProuter can be used through further SAProuter hops if IP-based routing is not permitted between your {{site.data.keyword.cloud_notm}}-based systems and your on-premises SAProuter. Alternatively, you might consider setting up another SAProuter that is based on one {{site.data.keyword.cloud_notm}}-based server with a public IP and connect it to the SAP OSS system through the internet.
  *	[SAP Solution Manager](https://support.sap.com/en/solution-manager.html). Access to the SAP Solution Manager has different connectivity requirements between an SAP Solution Manager and its managed systems, depending on your usage scenario. These scenarios require an understanding of the required network connectivity.  

## External storage
{: #external_storage}

Local storage provides the best performance for your database deployment. In addition to the local storage, you might require more external storage to perform backups, or your SAP systems’ database might exceed the storage capacity of the internal disks. Another example is your project requirements might demand external storage; like for multiple ESX-based servers, which want to share virtual machines (VMs). For these requirements, you can order block storage or Network Attached Storage (NAS) as described in [Storage](/docs/infrastructure/sap-netweaver/sap-general-iaas-concepts.html#storage). Since extra block storage and NAS data is transferred through the same physical adapters as all other network traffic, the impact needs to be kept in mind. Performance numbers comparable to the numbers measured in the certification benchmarks might merely be achievable.

It is recommended that you choose a 10 Gb-based data center for your deployment if you are planning to primarily use external storage instead of local storage. For example, the external storage is used for both backup and for your database, and if you are planning to put a high load on your SAP system. If you are close to over-loading a 1 Gb network with a 90 MB/s I/O load.

Another recommendation is that you use at least 4 IOPS/GB if your database resides primarily on external storage. Slower storage should only be used if database performance is not critical for your project or for backup purposes.

If you are planning to use external storage as data stores for VMware ESX, follow the decision guidelines under [Storage to use with VMware Systems](https://console.bluemix.net/docs/infrastructure/vmware/select-storage-option-use-vmware.html#storage-to-use-with-vmware-systems) to determine the optimal storage type for your use case.

## VMware ESXi server deployments
{: #vmware_server}

VMware ESXi-based deployments in {{site.data.keyword.cloud_notm}} are different from other cloud-based deployments. {{site.data.keyword.cloud_notm}} does not provide its customers with running VMs; you take control of your environment and configure it to meet your requirements. You receive a configured server when you order a VMware ESX server. The following links provide information on additional storage and running guest VMs.

  *	[Storage to use with VMware Systems](https://console.bluemix.net/docs/infrastructure/vmware/select-storage-option-use-vmware.html#storage-to-use-with-vmware-systems) provides further direction on how to integrate storage in an ESX environment.
  * [Mounting iSCSI VMware ESXi](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi) describes the steps to integrate iSCSI-based storage with ESX.
  * [Creating a VMware ESX Virtual Machine](https://console.bluemix.net/docs/infrastructure/vmware/vmware-esx-create-virtual-machine.html#creating-a-vmware-esx-virtual-machine) guides you through the process of deploying your first VM.

Keep in mind that for deploying SAP NetWeaver-based software in the guest OS, you have to choose the guest OS from the operating systems mentioned in [SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097).
