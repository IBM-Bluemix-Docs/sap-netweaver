---



copyright:
  years: 2017, 2018
lastupdated: "2018-01-25"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# IBM Cloud IaaS 상의 SAP NetWeaver 개요
IaaS(Infrastructure as a Service) 환경은 다양한 구성요소(데이터 센터, 컴퓨팅, 연결, 스토리지 및 네트워크)로 구성됩니다.  

## 데이터 센터

사용자는 북아메리카 및 남아메리카, 유럽, 아시아 및 오스트레일리아 전역의 데이터 센터를 통해, 클라우드 리소스를 필요한 위치에, 필요한 시간에 프로비저닝할 수 있습니다. 각 데이터 센터는 {{site.data.keyword.cloud_notm}} 글로벌 사설 네트워크에 연결되어 있어 세계 어디서든 빠르고 효율적으로 데이터를 전송할 수 있게 해 줍니다. 

{{site.data.keyword.cloud_notm}} 데이터 센터 및 상호접속 위치(PoP)에 대한 자세한 정보는 [데이터 센터](https://www.ibm.com/cloud-computing/bluemix/data-centers){: new_window}를 참조하십시오. 

## 베어메탈 서버

{{site.data.keyword.baremetal_long}}는 제한된 사용자 정의가 가능한 실제 서버입니다. 이러한 서버는 사용자 또는 사용자의 고객 전용으로, 서버 리소스를 포함한 모든 부분은 다른 {{site.data.keyword.cloud_notm}} 고객과 공유되지 않습니다. 이러한 서버는 사용자 또는 사용자의 고객이 관리하며 하이퍼바이저 없이 프로비저닝됩니다. 

베어메탈 서버에서는 사용자 정의가 제한되어 있으므로, 1 - 4시간 내에 신속히 프로비저닝할 수 있습니다. 빠른 프로비저닝은 경쟁 앱보다 먼저 앱을 시장에 출시하는 데 도움이 됩니다. 

SAP 인증 서버는 사전 구성된 수량의 RAM과 CPU를 포함하므로, 다양한 RAM 및 CPU 조합이 제공됩니다. 이러한 조합은 주문 프로세스 중에, 또는 서버가 배치된 후의 지원 티켓을 통해 변경할 수 *없습니다*. 

프로젝트에서 시각화 계층을 필요로 하는 경우, SAP NetWeaver 오퍼링은 VMware ESXi를 사용하여 배치되는 {{site.data.keyword.baremetal_short}}를 주문하는 선택사항을 포함합니다. ESX 인스턴스는 사용자의 데이터 센터에 배치되므로 전적으로 사용자가 제어합니다. 이 시스템은 네트워크 관련으로는 완전히 구성되어 있습니다(스토리지와 같은 추가 구성은 사용자에 따라 달라짐). 프로젝트를 성공적으로 시작하려면 담당자 중에 ESX 관리에 대한 지식이 있는 사람을 두는 것이 좋습니다. 

베어메탈 서버에 대한 자세한 정보는 [베어메탈 서버 정보](https://console.bluemix.net/docs/bare-metal/index.html#about-bare-metal-servers)를 참조하십시오.  

## 운영 체제

SAP NetWeaver 기반 시스템을 배치하는 데 필요한 게스트 운영 체제(OS)의 목록은 [SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097){: new window}을 참조해야 합니다. SAP Note에 액세스하려면 SAP S-사용자 ID가 필요합니다. 게스트 OS의 라이센싱은 사용자가 부담합니다. 

## 네트워크 연결

{{site.data.keyword.cloud_notm}} 계정이 설정되면 {{site.data.keyword.cloud_notm}} Virtual Cloud Network에 대한 가상 사설망(VPN) 연결이 자동으로 부여됩니다. 기본적으로 서버에는 공인 및 사설 IP 주소가 있습니다. 서버를 개인용으로 사용하려는 경우에는 서버가 프로비저닝된 후 공용 인터페이스를 끄거나 서버를 개인용으로 주문할 수 있습니다. {{site.data.keyword.cloud_notm}} VPN에 대한 자세한 정보는 [가상 사설망(VPN) 시작하기](https://console.bluemix.net/docs/infrastructure/iaas-vpn/getting-started.html#getting-started-with-virtual-private-networking-vpn-)를 참조하십시오. 

## 스토리지
{: #storage}

로컬 스토리지는 {{site.data.keyword.baremetal_short}}와 함께 제공되며 {{site.data.keyword.cloud_notm}} 사설 네트워크 가상 LAN(VLAN)을 사용하여 관리자 액세스를 방해하지 않는 동시에 엔터프라이즈급 보안을 제공하는 데 도움을 줍니다. 이는 OS와 같이 I/O 요구사항이 높으며 스토리지 사용량이 많은 애플리케이션, 그리고 데이터베이스 및 애플리케이션 소프트웨어에 대해 적합합니다. SAP NetWeaver 서버 디스크 공간은 서버 구성 방법에 따라 다릅니다. 서버에 있는 로컬 스토리지가 워크로드에 비해 충분하지 않은 경우에는 [{{site.data.keyword.cloud_notm}} 지원](https://console.bluemix.net/docs/support/index.html#getting-customer-support)에 확장 선택사항에 대해 문의하십시오. 

{{site.data.keyword.cloud_notm}}에는 SAP NetWeaver의 백업 및 복원을 수행하기 위해 선택할 수 있는 두 가지 유형의 스토리지(블록 및 파일)가 있습니다. 두 유형은 모두 스토리지 요구사항을 판별하는 데 사용되는 IOPS(Input/output Operations Per Second)를 사용합니다. IOPS는 50/50으로 읽기/쓰기가 혼합된 16KB 블록 크기를 기반으로 측정됩니다. 볼륨에서 최대 IOPS를 달성하려면 적절한 네트워크 리소스가 갖추어져 있어야 합니다. 기타 고려사항에는 스토리지 외부 및 호스트 측의 사설 네트워크 사용 및 애플리케이션 고유 튜닝(IP 스택 및 큐 깊이)이 있습니다. 스토리지 계층 및 성능에 대한 자세한 정보는 [블록 스토리지 시작하기](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) 및 [파일 스토리지 시작하기](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage)를 참조하십시오. 

{{site.data.keyword.cloud_notm}}에서는 사용자 디바이스에 맞는 빠르고 비용 효율적인 백업 솔루션을 원하는 사용자를 위해 NAS(Network Attached Storage) 또한 제공합니다. NAS는 다음과 호환됩니다. 
  * Red Hat Enterprise Linux(RHEL) for SAP Business Applications 6.X OS
  * Parallels Plesk Panel, cPanel 및 WHM의 FTP(File Transfer Protocol)
  * CIFS(Common Internet File System) 프로토콜을 사용하는 표준 Windows 프로시저를 통한 Microsoft Windows Server
  
NAS 및 FTP 스토리지는 월별로 비용 청구되며 다양한 스토리지 크기로 사용 가능합니다. NAS 및 FTP 스토리지와의 상호작용은 주로 OS의 명령행 또는 터미널이나, {{site.data.keyword.cloud_notm}} 인프라 고객 포털에 있는 패널에서의 마우스 클릭 상호작용을 통해 이뤄집니다. 

{{site.data.keyword.cloud_notm}} 환경의 NAS에 대한 자세한 정보는 [NAS 시작하기](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#getting-started-with-nas)에 있습니다. 

## 배치 및 관리

{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}는 {{site.data.keyword.cloud_notm}} 고객 계정을 작성한 후 {{site.data.keyword.cloud_notm}} 인프라 고객 포털 또는 API를 통해 배치됩니다. 서버는 고객 포털, API 또는 명령행 인터페이스(CLI)를 통해 관리할 수 있습니다. 자세한 정보는 [베어메탈 서버 정보](https://console.bluemix.net/docs/bare-metal/index.html#about-bare-metal-servers)에서 찾을 수 있습니다. 

## 지원

[{{site.data.keyword.cloud_notm}} 고객 지원](https://console.bluemix.net/docs/support/index.html#getting-customer-support)은 대화, 전화 및 티켓 기반 지원을 포함한 다양한 창구를 사용하여 발생할 수 있는 질문 및 문제에 대한 지원을 제공합니다. 고객 지원은 모든 {{site.data.keyword.cloud_notm}} 고객에게 무료로 제공되며 매일 작성되는 티켓의 대부분을 당일 처리합니다. 자세한 정보는 [고객 지원 받기](https://console.bluemix.net./docs/support/index.html#getting-customer-support)를 참조하십시오. 
