---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.Db2_on_Cloud_short}}, FAQs, VLAN, application server, SAP Certified, high availability, highly available

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# FAQ: IBM Cloud 上の SAP
{: #faqs}

## SAP NetWeaver を {{site.data.keyword.cloud_notm}} 上で実行するには DB2 が必要ですか?
{: faq}

[SAP Note 2414097 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} を定期的に確認してください。[SAP の製品出荷マトリクス (PAM) ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: new_window} も参照してください。ご使用のデータベースごとに異なるサービス・パックのセットが必要であるため、SAP Note に記載されているオペレーティング・システムに注意してください。

## {{site.data.keyword.Db2_on_Cloud_short}} が {{site.data.keyword.cloud_notm}} の認証用に選択された理由は何ですか?
{: faq}

{{site.data.keyword.Db2_on_Cloud_long_notm}} は {{site.data.keyword.IBM_notm}} 製品であり、{{site.data.keyword.cloud_notm}} は {{site.data.keyword.IBM_notm}} の一部であるため、認証用に選択されました。

## 分散 SAP 環境を複数の異なるデータ・センターに分割することはできますか?
{: faq}

分散 SAP インストールの場合は、すべてのノードを同じデータ・センターおよび VLAN セグメントに配置することをお勧めします。 このように配置しなかった場合は、待ち時間とタイムアウトが発生することがあり、SAP システムが応答しなくなる可能性があります。

## SAP アーキテクチャーで定義された SAP の高可用性を実現することはできますか?
{: faq}

サポートされる高可用性アーキテクチャーは、アプリケーション・サーバーのスケーリングのみです。 現在、高可用性サポート対応のハードウェアはありません。

## SAP 配布ソフトウェアを {{site.data.keyword.cloud_notm}} から直接ダウンロードすることはできますか?
{: faq}

現在、[SAP Service Marketplace ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://websmp201.sap-ag.de/){: new_window} との直接リンクは提供されていません。そのため、オンプレミス・デプロイメントの場合と同様に、配布 DVD をダウンロードする必要があります。
