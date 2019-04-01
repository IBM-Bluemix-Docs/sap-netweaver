---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-18"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.baremetal_short}}, ABAP, application server, SAP Product Availability Matrix, PAM, SAP Certified, SAP Content Server, SAP liveCache

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:note: .note}
{:faq: .faq}


# IBM Cloud SAP 인증 인프라 정보
{: #about_ibmcloud_for_sap}

IBM과 SAP는 45년간 하드웨어, 소프트웨어, 클라우드, 서비스 및 금융을 포함한 다양한 분야에서 파트너로서 팀을 이뤄 협업해 왔습니다. 첫 번째 협업은 1972년에 시작되었으며 이는 수백 개의 SAP 클라이언트가 IaaS(Infrastructure as a Service) 솔루션으로 {{site.data.keyword.cloud}}를 사용하는 관계로 성장했습니다. {{site.data.keyword.IBM_notm}}에서는 SAP NetWeaver 컴퓨팅 플랫폼에 대한 지원을 포함하기 위해 자사의 클라우드 인프라 제품을 계속해서 최적화하였습니다.

바로 이러한 관계, 그리고 기타 {{site.data.keyword.cloud_notm}} 기능이 SAP에서 {{site.data.keyword.IBM_notm}}을 자사의 필수 비즈니스 애플리케이션을 위한 클라우드 인프라 서비스의 주요 제공자 중 하나로 선택한 이유입니다. SAP NetWeaver 제품 스위트에 대한 지원은 확장성, 개방성 및 보안성이 뛰어난 {{site.data.keyword.cloud_notm}}를 통해 사용 가능합니다. 이 파트너십을 통해, SAP NetWeaver 기반 애플리케이션은 세계 각국에 있는 60개 이상의 {{site.data.keyword.IBM_notm}} 데이터 센터를 이용하여 주요 시장에 진출할 수 있습니다.

이 오퍼링의 특징은 8개의 메모리 옵션이 있는 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}입니다.
  * 싱글 소켓 32GB
  * 싱글 소켓 64GB
  * 듀얼 소켓 128GB
  * 듀얼 소켓 256GB
  * 듀얼 소켓 512GB
  * 듀얼 소켓 192GB
  * 듀얼 소켓 384GB
  * 듀얼 소켓 768GB

8개의 모든 옵션은 SAP NetWeaver의 인증을 받았으며, 신속한 SAP 애플리케이션 배치를 위한 확장성, 보안성, 개방성이 뛰어난 글로벌 엔터프라이즈 클라우드 플랫폼을 제공할 수 있습니다.

