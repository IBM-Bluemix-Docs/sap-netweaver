---



copyright:
  years: 2017, 2018
lastupdated: "2018-02-27"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# IBM Cloud for SAP Applications 튜토리얼 시작하기
{: #getting-started}

{{site.data.keyword.IBM_notm}}과 SAP는 40여년 간 하드웨어, 소프트웨어, 클라우드, 서비스 및 금융을 포함한 다양한 분야에서 협업해 왔습니다. 이제 두 회사는 SAP NetWeaver 기반 애플리케이션을 {{site.data.keyword.baremetal_long}}에서 실행하기 위해 협업합니다. 이 오퍼링은 세계 각국에 있는 60개 이상의 {{site.data.keyword.cloud_notm}} 데이터 센터에서 모두 사용 가능한 네 가지 메모리 선택사항(싱글 소켓(32GB) 및 듀얼 소켓(128GB, 256GB 및 512GB))을 포함합니다.
{: shortdesc}

이 컨텐츠는 SAP NetWeaver 기반 SAP 제품을 지원하기 위한 인프라의 프로비저닝 및 설치와 {{site.data.keyword.cloud_notm}}에서의 구독에 대한 권장사항을 제공합니다. 이는 어떤 SAP NetWeaver 구현 관련 문서도 대체하지 않습니다. 이 컨텐츠의 목적은 SAP 설치를 시작할 수 있도록 인프라를 계획하고 프로비저닝을 수행하는 데 도움을 주는 것입니다. SAP 설치(데이터베이스 설치 포함)는 온프레미스 환경에 대한 설치와 다르지 않습니다. {{site.data.keyword.cloud_notm}} 환경에서 SAP 시스템을 운영하는 데 도움을 주기 위해 권장사항 및 가이드라인이 제공됩니다. 

표 1에는 신속히 {{site.data.keyword.cloud_notm}} 인프라를 빌드하는 데 도움을 주는 단계가 포함되어 있습니다. 
<table>
   <CAPTION>표 1. 빠른 시작 단계</CAPTION>
   <THEAD>
   <TR>
   <th>태스크</th>
   <th>세부사항</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>1. 구현과 관련된 IBM Cloud 및 SAP 컨텐츠 읽기</td>
   <td>조직에서 IBM Cloud를 처음으로 사용하는 경우에는 다음 정보가 유용하며, 계획 단계 전에 이들 정보를 읽어야 합니다.
   <li><a href="https://ibm.com/cloud-computing/">IBM Cloud의 개념</a></li>
   <li><a href="https://ibm.com/cloud/get-started">IBM Cloud 시작하기</a></li>
   <li><a href="https://help.sap.com/nw75#section2">SAP NetWeaver 7.5 설치 및 업그레이드 정보</a>: 설치 안내서 다운로드</li>
   
   다음 SAP 문서 또한 유용합니다. 
   <li><a href="https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77/">SAP S-사용자 ID 설정 방법</a></li>
   <li><a href="https://help.sap.com/netweaver">SAP NetWeaver 도움말</a></li>
   <li><a href="https://support.sap.com">SAP Note</a>: SAP S-사용자 ID 필요</li>
   </td>
   <tr>
   <td>2. IBM Cloud에 가입</td>
   <td><a href="https://console.bluemix.net/docs/admin/adminpublic.html#signing-up-for-ibm-cloud">IBM Cloud 가입</a>에 방문하여 IBM Cloud 계정을 설정하는 단계를 알아보십시오. </td>
 <tr>
   <td>3. IBM Cloud 인프라 고객 포털에 액세스</td>
   <td><a href="https://control.softlayer.com">IBM Cloud 인프라 고객 포털</a>은 컴퓨팅, 연결, 스토리지, 네트워크 및 데이터 센터와 같은 모든 인프라 구성요소에 대한 그래픽 게이트웨이입니다. 고객 포털에 액세스하려면 <a href="https://console.bluemix.net/docs/customer-portal/getting-started.html#getting-started">IBM ID 및 비밀번호</a>가 필요합니다. </td> 
   <tr>
   <td>4. 시스템 랜드스케이프 계획</td>
   <td><a href="sap-planning-your-system-landscape.html#planning-your-system-landscape">시스템 랜드스케이프 계획</a>에 있는 정보를 사용하여 SAP NetWeaver 워크로드를 지원하는 데 필요한 IBM Cloud 환경을 설계하고, 크기 지정하고 프로비저닝하십시오. </td>  
 <tr>
   <td>5. 시스템 프로비저닝</td>
   <td><a href="sap-provision-environment.html#provision_environment">SAP NetWeaver 환경 프로비저닝</a>에 있는 단계 및 정보를 사용하여 IBM Cloud 인프라를 설정하십시오. 빠른 참조 안내서에 있는 단계 또한 사용할 수 있습니다. </td>
   <tr>
   <td>6. SAP NetWeaver 설치</td>
   <td>SAP NetWeaver를 서버가 온프레미스인 경우와 마찬가지로 IBM Cloud 인프라에 설치하십시오. 자세한 정보는 <a href="sap-installing-SAP-landscape.html#install_sap">SAP 소프트웨어 및 애플리케이션 다운로드 및 설치</a>를 참조하십시오. </td>
   </td>
   </tr>
   </TBODY>
   </table>
