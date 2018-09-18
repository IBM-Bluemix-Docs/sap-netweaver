---



copyright:
  years: 2017, 2018
lastupdated: "2018-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# FAQ: SAP on IBM Cloud 애플리케이션
{: #faqs}

## SAP NetWeaver를 {{site.data.keyword.cloud_notm}}에서 실행하려면 DB2가 필요합니까?

[SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097)을 정기적으로 확인하고 [SAP Product Availability Matrix](https://apps.support.sap.com/sap/support/pam)도 참조하십시오. 사용자의 데이터베이스에서는 다른 서비스 팩 세트를 필요로 하므로 SAP Note에 제공된 운영 체제에 주의하십시오.

## {{site.data.keyword.cloud_notm}}에 대한 인증을 위해 {{site.data.keyword.Db2_on_Cloud_short}}가 선택된 이유는 무엇입니까?

{{site.data.keyword.Db2_on_Cloud_long_notm}}는 {{site.data.keyword.IBM_notm}} 제품이며 {{site.data.keyword.cloud_notm}}는 {{site.data.keyword.IBM_notm}}의 일부이므로 인증을 위해 선택되었습니다.

## 분산 SAP 환경을 여러 데이터 센터 간에 분할할 수 있습니까?

분산 SAP 설치의 경우에는 모든 노드를 동일한 데이터 센터 및 VLAN 세그먼트에 두는 것이 좋습니다. 그렇지 않은 경우에는 SAP 시스템이 응답하지 않는 대기 시간 및 제한시간이 발생할 수 있습니다.

## SAP 아키텍처에 정의된 SAP 고가용성을 달성할 수 있습니까?

유일하게 지원되는 고가용성 아키텍처는 애플리케이션 서버의 스케일링입니다. 현재는 고가용성 지원이 사용으로 설정된 하드웨어가 없습니다.

## {{site.data.keyword.cloud_notm}}에서 직접 SAP 배포 소프트웨어를 다운로드할 수 있습니까?

현재는 [SAP Service Marketplace](https://websmp201.sap-ag.de/)에 대한 직접 링크를 제공하지 않습니다. 그러므로 사용자는 현재 온프레미스 배치와 마찬가지로 배포 DVD를 다운로드해야 합니다.
