---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, SAP landscape, SAP Business Suite, SAP Business Warehouse, SAP BW

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: .faq}

# 規劃系統架構
{: #planning-your-system-landscape}

SAP *架構*是包含兩個以上的 SAP *系統*的群組，其通常包括開發、品質及測試和正式作業。一個 SAP 系統是由一個以上的 *SAP 實例*組成，它們是同時啟動和停止的一個處理程序群組。如需 SAP 架構的相關資訊，請參閱 [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://lenovopress.com/redp5073.pdf){: new_window}。
{: shortdesc}

針對市場中的所有 SAP 解決方案，有數個可能的架構配置，例如伺服器（大小）/儲存空間（大小）。這些解決方案包括 SAP NetWeaver 型產品，例如 [SAP Business Suite ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://open.sap.com/courses/suitehana1){: new_window}、SAP Business Warehouse，以及所有特定的 SAP 附加程式，{{site.data.keyword.cloud}} SAP 認證基礎架構中的伺服器支援它們。其他需要記住的解決方案為任何非 SAP NetWeaver 型的 SAP 解決方案，以及可能與 SAP 整合的任何協力廠商軟體。如果您計劃在 {{site.data.keyword.cloud}} IaaS 架構中配置非 SAP NetWeaver 型或協力廠商軟體，請聯絡 [SAP 支援中心 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://support.sap.com/en/index.html){: new_window}。

當您根據您規劃執行的應用程式、潛在成長及效能來決定伺服器的大小時，您希望越詳細越好。此外，請記住您的應用程式的儲存空間和記憶體需求。架構中的 SAP 系統具有連線功能（彼此之間或與外部系統之間）的特定需求。如需相關資訊，請參閱[規劃 SAP 架構時要考量的項目](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations)。

表 1 包含規劃程序內的步驟。請利用它來協助建置您的目標 SAP 架構。

表 1. 規劃程序概觀

|步驟 |詳細資料 |
| --- | --- |
|1 |[取得 SAP 及 {{site.data.keyword.cloud_notm}} 認證和建立帳戶](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-get_sap_ibm_credentials#get_sap_ibm_credentials) |
|2 |[檢閱任何相關 SAP 及 {{site.data.keyword.cloud_notm}} 文件](/docs/infrastructure/sap-netweaver/sap-review-doc.html) |
|3 |[決定 SAP NetWeaver 應用程式](/docs/infrastructure/sap-netweaver/sap-determine-apps.html) |
|4 |[調整伺服器大小](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server) |
|5 |[決定配置](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration) |

## 後續步驟

在表 1 選取適當的步驟，以開始規劃您的 SAP 架構。
