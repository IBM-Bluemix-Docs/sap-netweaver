---



copyright:
  years: 2018
lastupdated: "2018-01-25"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. ストレージを注文する
{: #order_storage}

{{site.data.keyword.blockstoragefull}}、{{site.data.keyword.filestorage_full_notm}}、Network Attached Storage (NAS) は、{{site.data.keyword.cloud_notm}}{{site.data.keyword.baremetal_short}} のデプロイ後に注文します。 

## {{site.data.keyword.cloud_notm}} ストレージの注文
{: #ibm_storage}

[{{site.data.keyword.blockstorageshort}} のプロビジョニングと管理](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage)または [{{site.data.keyword.filestorage_full_notm}}のプロビジョニングと管理](https://console.bluemix.net/docs/infrastructure/FileStorage/provisioning-file-storage.html#provisioning-and-managing-ibm-file-storage-for-ibm-cloud)の手順に従って、バックアップとリストアのストレージ・ソリューションを注文できます。使用するストレージ・タイプ、注文方法、サーバーへのデプロイ方法を決定するプロセスが記載されています。

「*SAP NetWeaver Quick Reference Guides (for Microsoft Windows* or *for Red Hat Enterprise Linux*)」には、{{site.data.keyword.cloud_notm}}{{site.data.keyword.blockstorageshort}} を含むサーバー構成とデプロイメントに関する包括的な説明と、Linux と Windows 用のデプロイメント例に基づいた iSCSI 構成手順が記載されています。

VMware ESXi の場合、{{site.data.keyword.cloud_notm}} ストレージ・タイプをデータ・ストアとして使用できます。そのようにすると、そのデータ・ストアは iSCSI デバイスとして ESXi にマップされます。[iSCSI の VMware ESXi へのマウント](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi)の手順に従って、iSCSI デバイスを ESXi にマップします。

## NAS の注文
{: #order-nas}

データベースのアーカイブ・ログ・ファイル用のストレージが必要な場合、またはオンライン/オフライン・バックアップを頻繁に実行する必要がある場合は、NAS ストレージが、サーバーのローカル・ストレージ拡張機能としての重要な役割を果たす場合があります。NAS を注文してセットアップするには、[NAS/FTP ストレージの注文](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#ordering-nas-ftp-storage)の情報を参照してください。また、ネットワーク・ファイル・ストレージ (NFS) を Linux サーバーにマップする方法については、[Mounting NAS Storage in Linux](https://console.bluemix.net/docs/infrastructure/network-attached-storage/mount-nas-storage-linux.html#mounting-nas-storage-in-linux) を参照してください。[NAS ストレージは、NFS を使ってデータ・ストアとして VMware ESXi にマップすることもできます](https://console.bluemix.net/docs/infrastructure/network-attached-storage/connect-nas-storage-windows.html#connecting-to-nas-storage-in-windows)。

## 次のステップ

  [2. 環境を保護する](/docs/infrastructure/sap-netweaver/sap-secure-environment.html)

  [3. ESX ハイパーバイザーにゲスト OS をインストールする (オプション)](/docs/infrastructure/sap-netweaver/sap-installing-guest-operating-system-VMware-deployments.html)

  [4. SAP ソフトウェアとアプリケーションをダウンロードしてインストールする](/docs/infrastructure/sap-netweaver/sap-installing-SAP-landscape.html)
  
  [5. {{site.data.keyword.cloud_notm}} データ・センターへの接続をテストする](/docs/infrastructure/sap-netweaver/sap-testing-connectivity.html)
