---



copyright:
  years: 2018
lastupdated: "2018-06-28"


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

[{{site.data.keyword.blockstorageshort}} 프로비저닝 및 관리](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) 또는 [{{site.data.keyword.filestorage_full_notm}} 프로비저닝 및 관리](https://console.bluemix.net/docs/infrastructure/FileStorage/provisioning-file-storage.html#provisioning-and-managing-ibm-file-storage-for-ibm-cloud)의 단계를 사용하여 백업 및 복원 스토리지 솔루션을 주문할 수 있습니다. 사용자는 사용할 스토리지 유형, 주문 방법 및 이러한 스토리지의 서버 배치 방법을 결정하는 프로세스에 대한 안내를 받습니다.

*SAP NetWeaver 빠른 참조 안내서(Microsoft Windows* 또는 *Red Hat Enterprise Linux*용)에서는 Linux 및 Windows용 샘플 배치를 기반으로 {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}} 및 iSCSI 구성 단계를 포함한 전체 서버 구성 및 배치를 단계별로 안내합니다.

VMware ESXi의 경우에는 {{site.data.keyword.cloud_notm}} 스토리지 유형을 데이터 저장소로 사용할 수 있으며, 이 경우 이는 ESXi에 iSCSI 디바이스로 맵핑됩니다. iSCSI 디바이스를 ESXi에 맵핑하려면 [iSCSI VMware ESXi 마운트](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi)의 단계를 참조하십시오.

## NAS 주문
{: #order-nas}

NAS 스토리지는 데이터베이스에 대한 아카이브된 로그 파일, 또는 빈번한 온라인 및 오프라인 백업을 위한 스토리지가 필요한 경우 서버의 로컬 스토리지를 확장시켜주는 유용한 디바이스입니다. NAS를 주문하고 설정하려면 [NAS/FTP 스토리지 주문](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#ordering-nas-ftp-storage)에 방문하십시오. 또한 [Linux에서의 NAS 스토리지 마운트](https://console.bluemix.net/docs/infrastructure/network-attached-storage/mount-nas-storage-linux.html#mounting-nas-storage-in-linux)를 참조하여 네트워크 파일 스토리지(NFS)를 Linux 서버에 맵핑하는 방법을 확인하십시오. [NAS 스토리지는 NFS를 통해 VMware ESXi에 데이터 저장소로 맵핑될 수도 있습니다](https://console.bluemix.net/docs/infrastructure/network-attached-storage/connect-nas-storage-windows.html#connecting-to-nas-storage-in-windows).

## 다음 단계

  [2. 환경 보안](/docs/infrastructure/sap-netweaver/sap-secure-environment.html)

  [3. ESX 하이퍼바이저에 게스트 OS 설치(선택사항)](/docs/infrastructure/sap-netweaver/sap-installing-guest-operating-system-VMware-deployments.html)

  [4. SAP 소프트웨어 및 애플리케이션 다운로드 및 설치](/docs/infrastructure/sap-netweaver/sap-installing-SAP-landscape.html)
  
  
