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

# 시스템 랜드스케이프 계획
{: #planning-your-system-landscape}

SAP *랜드스케이프*는 일반적으로 개발, 품질 보증 및 테스트, 프로덕션 환경을 포함하는 둘 이상의 SAP *시스템*의 그룹입니다. 하나의 SAP 시스템은 동시에 시작되고 중지되는 프로세스의 그룹인 *SAP 인스턴스*가 하나 이상 모여 구성되어 있습니다. SAP 랜드스케이프에 대한 자세한 정보는 [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://lenovopress.com/redp5073.pdf){: new_window}를 참조하십시오.
{: shortdesc}

시장에 출시된 모든 SAP 솔루션에 대해서는 서버(크기)/스토리지(크기)와 같은, 몇 가지 가능한 랜드스케이프 구성이 있습니다. 이러한 솔루션에는 [SAP Business Suite ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://open.sap.com/courses/suitehana1){: new_window}, SAP Business Warehouse 등의 SAP NetWeaver 기반 제품 및 {{site.data.keyword.cloud}} SAP 인증 인프라의 서버가 지원하는 모든 특정 SAP 추가 기능이 포함됩니다. SAP와 통합될 수 있는 SAP NetWeaver 기반이 아닌 SAP 솔루션 또는 서드파티 소프트웨어 또한 유의해야 합니다. {{site.data.keyword.cloud}} IaaS 랜드스케이프에 SAP NetWeaver 기반이 아닌 소프트웨어 또는 서드파티 소프트웨어를 배치하려는 경우에는 [SAP 지원![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://support.sap.com/en/index.html){: new_window}에 문의하십시오.

실행할 애플리케이션, 잠재적 확장 크기 및 성능을 기반으로 서버의 크기를 결정할 때는 가능한 한 자세한 정보가 필요합니다. 애플리케이션의 스토리지 및 메모리 요구사항 또한 고려해야 합니다. 랜드스케이프 내의 SAP 시스템에는 각각 특정한 연결 요구사항(내부 시스템 간 또는 외부 시스템 간)이 있습니다. 자세한 정보는 [SAP 랜드스케이프를 계획할 때 고려해야 하는 항목](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations)을 참조하십시오.

표 1에는 계획 프로세스의 단계가 포함되어 있습니다. 목표 SAP 랜드스케이프를 빌드하려면 이 단계를 사용하십시오.

표 1. 계획 프로세스 개요

|단계 |세부사항 |
| --- | --- |
|1 |[SAP 및 {{site.data.keyword.cloud_notm}} 인증 정보 가져오기 및 계정 작성](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-get_sap_ibm_credentials#get_sap_ibm_credentials) |
|2 |[관련 SAP 및 {{site.data.keyword.cloud_notm}} 문서 검토](/docs/infrastructure/sap-netweaver/sap-review-doc.html) |
|3 |[SAP NetWeaver 애플리케이션 결정](/docs/infrastructure/sap-netweaver/sap-determine-apps.html) |
|4 |[서버 크기 결정](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server) |
|5 |[구성 결정](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration) |

## 다음 단계

표 1의 적절한 단계를 선택하여 SAP 랜드스케이프 계획을 시작하십시오.
