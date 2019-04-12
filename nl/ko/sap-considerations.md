---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, network connectivity, VLANs, hybrid, STMS, SAProuter, SAP Solution Manager, SAP certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# SAP 랜드스케이프를 계획할 때 고려해야 하는 항목
{: #considerations}

랜드스케이프 내의 SAP 시스템에는 각각 특정한 연결 요구사항(내부 시스템 간 또는 외부 시스템 간)이 있습니다. 랜드스케이프에 대한 외부 스토리지를 고려하거나, 서버에 VMware를 배치하는 경우 수행해야 하는 작업 또한 생각해 보아야 합니다.

## 네트워크 연결
{: #network_connectivity}

[{{site.data.keyword.cloud_notm}} 네트워크](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-ibm_cloud_network#ibm_cloud_network)는 네트워크 연결에 대한 {{site.data.keyword.cloud}} 접근법의 개요를 보여줍니다. 네트워크 연결 문제는 적절히 계획하지 않는 경우 시스템 용도에 관계없이 프로젝트에 막대한 지연을 초래합니다.

일반적으로는 IaaS 프로비저닝된 {{site.data.keyword.cloud_notm}} 서버에 대해 두 가지 인터페이스를 선택할 수 있으며, 첫 번째는 공인 IP를 사용하는 외부 인터페이스입니다. 두 번째는 RFC(Request for Comment) 1918을 준수하는 “사설 IP”를 사용하여 제공되는 내부 인터페이스입니다. “사설 IP”를 사용하는 단일 내부 인터페이스를 선택할 수도 있습니다. 두 선택사항은 Linux의 “인터페이스 본딩” 또는 Windows의 네트워크 인터페이스 카드(NIC) 팀 구성을 통해 중복으로 구성할 수 있으며, 100Mb/s, 1Gb/s 및 10Gb/s의 속도를 사용하도록 할 수 있습니다..

유스 케이스에 따라, 개념 증명(PoC) 랜드스케이프에서는 외부 IP 사용이 용이할 수 있으므로 공인 IP가 적절할 수 있습니다. 기본 방화벽이 설치되어 사전 구성된 경우에도 잠재적 보안 위험은 존재합니다. 공용 인터페이스를 사용하려는 경우에는 서버를 주문할 때 **공용 대역폭**에 대해 충분히 높은 값을 선택하십시오. 이 값은 1개월 기간 동안 해당 인터페이스를 통해 전송할 수 있는 총 데이터 양을 결정합니다. 일반적인 네트워크 통신 중에는 SAP 그래픽 사용자 인터페이스(GUI) 또는 SAP 원격 함수 호출(RFC) 트래픽의 총량이 하루에 수 메가바이트에 불과할 수 있으나, 대량 데이터 업로드 시에는 1개월당 1,000GB 한계를 쉽게 초과할 수 있습니다. 사용자는 전송되는 데이터 양의 자리수만이라도 알고 있거나, 두 번째 선택사항으로 전환해야 합니다.

두 번째 선택사항은 {{site.data.keyword.cloud_notm}} 인프라 고객 포털을 통해 {{site.data.keyword.cloud_notm}} 가상 사설망(VPN)에 액세스하거나, 사용자의 랜드스케이프에 보안 디바이스를 배치합니다. 보안 디바이스는 방화벽, 네트워크 주소 변환, VPN 액세스 및 기타 네트워크 기능에 대해 제공됩니다. 또한 이러한 보안 디바이스는 더 큰 대역폭을 제공할 수 있으며, 이는 {{site.data.keyword.cloud_notm}} 데이터 센터에 많은 양의 데이터를 전송하는 데 도움을 줍니다. 랜드스케이프의 레이아웃과 SAP 애플리케이션 계층에서 필요한 연결이 결정된 후에는 네트워킹 부서에서 [{{site.data.keyword.cloud_notm}} 지원](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support)에 연락하여 의견을 교환하는 것이 좋습니다.

### VLAN
{: #vlans}

랜드스케이프 내의 서로 다른 네트워크 트래픽 유형을 분리하려는 경우에는 추가 가상 LAN(VLAN)을 주문할 수 있습니다. VLAN이 추가되면 트래픽만 분리되는 것이며 성능이 증가하지는 않는다는 점에 유의하십시오. 보안 관련 이유로 인해 서로 다른 네트워크 트래픽을 더 엄격하게 분리해야 하는 정교한 VMware 기반 배치에서는 트래픽 분리를 고려해야 합니다.

다음 유스 케이스에서는 모든 서버가 배치 중에 같은 VLAN에 속하도록 하는 것이 좋습니다.
  *	3계층 SAP 설정 데이터베이스 및 서로 다른 서버에 있는 SAP 애플리케이션 인스턴스와 같이, 여러 서버가 데이터를 교환하는 경우
  *	여러 시스템이 대량의 데이터를 교환하는 경우

로컬 스토리지를 사용하는 SAP 배치의 경우에는, 3계층 설치인 경우에도 1GB 네트워크면 충분합니다. 그 외에 추가로 고려해야 하는 요소가 있을 수 있습니다. 네트워크 스토리지 선택사항에 대한 자세한 정보는 [외부 스토리지](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations#external_storage)를 참조하십시오.

### 하이브리드 설치
{: #hybrid}

{{site.data.keyword.cloud_notm}} 데이터 센터에 SAP 시스템을 두고 사이트에 다른 시스템을 두는 하이브리드 랜드스케이프를 구현하려 하는 경우에는 {{site.data.keyword.cloud_notm}} for SAP Applications 오퍼링을 외부 데이터 센터로 취급할 수 있습니다. 하이브리드 설치에서는 프로젝트 계획 단계의 일부로서 고려해야 하는 몇 가지 특정 구성 항목이 있습니다.

  *	[SAP Transport Management System(STMS)![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.sap.com/products/transportation-logistics.html){: new_window}. 데이터 센터 간 파일 공유를 방지하기 위해 전송 그룹을 기반으로 이를 구성하십시오.
  *	[SAProuter ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://support.sap.com/en/tools/connectivity-tools/saprouter.html){: new_window}. SAP Online Service System(OSS)에 대한 액세스를 제공합니다. 이미 사용 가능한 상태인 사용자의 온프레미스 SAProuter를 사용하여 OSS에 액세스하십시오. {{site.data.keyword.cloud_notm}} 기반 시스템과 온프레미스 SAProuter 간의 IP 기반 라우팅이 허용되지 않은 경우에는 추가 SAProuter 홉을 통해 이 SAProuter를 사용할 수 있습니다. 또는 공인 IP를 사용하는 하나의 {{site.data.keyword.cloud_notm}} 기반 서버를 기반으로 하는 다른 SAProuter를 설정하고 이를 인터넷을 통해 SAP OSS 시스템에 연결하는 것을 고려할 수도 있습니다.
  *	[SAP Solution Manager ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://support.sap.com/en/solution-manager.html){: new_window}. 사용 시나리오에 따라, SAP Solution Manager와 해당 관리 시스템에서는 SAP Solution Manager에 액세스하기 위한 연결 요구사항이 서로 다릅니다. 이러한 시나리오는 필수 네트워크 연결에 대한 이해를 필요로 합니다.  

## 외부 스토리지
{: #external_storage}

로컬 스토리지는 데이터베이스 배치에 최상의 성능을 제공합니다. 사용자는 로컬 스토리지 외에 백업을 수행하기 위한 추가 외부 스토리지를 필요로 할 수 있으며, SAP 시스템의 데이터베이스가 내부 디스크의 스토리지 용량을 초과하는 경우도 있습니다. 또 다른 예로는 가상 머신(VM)을 공유하려는 여러 ESX 기반 서버와 같이, 프로젝트 요구사항에서 외부 스토리지를 필요로 하는 경우가 있습니다. 이러한 요구사항이 있는 경우에는 [스토리지](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-storage#storage)에 설명되어 있는 바와 같이 블록 스토리지 또는 NAS(Network Attached Storage)를 주문할 수 있습니다. 추가 블록 스토리지 및 NAS 데이터는 다른 모든 네트워크 트래픽과 동일한 실제 어댑터를 통해 전송되므로, 이에 대한 영향을 고려해야 합니다. 이로 인해 인증 벤치마크에서 측정된 성능 수치와 유사한 수치를 달성하기 힘들 수 있습니다.

로컬 스토리지 대신 외부 스토리지를 주로 사용하려는 경우에는 배치에 대해 10Gb 기반 데이터 센터를 선택하는 것이 좋습니다. 예를 들어, 외부 스토리지가 백업용 및 데이터베이스용으로 모두 사용되며 SAP 시스템에서 많은 작업을 처리할 예정입니다. 이러한 경우 I/O 로드가 90MB/s이면 1Gb 네트워크에서는 과부하가 발생할 확률이 높습니다.

또 다른 권장사항은 데이터베이스가 주로 외부 스토리지에 상주하는 경우 4IOPS/GB 이상을 사용하는 것입니다. 이보다 느린 스토리지는 데이터베이스 성능이 프로젝트에서 중요하지 않은 경우에만, 또는 백업 용도로만 사용해야 합니다.

외부 스토리지를 VMware ESX의 데이터 저장소로 사용하려는 경우에는 [VMware 시스템과 함께 사용하는 스토리지](/docs/infrastructure/vmware?topic=VMware-vmware-storage#vmware-storage)의 의사결정 가이드라인에 따라 사용자의 유스 케이스에 가장 적합한 스토리지 유형을 판별하십시오.

## VMware ESXi 서버 배치
{: #vmware_server}

{{site.data.keyword.cloud_notm}}에서의 VMware ESXi 기반 배치는 다른 클라우드 기반 배치와는 다릅니다. {{site.data.keyword.cloud_notm}}에서는 고객에게 실행 중인 VM을 제공하지 않으며, 사용자가 환경을 제어하고 요구사항을 만족시킬 수 있도록 이를 구성해야 합니다. VMware ESX 서버를 주문하면 구성된 서버를 받게 됩니다. 다음 링크는 추가 스토리지 및 게스트 VM 실행에 대한 정보를 제공합니다.

  *	[VMware 시스템과 함께 사용하는 스토리지](/docs/infrastructure/vmware?topic=VMware-vmware-storage#vmware-storage)는 스토리지를 ESX 환경과 통합하는 방법에 대한 추가 지시사항을 제공합니다.
  * [iSCSI VMware ESXi 마운트](/docs/infrastructure/vmware?topic=VMware-mount-iscsi-esxi#mount-iscsi-esxi)에는 iSCSI 기반 스토리지를 ESX와 통합하는 단계가 설명되어 있습니다.
  * [VMware ESX 가상 머신 작성](/docs/infrastructure/vmware?topic=VMware-create-esx-vm#create-esx-vm)에서는 첫 번째 VM을 배치하는 프로세스를 단계별로 안내합니다.

게스트 OS에 SAP NetWeaver 기반 소프트웨어를 배치하려면 [SAP Note 2414097![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}에 언급된 운영 체제 중에서 게스트 OS를 선택해야 한다는 점에 유의하십시오.
