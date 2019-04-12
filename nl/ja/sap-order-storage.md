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

# 1. ストレージを注文する
{: #order_storage}

{{site.data.keyword.blockstoragefull}}、{{site.data.keyword.filestorage_full_notm}}、Network Attached Storage (NAS) は、{{site.data.keyword.cloud_notm}}{{site.data.keyword.baremetal_short}} のデプロイ後に注文します。

## {{site.data.keyword.cloud_notm}} ストレージの注文
{: #ibm_storage}

[{{site.data.keyword.blockstorageshort}}のプロビジョンと管理](/docs/infrastructure/BlockStorage?topic=BlockStorage-getting-started#getting-started)または [{{site.data.keyword.filestorage_full_notm}} のプロビジョンと管理](/docs/infrastructure/FileStorage?topic=FileStorage-orderingConsole#orderingConsole)の手順を実行して、バックアップ/リストア用のストレージ・ソリューションを注文できます。使用するストレージ・タイプ、注文方法、サーバーへのデプロイ方法を決定するプロセスが記載されています。

「*SAP NetWeaver Quick Reference Guides (for Microsoft Windows* or *for Red Hat Enterprise Linux*)」には、{{site.data.keyword.cloud_notm}}{{site.data.keyword.blockstorageshort}} を含むサーバー構成とデプロイメントに関する包括的な説明と、Linux と Windows 用のデプロイメント例に基づいた iSCSI 構成手順が記載されています。

VMware ESXi の場合、{{site.data.keyword.cloud_notm}} ストレージ・タイプをデータ・ストアとして使用できます。そのようにすると、そのデータ・ストアは iSCSI デバイスとして ESXi にマップされます。 [iSCSI の VMware ESXi へのマウント](/docs/infrastructure/vmware?topic=VMware-mount-iscsi-esxi#mount-iscsi-esxi)の手順に従って、iSCSI デバイスを ESXi にマップします。

## 次のステップ

  [2. 環境を保護する](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. ESX ハイパーバイザーにゲスト OS をインストールする (オプション)](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. SAP ソフトウェアとアプリケーションをダウンロードしてインストールする](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
