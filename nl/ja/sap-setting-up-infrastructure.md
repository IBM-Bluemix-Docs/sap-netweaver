---



copyright:
  years: 2017, 2018
lastupdated: "2010-08-10"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 2. インフラストラクチャーをセットアップする
{: #set_up_infrastructure}

SAP NetWeaver {{site.data.keyword.baremetal_long}}、ネットワーク、セキュリティー、ストレージ、オペレーティング・システム (OS) をセットアップする場合の指針を以下のセクションに記載します。 ご質問があれば、[{{site.data.keyword.cloud_notm}} サポート](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support)にご連絡ください。

## サーバーの注文
{: order-server}

以下の手順で {{site.data.keyword.baremetal_short}}を注文します。 追加情報については、[カスタム・ベアメタル・サーバーの作成](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#building-a-custom-bare-metal-server)を参照してください。

1. ユーザー固有の資格情報を使用して、[{{site.data.keyword.cloud_notm}} インフラストラクチャーのカスタマー・ポータル](https://control.softlayer.com)にログインします。
2. 「利用料金の要約」ページで**「アカウント」**>**「注文」**をクリックします。
3. 「デバイス」ページの「{{site.data.keyword.baremetal_short}}」の下にある**「月単位」**リンクをクリックします。 「サーバー・リスト」ダイアログ・ボックスが表示されます。
4. SAP 認定サーバーがリストの先頭に示されます。 **「月ごとの開始価格 (STARTING PRICE PER MONTH)」**の下のハイパーリンクをクリックして、該当するサーバーを選択し、「構成/オーダー (Configure/Order)」ページに移動します。 

   SAP NetWeaver 認定サーバーは、「CPU モデル」の下の **-NW** で見分けることができます。 Red Hat ベースのサーバー構成については、ステップ 7 と『サーバー・オプションの選択』のステップ 1 で説明します。これらの手順は、Microsoft Windows の場合も同じです。 VMware の場合、選択肢は限られていますが、ステップは同じであることに注意してください。
   
5. 注文するサーバーの数を**「数量」**フィールドに入力し、**「データ・センター」**でデータ・センターを選択します。
6. **「サーバー」**、**「RAM」**、プライベート・ストレージ・オプションは、サーバーの選択内容に基づいてデフォルト設定が決まるので、変更できません。 サーバーを注文した後で、{{site.data.keyword.IBM_notm}} {{site.data.keyword.blockstorageshort}} for {{site.data.keyword.cloud_notm}} または {{site.data.keyword.filestorage_full_notm}} と Network Attached Storage (NAS) を注文します。
7. **「オペレーティング・システム」**で、Microsoft、Red Hat、または SUSE を選択し、サーバー用の特定のオペレーティング・システムまたは VMware ハイパーバイザーを選択します。**注**: オペレーティング・システムに関してライセンス持ち込み (BYOL) を行う場合は、**「その他」**>**「オペレーティング・システムなし」**を選択します。詳しくは、[ライセンス持ち込み (BYOL)](#byol) を参照してください。

## サーバー・オプションの選択
{: #select_options}

次の手順では、構成に追加するディスクのタイプと数を選択します。 RAID (Redundant Arrays of Independent Disks) ストレージ・グループと、RAID ストレージ・グループ上のパーティショニング・レイアウトに関して、複数の異なるオプションを選択することもできます。 詳しくは、[RAID について](https://console.bluemix.net/docs/bare-metal/what-raid.html#about-raid)か、[{{site.data.keyword.cloud_notm}} サポート](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support)を参照してください。

1. **「SAP 認定サーバー (SAP Certified Servers)」**の下で、サーバーの使用計画に基づいて選択を行います。 詳しくは、[Design Decision Tool](https://github.com/ibm-cloud-architecture/infrastructure-design-decision-tool) (このツールが表示されるまでスクロールダウンする) または [{{site.data.keyword.cloud_notm}} サポート](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support)を参照してください。
2. ページの下部にある**「注文に追加」**ボタンをクリックします。

## 拡張システム構成のセットアップ
{: #adv_config}

1. [拡張システム構成](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html#advanced-server-configuration-options)の指針に従って、**「拡張システム構成」**ウィンドウで指定する値を決定します。

SAP ホスト名は、最大 13 文字の英数字で構成する必要があります。 SAP ホスト名について詳しくは、[SAP Notes 611361](https://launchpad.support.sap.com/#/611361) と [129997](https://launchpad.support.sap.com/#/129997) を参照してください。 

ご使用の環境のパブリック/プライベート・セットアップについては決定済みで、今後は以下のことを計画しているとします。
  * 相互に通信する必要のある複数の SAP システムをインストールする。*または*
  * 3 層 SAP セットアップ (データベース・インスタンスとアプリケーション・インスタンスが別々のハードウェア上にある) を選択する。
  
この場合、内部アドレスと外部アドレスの設定を反映するように名前解決が行われることを確認してください。 外部アドレスは、完全修飾ドメイン名 (FQDN) によって解決されるサーバーのホスト名と一致するようにします。 

内部アドレスはドメイン・ネーム・システム (DNS) に表示されません。 内部 IP をサーバー間の通信に使用する必要があるので、`/etc/hosts` のファイルまたは Microsoft Windows の「host」ファイルを適宜拡張するようにしてください。 この情報は、VMware ESXi ベースのデプロイメントのゲスト・オペレーティング・システムにも適用される場合があります。

## 選択内容の確認
{: #confirm_selections}

1. 「ご清算」ページで選択内容を確認し、**「クラウド・サービスのご利用条件 (Cloud Service terms)」**と**「サード・パーティー・ソフトウェアのご使用条件 (3rd Party Software Agreement)」**のチェック・ボックスをクリックします。
2. 「アカウントの作成: 請求の入力 (Create Account: Enter Billing)」までスクロールダウンし、請求に使用するクレジット・カードの**「支払いタイプ」、「名前」、「カード」**と**「有効期限」**(日付) を入力します。
3. **「注文の送信」**ボタンをクリックします。 注文番号を表示する画面にリダイレクトされます。 画面はオーダーの受領書でもあるので、印刷できます。

_{{site.data.keyword.cloud_notm}} Order ## has been approved_ という件名の確認 E メールが、お客様のプロファイルにある E メール・アドレスに送信されます。 この E メールは、サーバーが承認され、デプロイ中であることを示す通知です。 デプロイ後に別の通知が送信され、サーバーが使用可能であり、[{{site.data.keyword.cloud_notm}} インフラストラクチャー・カスタマー・ポータル](https://control.softlayer.com)で管理できることが通知されます。

## ライセンス持ち込み (BYOL)
{: #byol}

自分でオペレーティング・システム・ライセンスを所有している場合、ベンダーの指示に基づいて、それを {{site.data.keyword.baremetal_short}} にインストールします。詳しくは、[OS なしオプション](https://console.bluemix.net/docs/bare-metal/introduction-no-os.html#how-to-install-an-operating-system-on-a-no-os-server-)を参照してください。

## 次のステップ

これで、{{site.data.keyword.baremetal_short}}の管理を開始する準備ができました。 次の手順については、[SAP NetWeaver 環境の管理](/docs/infrastructure/sap-netweaver/sap-manage-environment.html)を参照してください。
