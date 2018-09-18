---



copyright:
  years: 2018
lastupdated: "2018-05-18"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 4. サーバーのサイズを決定する
{: #size_the_server}

使用する計画の SAP ソリューションを決定したら、次のステップとして、SAP ランドスケープをサポートするために必要な {{site.data.keyword.baremetal_long}}の数を判別し、サーバーのサイズが正しいことを確認します。
{: shortdesc}

## SAP のサイズ決定の方法について
{: #size_method}

SAP NetWeaver を中心とするアプリケーションに関する SAP のサイズ決定は、 SAP からの情報や実際のカスタマー・エクスペリエンスなどの SAP ベンチマークに基づいて行います。 SAP ワークロードの基本単位は、SAP Application Performance Standard (SAPS) です。 SAPS とは、SAP のキャパシティー・プランニングとパフォーマンス・テストの担当者が作るスループットの定義のことです。 例えば、標準的な SAP Sales and Distribution (SAP SD) アプリケーション・ベンチマークでは、100 の SAPS は、1 時間あたり 2,000 の完全に業務処理された注文書明細の項目として定義されます。 これは、SAP Enterprise Resource Planning (SAP ERP) ソリューションの、1 時間あたり 2,400 の SAP トランザクションに相当します。 プロセッサーの能力は、SAP で認定されている標準的な (SAP SD) ベンチマーク・テストの際に測定されます。 SAP で認定されているベンチマーク・テストについて詳しくは、[*SAP Business Suite on IBM X6 Systems Reference Architecture*](https://lenovopress.com/redp5073.pdf) を参照してください。 このテストでは、1 秒未満の応答時間の作業を 100% に近い CPU 負荷で処理する能力でプロセスを評価します。

## SAP Quick Sizer の使用
{: #quicksizer}
  
[SAP Quick Sizer](https://service.sap.com/quicksizer) は、Web ベースのツールで、すべてのパートナーとお客様向けに SAP から提供されています。 サイズの情報はこのツールに直接入力され、このツールで SAP NetWeaver ベースのアプリケーションと SAP NetWeaver ベースでないアプリケーションのサイズが決定されます。 これには SAP S ユーザー ID が必要です。
  
このツールは、SAPS 内のワークロードを計算し、適切なプロセッサーを使用できるように調整します。 したがって、1 時間あたり 4,800 の SAP SD ベンチマーク・トランザクションのワークロードが必要な場合、このツールは 200 の SAPS と計算します。 33% のターゲット・プロセッサー負荷が許容されている場合は、この値を調整して 100% で 600 の SAPS (= 33% で 200) を処理する能力があるプロセッサーを見つけます。SAPS の計算について詳しくは、[*SAP Business Suite on IBM X6 Systems Reference Architecture*![外部リンク・アイコン]](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://lenovopress.com/redp5073.pdf){: new_window} を参照してください。

サイズ決定の方式は控えめであると感じるかもしれませんが、サーバーの SAPS 数は特定の SAP SD ワークロードのみを実行する高度に調整された SAP システムに基づいて計算されていることに留意してください。 システム内の SAP アプリケーションのタイプ、カスタム構成、またはカスタム・コーディングによっては、結果が異なる場合があります。 また、PoC (概念検証) やパフォーマンスと応答時間に関してなど、プロジェクトの要件が異なる場合があります。

## {{site.data.keyword.cloud_notm}} ベア・メタル・サーバーの選択
{: #choose_server}

SAP アプリケーションを決定し、SAPS 数を SAP Quick Sizer で計算するか、現在のランドスケープに基づいて計算し終えたら、提供されているモデルからサーバーを選択することができます。 SAP NetWeaver 用として認定されている{{site.data.keyword.baremetal_short}}の SAPS 数を表 1 に記載します。 認定文書については、[SAP Standard Application Benchmarks ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")]](https://www.sap.com/about/benchmark.html){: new_window} を参照してください。 

表 1 にリストされているすべてのサポート対象のサーバー・タイプは、SAP で認定されて名前が公開されているものと一致しており、[SAP Note 2414097![外部リンク・アイコン]](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} で検証されています。完全なリストについては、[ここ [外部リンク・アイコン]](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.sap.com/dmc/exp/2014-09-02-hana-hardware/enEN/power-systems.html){: new_window} をクリックしてください。公開された名前は変更される場合があることに注意してください。

表 1. SAP NetWeaver 用に認定されている {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}

| サーバー・タイプ | SAPS | RAM |
| --- | --- | --- |
| BI.S1.NW32 | 10980 | 32 GB |
| BI.S1.NW128 | 54130 | 128 GB |
| BI.S1.NW256 | 55020 | 256 GB |
| BI.S2.NW512 | 65520 | 512 GB |
| BI.S3.NW32 | 11970 | 32 GB |
| BI.S3.NW64 | 12750 | 64 GB |
| BI.S3.NW192 | 78850 | 192 GB |
| BI.S3.NW384 | 79430 | 384 GB |
| BI.S3.SW768 | 79630 | 768 GB |

## 既存の SAP システムのマイグレーション 
{: #migrating}

既存の SAP システムをいずれかのソースから {{site.data.keyword.cloud_notm}} 環境にマイグレーションすることを計画している場合は、現在の環境の SAPS 数から SAPS 数を判別できます。 現在のワークロード (使用されている CPU と RAM) に関する情報を使用して、ご使用の CPU に相当する SAPS を [SAP SD ベンチマーク結果![外部リンク・アイコン]](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.sap.com/about/benchmark.html){: new_window} から取得してください。

## 次のステップ

 [5. 構成を決定する](/docs/infrastructure/sap-netweaver/sap-determine-configuration.html)
