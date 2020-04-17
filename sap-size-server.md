---

copyright:
  years: 2018, 2020
lastupdated: "2020-04-17"

keywords: SAP NetWeaver, SAP Application Performance Standard, SAPS, SAP Quick Sizer

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external: target="_blank" .external}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 2. Sizing the server
{: #size_the_server}

After you decide which SAP solutions you plan to use, your next step is to determine the number of {{site.data.keyword.baremetal_long}} you need to support your SAP landscape and ensure that the servers are correctly sized.
{: shortdesc}

## Understanding the SAP sizing methodology
{: #size_method}

The SAP sizing methodology for SAP NetWeaver-centric applications is based on SAP benchmarks, such as information from SAP and actual customer experiences. The base SAP workload unit is an SAP Application Performance Standard (SAPS). The SAPS is a definition of throughput that is coined by SAP capacity planning and performance testing personnel. For example, 100 SAPS are defined as 2,000 fully business processed order-line items per hour in the standard SAP Sales and Distribution (SAP SD) application benchmark. This is equivalent to 2,400 SAP transactions per hour with the SAP Enterprise Resource Planning (SAP ERP) solution. The capability of processors is measured during the standard (SAP SD) benchmark test that is certified by SAP. For more detail about the benchmark test that is certified by SAP, see [*SAP Business Suite on IBM X6 Systems Reference Architecture*](https://lenovopress.com/redp5073.pdf){: external}. The test rates the process on its capability to process work at close to 100% CPU load with a response time of below 1 second.

## Using the SAP Quick Sizer
{: #quicksizer}

The [SAP Quick Sizer](https://service.sap.com/quicksizer){: external} is a web-based tool and is provided by SAP for all partners and customers. Sizing information is input directly in to the tool, where it sizes SAP NetWeaver-based applications and non-SAP NetWeaver-based applications. It requires an SAP S-user ID.

It calculates the workload (in SAPS) and adjusts it to allow for suitable processor use. So, if a workload of 4,800 SAP SD benchmark transactions per hour was required, the tool calculates this as 200 SAPS. If a target processor load of 33% is allowed, adjust this to find a processor capable of 600 SAPS at 100% (=200 at 33%). For more detail about the SAPS calculation, see [*SAP Business Suite on IBM X6 Systems Reference Architecture*](https://lenovopress.com/redp5073.pdf){: external}.

While the sizing method might be considered conservative, consider the fact that the SAPS numbers for your servers were calculated based on highly tuned SAP systems running only specific SAP SD workloads. Depending on the type of SAP application, any custom configuration or custom coding in your system, your results might vary. Also, requirements for your project, such as proof-of-concept (PoC) or regarding performance and response time, might be different.

## Choosing an {{site.data.keyword.cloud_notm}} bare metal server
{: #choose_server}

After you have determined your SAP applications and the SAPS numbers have been calculated through the SAP Quick Sizer, or based on your current landscape, you are ready to choose a server from the offered models. Table 1 contains the SAPS numbers for the {{site.data.keyword.baremetal_short}} that have been certified for SAP NetWeaver. See [SAP Standard Application Benchmarks](https://www.sap.com/about/benchmark.html){: external} for the certification documents.

All supported server types listed in Table 1 match those that have been certified by SAP with the published name and are verified in [SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097){: external}; click [here](https://www.sap.com/dmc/exp/2014-09-02-hana-hardware/enEN/power-systems.html){: external} for a complete listing. Note that the published names are subject to change.

| Server type | SAPS | RAM |
| --- | --- | --- |
| BI.S1.NW32 | 10980 | 32 GB |
| BI.S1.NW128 | 54130 | 128 GB |
| BI.S1.NW256 | 55020 | 256 GB |
| BI.S2.NW512 | 65520 | 512 GB |
| BI.S3.NW32 | 11970 | 32 GB |
| BI.S3.NW64 | 12750 | 64 GB |
| BI.S3.NW192 | 78850 | 192 GB |
| BI.S3.NW384 | 79430 | 384 GB |
| BI.S3.NW768 | 79630 | 768 GB |
{: caption="Table 1. {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} certified for SAP NetWeaver" caption-side="top"}

## Migrating an existing SAP system
{: #migrating}

If you are planning to migrate an existing SAP system from any source to your {{site.data.keyword.cloud_notm}} environment, you can determine the SAPS numbers from the SAPS numbers of your current environment. Use the information on your current workload (the CPUs and RAM used) and get the SAPS equivalents for your CPU from the [SAP SD benchmark results](https://www.sap.com/about/benchmark.html){: external}.

## Next Steps
{: #size-server-next-steps}

 [5. Determining your configuration](/docs/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration)
