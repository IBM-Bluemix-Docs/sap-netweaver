---



copyright:
  years: 2018
lastupdated: "2018-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 4. 서버 크기 결정
{: #size_the_server}

사용할 SAP 솔루션을 결정한 후의 단계는 SAP 랜드스케이프를 지원하기 위해 필요한 {{site.data.keyword.baremetal_long}}의 수를 판별하고 서버 크기가 올바르게 결정되었는지 확인하는 것입니다.
{: shortdesc}

## SAP 크기 결정 방법 이해
{: #size_method}

SAP NetWeaver 중심 애플리케이션에 대한 SAP 크기 결정 방법은 SAP에서 제공하는 정보 및 실제 고객 경험과 같은 SAP 밴치마크를 기반으로 합니다. 기본 SAP 워크로드 단위는 SAPS(SAP Application Performance Standard)입니다. SAPS는 SAP 용량 계획 및 성능 테스트 담당자에 의해 만들어진 처리량 정의입니다. 예를 들어, 표준 SAP Sales and Distribution(SAP SD) 애플리케이션 벤치마크에서 100 SAPS는 시간당 2,000개의 완전 비즈니스 처리된 주문 행 항목으로 정의됩니다. 이는 SAP Enterprise Resource Planning(SAP ERP) 솔루션의 시간당 2,400개 SAP 트랜잭션과 동격입니다. 프로세서의 성능은 SAP에서 인증한 표준(SAP SD) 벤치마크 테스트 중에 측정됩니다. SAP에서 인증한 벤치마크 테스트에 대한 세부사항은 [*IBM X6 Systems 참조 아키텍처 상의 SAP Business Suite*](https://lenovopress.com/redp5073.pdf)를 참조하십시오. 이 테스트는 프로세스가 1초 미만의 응답 시간으로 100% CPU 로드에 가깝게 작업을 처리하는 능력을 평가합니다. 

## SAP Quick Sizer 사용
{: #quicksizer}
  
[SAP Quick Sizer](https://service.sap.com/quicksizer)는 SAP가 모든 파트너 및 고객에게 제공하는 웹 기반 도구입니다. 크기 결정 정보는 도구에 직접 입력되며, 이 도구는 SAP NetWeaver 기반 애플리케이션 및 SAP NetWeaver 기반이 아닌 애플리케이션의 크기를 결정합니다. 이는 SAP S-사용자 ID를 필요로 합니다. 
  
이 도구는 워크로드를 SAPS 단위로 계산하고 프로세서를 적절히 사용하도록 이를 조정합니다. 따라서 시간당 4,800개의 SAP SD 벤치마크 트랜잭션이 필요한 경우 이 도구는 이를 200 SAPS로 계산합니다. 33%의 목표 프로세서 로드가 허용되는 경우에는 100%에서 600 SAPS를 처리할 수 있는 프로세서를 찾기 위해 이를 조정하십시오(이는 33%에서 200과 같음). SAPS 계산에 대한 세부사항은 [*IBM X6 Systems 참조 아키텍처 상의 SAP Business Suite*![외부 링크 아이콘]](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://lenovopress.com/redp5073.pdf){: new_window}를 참조하십시오. 

이러한 크기 지정 방법이 보수적이라고 생각할 수 있으나, 서버의 SAPS 수가 특정 SAP SD 워크로드만을 실행하는 고도로 튜닝된 SAP 시스템을 기반으로 계산되었다는 점을 고려하십시오. 시스템의 SAP 애플리케이션 유형, 사용자 정의 구성 또는 사용자 정의 코딩에 따라 결과는 달라질 수 있습니다. 또한 개념 증명(PoC)과 같은 프로젝트 관련 요구사항, 또는 성능 및 응답 시간에 대한 요구사항 또한 다를 수 있습니다. 

## {{site.data.keyword.cloud_notm}} 베어메탈 서버 선택
{: #choose_server}

SAP 애플리케이션을 결정하였으며 SAP Quick Sizer를 통해, 또는 현재 랜드스케이프에 따라 SAPS 수가 계산되고 나면 제공된 모델에서 서버를 선택할 준비가 된 것입니다. 표 1에는 SAP NetWeaver에 대해 인증된 {{site.data.keyword.baremetal_short}}의 SAPS 수가 포함되어 있습니다. 인증 문서는 [SAP 표준 애플리케이션 벤치마크![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")]](https://go.sap.com/solution/benchmark.html){: new_window} 를 참조하십시오.  

표 1에 나열된 모든 지원되는 서버 유형은 공개된 이름으로 SAP에 의해 인증된 것과 일치하며 [SAP Note 2414097![외부 링크 아이콘]](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}에서 확인되었습니다. 전체 목록을 보려면 [여기![외부 링크 아이콘]](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://sap.com/solution/benchmark/appbm/cloud.html){: new_window} 를 클릭하십시오. 공개된 이름은 변경될 수 있다는 점을 참고하십시오. 

표 1. SAP NetWeaver에 대해 인증된 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}

| 서버 유형 | 인증 문서 | SAPS | RAM |
| --- | --- | --- | --- |
| BI.S1.NW32 | Cert16048 | 10,980 | 32GB |
| BI.S1.NW128 | Cert16063 | 54,130 | 128GB |
| BI.S1.NW256 | Cert17005 | 55,020 | 256GB |
| BI.S1.NW512 | Cert17027 | 65,520 | 512GB |

## 기존 SAP 시스템 마이그레이션 
{: #migrating}

임의의 소스에서 {{site.data.keyword.cloud_notm}} 환경으로 기존 SAP 시스템을 마이그레이션하려는 경우에는 현재 환경의 SAPS 수로부터 SAPS 수를 판별할 수 있습니다. 현재 워크로드의 정보(사용된 CPU 및 RAM 수)를 사용하여 [SAP SD 벤치마크 결과![외부 링크 아이콘]](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://go.sap.com/solution/benchmark.html){: new_window}에서 자신의 CPU에 대한, SAPS와 동격인 수치를 획득하십시오. 

## 다음 단계

 [5. 구성 결정](/docs/infrastructure/sap-netweaver/sap-determine-configuration.html)
