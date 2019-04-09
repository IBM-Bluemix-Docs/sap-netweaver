---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, SAP Application Performance Standard, SAPS, SAP Quick Sizer

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 4. 調整伺服器大小
{: #size_the_server}

在您決定打算要使用的 SAP 解決方案之後，下一步是判斷要支援 SAP 架構所需的 {{site.data.keyword.baremetal_long}} 數目，並確定伺服器已正確調整大小。
{: shortdesc}

## 瞭解 SAP 大小調整方法
{: #size_method}

以 SAP NetWeaver 為中心的應用程式，其 SAP 大小調整方法是根據 SAP 基準性能測試，例如來自 SAP 及實際客戶體驗的資訊。基本 SAP 工作負載單位是 SAP Application Performance Standard (SAPS)。SAPS 是由 SAP 產能規劃及效能測試人員所建立的傳輸量定義。例如，100 SAPS 在標準 SAP Sales and Distribution (SAP SD) 應用程式基準性能測試中，是定義為每小時 2,000 個完整商業處理的訂單明細行項目。這相當於「SAP 企業資源規劃 (SAP ERP)」解決方案中每小時 2,400 個 SAP 交易。處理器的能力是在 SAP 所認證的標準 (SAP SD) 基準性能測試期間進行測量。如需 SAP 認證的基準性能測試相關詳細資料，請參閱 [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://lenovopress.com/redp5073.pdf){: new_window}。此測試依處理程序以接近 100% CPU 負載且回應時間低於 1 秒來處理工作的能力來評定處理程序等級。

## 使用 SAP Quick Sizer
{: #quicksizer}

[SAP Quick Sizer ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://service.sap.com/quicksizer){: new_window} 是一款 SAP 為所有合作夥伴和客戶提供的 Web 型工具。調整大小資訊會直接輸入至該工具，然後在該工具調整 SAP NetWeaver 型的應用程式及非 SAP NetWeaver 型的應用程式的大小。它需要 SAP S 使用者 ID。

它會計算工作負載（使用 SAPS），並進行調整以容許適當的處理器使用。因此，如果需要每小時 4,800 個 SAP SD 基準性能測試交易的工作負載，則此工具對此計算的結果為 200 SAPS。如果容許的目標處理器負載為百分之 33，請對此進行調整，以找到具備百分之百時具有 600 SAPS 能力（百分之 33 時為 200 SAPS）的處理器。如需 SAPS 計算的相關詳細資料，請參閱 [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://lenovopress.com/redp5073.pdf){: new_window}。

大小調整方法可能比較保守，請考量此事實：伺服器的 SAPS 數目是根據只執行特定 SAP SD 工作負載的高度調整 SAP 系統而計算出來的。視 SAP 應用程式類型、系統中的任何自訂配置或自訂編碼而定，您的結果可能不同。此外，您專案的需求可能不同，例如概念驗證 (PoC) 或關於效能和回應時間。

## 選擇 {{site.data.keyword.cloud_notm}} 裸機伺服器
{: #choose_server}

在決定了 SAP 應用程式且 SAPS 數目已透過 SAP Quick Sizer 或基於您的現行架構計算之後，您可以開始從提供的模型中選擇伺服器。表 1 包含已針對 SAP NetWeaver 認證之 {{site.data.keyword.baremetal_short}} 的 SAPS 數目。
請參閱 [SAP Standard Application Benchmarks ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.sap.com/about/benchmark.html){: new_window}，來取得憑證文件。

表 1 列出的所有支援的伺服器類型都符合 SAP 認證的那些伺服器類型，並具有已發佈名稱，而且已在 [SAP 附註 2414097 ![所有支援的伺服器類型](../../icons/launch-glyph.svg "外部鏈結圖示")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} 中驗證；請按一下[這裡![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.sap.com/dmc/exp/2014-09-02-hana-hardware/enEN/power-systems.html){: new_window}來取得完整的清單。請注意，已發佈的名稱可能會變更。

表 1. {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 已針對 SAP NetWeaver 認證

|伺服器類型  |SAPS |RAM |
| --- | --- | --- |
|BI.S1.NW32 | 10980 |32 GB |
|BI.S1.NW128 | 54130 |128 GB |
|BI.S1.NW256 | 55020 |256 GB |
| BI.S2.NW512 | 65520 |512 GB |
| BI.S3.NW32 | 11970 |32 GB |
| BI.S3.NW64 | 12750 | 64 GB |
| BI.S3.NW192 | 78850 | 192 GB |
| BI.S3.NW384 | 79430 | 384 GB |
| BI.S3.NW768 | 79630 | 768 GB |

## 移轉現有的 SAP 系統
{: #migrating}

如果您打算將現有的 SAP 系統從任何來源移轉至 {{site.data.keyword.cloud_notm}} 環境，則可以從現行環境的 SAPS 數目來決定 SAPS 數目。請使用現行工作負載的資訊（使用的 CPU 及 RAM），並從 [SAP Standard Application Benchmarks ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.sap.com/about/benchmark.html){: new_window} 中取得 CPU 的 SAPS 對等項目。

## 後續步驟

 [5. 決定配置](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration)
