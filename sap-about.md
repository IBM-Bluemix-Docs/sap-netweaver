---

copyright:
  years: 2017, 2019
lastupdated: "2019-06-04"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.baremetal_short}}, ABAP, application server, SAP Product Availability Matrix, PAM, SAP Certified, SAP Content Server, SAP liveCache

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external: target="_blank" .external}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:note: .note}
{:faq: .faq}


# About IBM Cloud SAP-Certified Infrastructure
{: #about_ibmcloud_for_sap}

IBM and SAP have been teaming, partnering, and collaborating in areas that include hardware, software, cloud, services, and financing for over 45 years. The first collaboration was in 1972 and has continued to grow with hundreds of SAP clients that use {{site.data.keyword.cloud}} as their infrastructure-as-a-service (IaaS) solution. {{site.data.keyword.IBM_notm}} has continued to optimize its cloud infrastructure products to include support for the SAP NetWeaver computing platform.

It’s because of this relationship, and other {{site.data.keyword.cloud_notm}} capabilities, that {{site.data.keyword.IBM_notm}} was selected as one of SAP’s premier strategic providers of cloud infrastructure services for its business-critical applications. Support for SAP NetWeaver's suite of products is available through the highly scalable, open, and security-rich {{site.data.keyword.cloud_notm}}. With this partnership, SAP NetWeaver-based applications can expand to major markets made possible by more than 60 {{site.data.keyword.IBM_notm}} data centers worldwide.

The offering features {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} with eight memory options:
  * Single-socket 32 GB
  * Single-socket 64 GB
  * Dual-socket 128 GB
  * Dual-socket 256 GB
  * Dual-socket 512 GB
  * Dual-socket 192 GB
  * Dual-socket 384 GB
  * Dual-socket 768 GB

All eight options are certified for SAP NetWeaver and can provide a scalable, security-rich, open, global enterprise cloud platform for rapidly deploying SAP applications.

You can use your servers for production, non-production, or proof-of-concept (POC) environments. All SAP NetWeaver Application Server ABAP-based products and SAP NetWeaver Application Server Java-based products are supported on {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}. For all other software components, non-SAP NetWeaver-based SAP products, or third-party products, contact [SAP Support](https://support.sap.com/en/index.htmll){: external} if the products are supported within the IaaS offerings.

## {{site.data.keyword.cloud_notm}} for SAP NetWeaver offering model
{: #offer_model}

The {{site.data.keyword.cloud_notm}} for SAP Applications offering is ideal for practically all SAP NetWeaver use case-supported scenarios on {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} over the {{site.data.keyword.cloud_notm}} network.

The offering consists of the following servers, operating systems (OS), and databases:
  * {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} in eight sizes and the software that comes with each server.
      * 4 cores with 32 GB RAM
      * 4 cores with 64 GB RAM
      * 24 cores with 128 GB RAM
      * 24 cores with 256 GB RAM
      * 28 cores with 512 GB RAM
      * 36 cores with 192 GB RAM
      * 36 cores with 384 GB RAM
      * 36 cores with 768 GB RAM

  * Operating system or hypervisor
      * VMware vSphere ESXi 6.0 or 6.5 on your server
      * Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X OS [SAP Business Warehouse (SAP BW) is supported in production on {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}]
      * SUSE Linux Enterprise Server (see [SAP Note 2414097)](https://launchpad.support.sap.com/#/notes/2414097){: external} for version details)
      * Microsoft Windows Server (see [SAP Note 2414097)](https://launchpad.support.sap.com/#/notes/2414097){: external} for version details)

  * The databases that are offered are
      * Microsoft SQL Server for Windows (see [SAP Note 2414097)](https://launchpad.support.sap.com/#/notes/2414097){: external} for version details)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Linux (see [SAP Note 101809)](https://launchpad.support.sap.com/#/notes/101809){: external}: Supported versions and fix pack levels)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Windows (see [SAP Note 101809-DB6)](https://launchpad.support.sap.com/#/notes/101809){: external}: Supported versions and fix pack levels)
      * SAP MaxDB (see [SAP Note 2414097)](https://launchpad.support.sap.com/#/notes/2414097){: external} for version details)
      * SAP ASE 16.0 (see [SAP Note 2414097)](https://launchpad.support.sap.com/#/notes/2414097){: external} for details)
      * SAP HANA

{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} that are deployed with VMware ESXi can run the listed versions of RHEL and Windows, the referenced databases', and SAP NetWeaver-based software products. The servers can run other operating systems or non-SAP NetWeaver-based products, such as SAP liveCache, SAP Content Server, SAP Business One on Microsft SQL, and SAP BusinessObjects as listed in [SAP Note 2279688](https://launchpad.support.sap.com/#/notes/2279688){: external}.

If you're running SAP NetWeaver-based SAP products on your {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}, you must also run one of the supported operating systems and databases.
{: note}

See [SAP HANA on {{site.data.keyword.cloud_notm}}](/docs/infrastructure/sap-hana?topic=sap-hana-getting-started#getting-started) for information on deploying SAP HANA.

Consult the [SAP Product Availability Matrix (PAM)](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: external} for specific databases, operating system, and SAP NetWeaver requirements for {{site.data.keyword.cloud_notm}}. An SAP S-user ID is required to access SAP PAM.

## {{site.data.keyword.cloud_notm}} network
{: #ibm_cloud_network}

The {{site.data.keyword.cloud_notm}} provides more than 2,000 GB of connectivity across a global footprint of more than 60 {{site.data.keyword.cloud_notm}} data centers and 28 points of presence (PoPs). {{site.data.keyword.cloud_notm}} has 20 Gbps network connections across its locations. These connections are provided by leading global network providers and include multiple public peering links to dozens of additional internet access networks.

The network is three distinct and redundant gigabit network architectures-public, private, and data center-to-data center-seamlessly integrated to the industry's first network-within-a-network topology. This design provides maximum accessibility, security, and control for your IT infrastructure. See [The IBM Cloud network](https://www.ibm.com/cloud/data-centers/){: external} for more information.
