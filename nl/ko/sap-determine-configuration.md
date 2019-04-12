---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, RDBMS, SAP Application Performance Standards, SAPS, SAP Certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 5. 구성 결정
{: #determine_configuration}

SAP NetWeaver 시스템을 사용하는 경우에는 두 가지 배치 선택사항이 있습니다.
  * 단일 호스트 설치인 중앙 집중식 시스템(2계층)
  * 다중 호스트 설치인 분산 시스템(3계층)

이러한 선택사항은 서버 선택에 영향을 줍니다. 사용자는 여러 서버에 워크로드를 분산하거나, 단순함을 위해 하나의 서버에서 워크로드를 처리할 수 있습니다. 서버 배치 방법에 대한 단계별 안내는 [인프라 설정](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-set_up_infrastructure#set_up_infrastructure)을 참조하십시오.

## 스토리지 구성
{: #storage_config}

표 1은 외부 [{{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-getting-started#getting-started) 또는 [{{site.data.keyword.cloud_notm}} {{site.data.keyword.filestorage_short}}](/docs/infrastructure/FileStorage?topic=FileStorage-getting-started#getting-started)(4IOPS/GB)를 포함하는 {{site.data.keyword.Db2_on_Cloud_long}} 데이터베이스를 사용하며, SAP를 포함하는 중앙 집중식 시스템에서 1.5TB에 대해 IOPS가 6,000이고, [SAPS](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server)가 50,000인 256GB 서버에 대한 샘플 스토리지 구성입니다. IOPS 계산은 다음과 같습니다.

  * 6,000IOPS / 1,500GB = 4IOPS/GB가 외부 스토리지에 대해 필요합니다. 2IOPS/GB(중간 성능)인 3,000GB의 백업용 스토리지가 있다고 가정합니다.

표 1. IOPS 계산에 기반한 샘플 스토리지 레이아웃

|파일 시스템 |볼륨 수 |스토리지 유형 |IOPS/GB |GB |IOPS 수 |
| --- | --- | --- | --- | --- | --- |
| `/` |1 |내부 |해당사항 없음 |150GB |해당사항 없음 |
| `/boot` |1 |내부 |해당사항 없음 |0.25GB |해당사항 없음 |
| `swap` |1 |내부 |해당사항 없음 |256GB |해당사항 없음 |
| `/db2`(logs 포함) |1 |내부 |해당사항 없음 |250GB |해당사항 없음 |
| `sapdata` |1 |외부 |4IOPS/GB |1,500GB |6,000IOPS |
| `backup/log and backup` |1 |외부 |2IOPS/GB |3,000GB |6,000IOPS |

## 고가용성 구성
{: #ha_config}

{{site.data.keyword.cloud_notm}} 환경은 사전 구성된 고가용성(HA) 시나리오를 지원하지 않습니다. 그러나 선택하는 운영 체제용 HA 확장을 기반으로 HA 시나리오를 구성하는 것은 가능합니다. HA 확장은 랜드스케이프에 필수 하드웨어 및 필수 소프트웨어 컴포넌트를 추가하여 추가합니다. 추가 소프트웨어 라이센스가 필요한 경우에는 다른 소프트웨어 저장소에 액세스하거나, [{{site.data.keyword.cloud_notm}} 지원](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support)에 문의하여 추가 요구사항을 구성하는 데 대해 도움을 받으십시오.

이 정보는 SAP NetWeaver용 HA 소프트웨어뿐만 아니라, 선택하는 관계형 데이터베이스 관리 시스템(RDBMS)용 HA 소프트웨어에도 적용됩니다. 이는 복제와 같은, RDBMS를 위한 고가용성 및 재해 복구 메커니즘을 포함합니다. 설정 프로시저는 온프레미스 환경에서의 다른 설정 프로시저와 다르지 않으며 동일한 하드웨어 및 소프트웨어 구성 단계를 필요로 합니다.

## 다음 단계

이제 {{site.data.keyword.baremetal_short}}의 프로비저닝을 시작할 준비가 되었습니다. 다음 단계는 [SAP NetWeaver 환경 프로비저닝](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment)을 참조하십시오.
