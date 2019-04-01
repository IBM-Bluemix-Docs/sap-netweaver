---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.blockstorageshort}}, {{site.data.keyword.filestorage_full_notm}}, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.baremetal_short}}

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. 스토리지 주문
{: #order_storage}

{{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}를 배치한 후에는 {{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}} 및 NAS(Network Attached Storage)를 주문합니다.

## {{site.data.keyword.cloud_notm}} 스토리지 주문
{: #ibm_storage}

[{{site.data.keyword.blockstorageshort}} 프로비저닝 및 관리](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted#GettingStarted) 또는 [{{site.data.keyword.filestorage_full_notm}} 프로비저닝 및 관리](/docs/infrastructure/FileStorage?topic=FileStorage-orderingConsole#orderingConsole)의 단계를 사용하여 백업 및 복원 스토리지 솔루션을 주문할 수 있습니다. 사용자는 사용할 스토리지 유형, 주문 방법 및 이러한 스토리지의 서버 배치 방법을 결정하는 프로세스에 대한 안내를 받습니다.

*SAP NetWeaver 빠른 참조 안내서(Microsoft Windows* 또는 *Red Hat Enterprise Linux*용)에서는 Linux 및 Windows용 샘플 배치를 기반으로 {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}} 및 iSCSI 구성 단계를 포함한 전체 서버 구성 및 배치를 단계별로 안내합니다.

VMware ESXi의 경우에는 {{site.data.keyword.cloud_notm}} 스토리지 유형을 데이터 저장소로 사용할 수 있으며, 이 경우 이는 ESXi에 iSCSI 디바이스로 맵핑됩니다. iSCSI 디바이스를 ESXi에 맵핑하려면 [iSCSI VMware ESXi 마운트](/docs/infrastructure/vmware?topic=VMware-mounting-iscsi-vmware-esxi#mounting-iscsi-vmware-esxi)의 단계를 참조하십시오.

## 다음 단계

  [2. 환경 보안](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. ESX 하이퍼바이저에 게스트 OS 설치(선택사항)](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. SAP 소프트웨어 및 애플리케이션 다운로드 및 설치](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