사용자는 프로덕션, 비프로덕션 또는 개념 증명(POC) 환경에 서버를 사용할 수 있습니다. 모든 SAP NetWeaver Application Server ABAP 기반 제품 및 SAP NetWeaver Application Server Java 기반 제품은 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}에서 지원됩니다. 모든 기타 소프트웨어 컴포넌트, SAP NetWeaver 기반이 아닌 SAP 제품 또는 서드파티 제품의 경우에는 해당 제품이 IaaS 오퍼링 내에서 지원되는지 확인하려면 [SAP 지원![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://support.sap.com/home.html){: new_window}에 문의하십시오.

## {{site.data.keyword.cloud_notm}} for SAP NetWeaver 오퍼링 모델
{: #offer_model}

{{site.data.keyword.cloud_notm}} for SAP Applications 오퍼링은 {{site.data.keyword.cloud_notm}} 네트워크를 사용하는 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}에서의 거의 모든 SAP NetWeaver 유스 케이스 지원 시나리오에 대해 적합합니다.

이 오퍼링은 다음 서버, 운영 체제(OS) 및 데이터베이스로 구성되어 있습니다.
  * 8개 크기의 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 및 각 서버와 함께 제공되는 소프트웨어.
      * 4개 코어(32GB RAM)
      * 4개 코어(64GB RAM)
      * 24개 코어(128GB RAM)
      * 24개 코어(256GB RAM)
      * 28개 코어(512GB RAM)
      * 36개 코어(192GB RAM)
      * 36개 코어(384GB RAM)
      * 36개 코어(768GB RAM)

  * 운영 체제 또는 하이퍼바이저
      * 사용자 서버의 VMware vSphere ESXi 6.0 또는 6.5
      * Red Hat Enterprise Linux(RHEL) for SAP Business Applications 6.X OS [SAP Business Warehouse(SAP BW)는 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 상의 프로덕션 환경에서 지원됨]
      * SUSE Linux Enterprise Server(버전 세부사항은 [SAP Note 2414097 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 참조)
      * Microsoft Windows Server(버전 세부사항은 [SAP Note 2414097 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 참조)

  * 제공되는 데이터베이스
      * Microsoft SQL Server for Windows(버전 세부사항은 [SAP Note 2414097 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 참조)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Linux([SAP Note 101809 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://launchpad.support.sap.com/#/notes/101809){: new_window} 참조: 지원되는 버전 및 수정팩 레벨)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Windows([SAP Note 101809-DB6 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://launchpad.support.sap.com/#/notes/101809){: new_window} 참조: 지원되는 버전 및 수정팩 레벨)
      * SAP MaxDB(버전 세부사항은 [SAP Note 2414097 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 참조)
      * SAP ASE 16.0(세부사항은 [SAP Note 2414097 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 참조)
      * SAP HANA

VMware ESXi를 사용하여 배치된 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}는 RHEL 및 Windows, 참조된 데이터베이스 및 SAP NetWeaver 기반 소프트웨어 제품의 나열된 버전을 실행할 수 있습니다. 서버는 [SAP Note 2279688 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://launchpad.support.sap.com/#/notes/2279688){: new_window}에 나열된 대로 기타 운영 체제 또는 비SAP 네트워크 기반의 제품(SAP liveCache, SAP Content Server, SAP Business One on Microsoft SQL, 및 SAP BusinessObjects 등)에서 실행될 수 있습니다.

{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}에서 SAP NetWeaver 기반의 SAP 제품을 실행하는 경우, 지원되는 운영 체제 및 데이터베이스 중 하나를 실행해야 합니다.
{: note}

SAP HANA 배치에 대한 정보는 [SAP HANA on {{site.data.keyword.cloud_notm}}](/docs/infrastructure/sap-hana?topic=sap-hana-getting-started#getting-started)를 참조하십시오.

{{site.data.keyword.cloud_notm}}의 특정 데이터베이스, 운영 체제 또는 SAP NetWeaver 요구사항에 대해서는 [SAP PAM(Product Availability Matrix)![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: new_window}을 참조하십시오. SAP PAM에 액세스하려면 SAP S-사용자 ID가 필요합니다.

## {{site.data.keyword.cloud_notm}} 네트워크
{: #ibm_cloud_network}

{{site.data.keyword.cloud_notm}}는 60개 이상의 {{site.data.keyword.cloud_notm}} 데이터 센터와 28개의 상호접속 위치(PoP)의 전 세계적 풋프린트에 2,000GB 이상의 연결을 제공합니다. {{site.data.keyword.cloud_notm}}는 해당 위치 간에 20Gbps 네트워크로 연결되어 있습니다. 이러한 연결은 대표적인 글로벌 네트워크 제공자로부터 제공되며 수많은 추가 인터넷 액세스 네트워크에 대한 다중 공용 피어링 링크를 포함합니다.

이 네트워크는 업계 최고의 네트워크 내 네트워크 토폴로지에 빈틈없이 통합된 세 가지 개별 중복 기가비트 네트워크 아키텍처(공용, 개인용 및 데이터 센터 대 데이터 센터)입니다. 이 디자인은 IT 인프라에 대한 최대의 접근성, 보안 및 제어 기능을 제공합니다. 자세한 정보는 [IBM Cloud 네트워크 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud-computing/bluemix/our-network){: new_window}를 참조하십시오.
