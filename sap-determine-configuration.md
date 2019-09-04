---

copyright:
  years: 2018, 2019
lastupdated: "2019-09-04"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, RDBMS, SAP Application Performance Standards, SAPS, SAP Certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external="_blank" .external}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 5. Determining your configuration
{: #determine_configuration}

With an SAP NetWeaver system, you have two deployment options:
  * Central system, which is a single-host installation (two-tier)
  * Distributed system, which is a multi-host installation (three-tier)

The options influence your server choice. You might want to distribute your workload to different servers or keep the workload on one server for simplicity. See [Setting up your infrastructure](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-set_up_infrastructure#set_up_infrastructure) for step-by-step guidance on how deploy your server.
{:shortdesc}

## Storage configuration
{: #storage_config}

Table 1 is a sample storage configuration for a 256 GB server with 50,000 [SAPS](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server), 1.5 TB at 6,000 IOPS for a central system with SAP, using an {{site.data.keyword.Db2_on_Cloud_long}} database with external [{{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-getting-started#getting-started) or [{{site.data.keyword.cloud_notm}} {{site.data.keyword.filestorage_short}}](/docs/infrastructure/FileStorage?topic=FileStorage-getting-started#getting-started) (4 IOPS/GB). The calculation for the IOPS is

  * 6,000 IOPS/1,500 GB = 4 IOPS/GB needed for external storage. There is an assumption of 3,000 GB for backup at 2 IOPS/GB (medium performance.

| File system | # of volumes | Storage type | IOPS/GB | GB | # IOPS |
| --- | --- | --- | --- | --- | --- |
| `/` | 1 | Internal | N/A | 150 GB | N/A |
| `/boot` | 1 | Internal | N/A | 0.25 GB | N/A |
| `swap` | 1 | Internal | N/A | 256 GB | N/A |
| `/db2` (including logs) | 1 | Internal | N/A | 250 GB | N/A |
| `sapdata` | 1 | External | 4 IOPS/GB | 1,500 GB | 6,000 IOPS |
| `backup/log and backup` | 1 | External | 2 IOPS/GB | 3,000 GB | 6,000 IOPS |
{: caption="Table 1. Sample storage layout based on IOPS calculation" caption-side="top"}

## High-availability configuration
{: #ha_config}

The {{site.data.keyword.cloud_notm}} environment does not support any preconfigured high-availability (HA) scenarios. However, you can configure HA scenarios based on the HA extension for the operating system you choose. You add the HA extension by adding the required hardware and the required software components to your landscapes. If you require additional software licenses, access to different software repositories, or both contact [{{site.data.keyword.cloud_notm}} Support](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) to help you with setting up any additional requirements.

This information not only applies to HA software for SAP NetWeaver, it also applies to HA software for the relational database management system (RDBMS) you choose. This includes the high-availability and disaster-recovery mechanisms for your RDBMS, for example, replication. Setup procedures do not differ from any setup procedures in an on-premises environment and require the same hardware and software configuration steps.

## Next Steps
{: #determine-configuration-next-steps}

You are now ready to begin Provisioning your {{site.data.keyword.baremetal_short}}. See [Provisioning your SAP NetWeaver environment](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment) for your next steps.
