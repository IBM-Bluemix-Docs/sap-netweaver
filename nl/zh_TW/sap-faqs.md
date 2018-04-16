---



copyright:
  years: 2017, 2018
lastupdated: "2018-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 常見問題：SAP on IBM Cloud
{: #faqs}

## 我需要 Db2 在 {{site.data.keyword.cloud_notm}} 上執行 SAP NetWeaver 嗎？

定期檢查 [SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097)，並參照 [SAP Product Availability Matrix](https://apps.support.sap.com/sap/support/pam)。請注意 SAP Note 中提供的作業系統，因為您的資料庫需要不同的服務套件組。

## 為什麼針對 {{site.data.keyword.cloud_notm}} 的憑證會選擇 {{site.data.keyword.Db2_on_Cloud_short}}？

因為 {{site.data.keyword.Db2_on_Cloud_long_notm}} 是 {{site.data.keyword.IBM_notm}} 產品，而 {{site.data.keyword.cloud_notm}} 是為我們的憑證所選擇的 {{site.data.keyword.IBM_notm}} 的一部分。

## 我可以在不同的資料中心之間分割分散式 SAP 環境嗎？

若為分散式 SAP 安裝，最好讓所有節點都位於相同的資料中心和 VLAN 區段中。由此洐生的偏差會產生延遲和逾時，而使 SAP 系統變成無回應。

## 我可以依 SAP 架構所定義而達到 SAP 高可用性嗎？

唯一支援的高可用性架構是應用程式伺服器的調整大小。目前，沒有啟用硬體的高可用性支援。

## 我可以直接從 {{site.data.keyword.cloud_notm}} 下載 SAP 配送軟體嗎？

目前，我們不提供與 [SAP Service Marketplace](https://websmp201.sap-ag.de/) 的直接鏈結。因此，您應該下載發行套件 DVD，就像您今天對於內部部署所進行的動作一樣。
