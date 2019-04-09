---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, SAP Application Performance Standard, SAPS, SAP Quick Sizer

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 4. 设置服务器的大小
{: #size_the_server}

决定计划使用的 SAP 解决方案之后，接下来的步骤是确定支持 SAP 格局所需的 {{site.data.keyword.baremetal_long}} 数量并确保正确设置了这些服务器的大小。
{: shortdesc}

## 了解 SAP 大小设置方法
{: #size_method}

以 SAP NetWeaver 为中心的应用程序的 SAP 大小设置方法基于 SAP 基准，例如来自 SAP 和真实客户体验的信息。基本 SAP 工作负载单元是 SAP 应用程序性能标准 (SAPS)。SAPS 是吞吐量的定义，该词由 SAP 容量规划和性能测试人员创造。例如，在标准 SAP 销售和分发 (SAP SD) 应用程序基准中，100 SAPS 定义为每小时 2000 个完全处理业务的订单行项。这相当于 SAP 企业资源规划 (SAP ERP) 解决方案的每小时 2,400 个 SAP 事务。在 SAP 认证的标准 (SAP SD) 基准测试期间，会度量处理器能力。有关 SAP 认证的基准测试的更多详细信息，请参阅 [*SAP Business Suite on IBM X6 Systems 参考体系结构
 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://lenovopress.com/redp5073.pdf){: new_window}。测试将该过程处理工作的能力评估为在接近 100% 的 CPU 负载下，响应时间低于 1 秒。

## 使用 SAP Quick Sizer
{: #quicksizer}

[SAP Quick Sizer ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://service.sap.com/quicksizer){: new_window} 是 SAP 为所有合作伙伴和客户提供的基于 Web 的工具。大小设置信息直接输入到该工具中，然后该工具会对基于 SAP NetWeaver 的应用程序和非基于 SAP NetWeaver 的应用程序设置大小。需要 SAP S 用户标识。

此工具计算工作负载（以 SAPS 为单位），并对其进行调整以适应适当的处理器使用。因此，如果需要每小时 4,800 个 SAP SD 基准事务的工作负载，该工具会将其计算为 200 SAPS。如果允许 33% 的目标处理器负载，请调整此值以找到能够在负载为 100% 时达到 600 SAPS（相当于负载为 33% 时达到 200 SAPS）的处理器。有关 SAPS 计算的更多详细信息，请参阅 [*SAP Business Suite on IBM X6 Systems 参考体系结构* ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://lenovopress.com/redp5073.pdf){: new_window}。

虽然该大小设置方法可能被视为较保守，但值得注意的是，服务器的 SAPS 数量是基于仅运行特定 SAP SD 工作负载的高度调优 SAP 系统来计算的。根据 SAP 应用程序的类型以及系统中的任何定制配置或定制编码，结果可能有所不同。此外，项目的需求（例如概念证明 (PoC) 或有关性能和响应时间的需求）可能也不同。

## 选择 {{site.data.keyword.cloud_notm}} 裸机服务器
{: #choose_server}

确定 SAP 应用程序并通过 SAP Quick Sizer 或基于当前格局计算 SAPS 数量后，即可从提供的模型中选择服务器。表 1 包含已针对 SAP NetWeaver 认证的 {{site.data.keyword.baremetal_short}} SAPS 数量。请参阅
[SAP Standard Application Benchmarks ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.sap.com/about/benchmark.html){: new_window} 以获取认证文档。

表 1 中列出的所有受支持服务器类型都与 SAP 认证的带有已发布名称并在 [SAP Note 2414097 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 中经过验证的服务器类型相匹配；单击[此处 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.sap.com/dmc/exp/2014-09-02-hana-hardware/enEN/power-systems.html){: new_window} 以获取完整列表。请注意，已发布的名称可能会更改。

表 1. 针对 SAP NetWeaver 进行认证的 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}

|服务器类型|SAPS |RAM |
| --- | --- | --- |
|BI.S1.NW32 | 10980 |32 GB |
|BI.S1.NW128 | 54130 |128 GB |
|BI.S1.NW256 | 55020 |256 GB |
| BI.S2.NW512 | 65520 |512 GB |
| BI.S3.NW32 | 11970 |32 GB |
| BI.S3.NW64 | 12750 | 64 GB |
| BI.S3.NW192 | 78850 | 192 GB |
| BI.S3.NW384 | 79430 | 384 GB |
| BI.S3.NW768 | 79630 | 768 GB |

## 迁移现有 SAP 系统
{: #migrating}

如果计划将现有 SAP 系统从任何源迁移到 {{site.data.keyword.cloud_notm}} 环境，那么可以从当前环境的 SAPS 数量确定 SAPS 数量。使用有关当前工作负载（CPU 数和已用 RAM）的信息，并从 [SAP SD 基准结果![外部链接图标]](../../icons/launch-glyph.svg "外部链接图标")](https://www.sap.com/about/benchmark.html){: new_window}.

## 后续步骤

 [5. 确定配置](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration)
