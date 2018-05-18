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

# IBM Cloud for SAP アプリケーション概説チュートリアル
{: #getting-started}

{{site.data.keyword.IBM_notm}} と SAP は、ハードウェア、ソフトウェア、クラウド、サービス、財務などの複数の分野で 40 年以上にわたりコラボレーションを行ってきました。現在は、{{site.data.keyword.baremetal_long}} 上で SAP NetWeaver ベースのアプリケーションを実行するためのコラボレーションを行っています。このオファリングには、シングル・ソケット (32 GB) とデュアル・ソケット (128 GB、256 GB、512 GB) という 4 つのメモリー・オプションがあります。これらはすべて、世界中の 60 を超える {{site.data.keyword.cloud_notm}} データ・センターで利用できます。
{: shortdesc}

ここでは、{{site.data.keyword.cloud_notm}} 上の SAP NetWeaver ベースの SAP 製品とサブスクリプションをサポートするためのインフラストラクチャーのプロビジョニングとインストールに関する推奨事項を記載します。これは、SAP NetWeaver 実装関連の資料を置き換えるものではありません。ここでの目的は、SAP のインストールを開始できるようにインフラストラクチャーの計画とプロビジョニングを支援することです。SAP のインストール (データベースのインストールを含む) とオンプレミス環境のインストールに違いはありません。{{site.data.keyword.cloud_notm}} 環境での SAP システムの操作に役立つ推奨事項とガイドラインをここに記載します。

{{site.data.keyword.cloud_notm}} インフラストラクチャーを素早く構築するために役立つ手順を表 1 に記載します。
<table>
   <CAPTION>表 1. クイック・スタート手順</CAPTION>
   <THEAD>
   <TR>
   <th>作業</th>
   <th>詳細</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>1. お客様の実装に関連する IBM Cloud と SAP の内容を読む</td>
   <td>組織として初めて IBM Cloud を使用する場合は、以下の情報が役に立つことがあるため、計画段階の前にお読みください。
   <li><a href="https://ibm.com/cloud-computing/">IBM Cloud の概要</a></li>
   <li><a href="https://ibm.com/cloud/get-started">Getting started with IBM Cloud</a></li>
   <li><a href="https://help.sap.com/nw75#section2">SAP NetWeaver 7.5 インストールとアップグレードのガイド</a>: インストール・ガイドをダウンロードしてください</li>
   
   以下の SAP 資料も役立ちます。
   <li><a href="https://www.sapappsdevelopmentpartnercenter.com/en/faq/program-faqs_2/how-to-receive-an-s-user-to-access-the-s_77/">SAP S ユーザー ID のセットアップ方法</a></li>
   <li><a href="https://help.sap.com/netweaver">SAP NetWeaver ヘルプ</a></li>
   <li><a href="https://support.sap.com">SAP Notes</a>。SAP S ユーザー ID が必要です</li>
   </td>
   <tr>
   <td>2. IBM Cloud に登録する</td>
   <td>IBM Cloud アカウントのセットアップ手順については、<a href="https://console.bluemix.net/docs/admin/adminpublic.html#signing-up-for-ibm-cloud">IBM Cloud への登録</a>を参照してください。</td>
 <tr>
   <td>3. IBM Cloud インフラストラクチャーのカスタマー・ポータルにアクセスする</td>
   <td><a href="https://control.softlayer.com">IBM Cloud インフラストラクチャーのカスタマー・ポータル</a>は、コンピュート、接続、ストレージ、ネットワーク、データ・センターといったすべてのインフラストラクチャー・コンポーネントへの入り口となるグラフィカル・ゲートウェイです。カスタマー・ポータルにアクセスするには、<a href="https://console.bluemix.net/docs/customer-portal/getting-started.html#getting-started">IBM ID とパスワード</a>が必要です。</td> 
   <tr>
   <td>4. システム・ランドスケープを計画する</td>
   <td><a href="sap-planning-your-system-landscape.html#planning-your-system-landscape">システム・ランドスケープの計画</a>の情報を使用して、SAP NetWeaver ワークロードをサポートするように IBM Cloud 環境を設計、サイズ設定、プロビジョンします。</td>  
 <tr>
   <td>5. システムをプロビジョンする</td>
   <td><a href="sap-provision-environment.html#provision_environment">SAP NetWeaver 環境のプロビジョニング</a>の手順と情報を使用して、IBM Cloud インフラストラクチャーをセットアップします。クイック・リファレンス・ガイドの手順を使用することもできます。</td>
   <tr>
   <td>6. SAP NetWeaver をインストールする</td>
   <td>サーバーがオンプレミスに置かれている場合と同様に、SAP NetWeaver を IBM Cloud インフラストラクチャーにインストールします。詳しくは、<a href="sap-installing-SAP-landscape.html#install_sap">SAP ソフトウェアとアプリケーションをダウンロードしてインストールする</a>を参照してください。</td>
   </td>
   </tr>
   </TBODY>
   </table>