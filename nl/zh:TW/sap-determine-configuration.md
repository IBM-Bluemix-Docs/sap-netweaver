---



copyright:
  years: 2018
lastupdated: "2018-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 5. 決定配置
{: #determine_configuration}

使用 SAP NetWeaver 系統時，您有兩個部署選項：
  * 中央系統，為單一主機安裝（兩層）
  * 分散式系統，為多重主機安裝（三層）
  
這些選項會影響您的伺服器選項。您可能想要將工作負載分散到不同的伺服器，或為了簡單起見而將工作負載保留在一部伺服器上。如需如何部署伺服器的逐步指引，請參閱[設定基礎架構](/docs/infrastructure/sap-netweaver/sap-setting-up-infrastructure.html#set_up_infrastructure)。

## 儲存空間配置
{: #storage_config}

「表 1」是一個儲存空間配置範例，它是一個 256 GB 伺服器，具有 50,000 [SAPS](docs/infrastructure/sap-netweaver/sap-size-server.html)，對於具有 SAP 的中央系統，它有 1.5 TB 及 6,000 IOPS，並使用具有外部 [{{site.data.keyword.cloud_notm}}{{site.data.keyword.blockstorageshort}}](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage)或 [{{site.data.keyword.cloud_notm}}{{site.data.keyword.filestorage_short}}](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage) (4 IOPS/GB) 的 {{site.data.keyword.Db2_on_Cloud_long}} 資料庫）。IOPS 的計算方式如下

  * 6,000 IOPS/1,500 GG = 4 IOPS/GB，為外部儲存空間所需。已假設有 3,000 GB 來進行 2 IOPS/GB（中間效能）的備份。
  
表 1. 根據 IOPS 計算的儲存空間佈置範例

| 檔案系統    | 磁區數目     | 儲存空間類型 | IOPS/GB | GB | # IOPS |
| --- | --- | --- | --- | --- | --- |
| / | 1 | 內部     | N/A | 150 GB | N/A |
| /boot | 1 | 內部     | N/A | 0.25 GB | N/A |
| swap | 1 | 內部     | N/A | 256 GB | N/A |
| /db2（包括日誌）      | 1 | 內部     | N/A | 250 GB | N/A |
| sapdata | 1 | 外部     | 4 IOPS/GB | 1,500 GB | 6,000 IOPS |
| 備份/日誌及備份       | 1 | 外部     | 2 IOPS/GB | 3,000 GB | 6,000 IOPS |

## 高可用性配置
{: #ha_config}

{{site.data.keyword.cloud_notm}} 環境不支援任何預先配置的高可用性 (HA) 情境。不過，您可以根據所選作業系統的 HA 延伸來配置 HA 情境。您可以把所需的硬體及所需的軟體元件新增至您的架構中，來新增 HA 延伸。如果您需要其他軟體授權，請存取不同的軟體儲存庫，或聯絡 [{{site.data.keyword.cloud_notm}} 支援中心](https://console.bluemix.net/docs/get-support/howtogetsupport.html#getting-customer-support)，以協助您設定任何其他需求。

此資訊不僅適用於 SAP NetWeaver 的 HA 軟體，也適用於您選擇的關聯式資料庫管理系統 (RDBMS) 的 HA 軟體。這包括用於 RDBMS 的高可用性及災難回復機制，例如抄寫。設定程序不同於內部部署環境中的任何設定程序，且需要相同的軟硬體配置步驟。

## 後續步驟

現在，您已準備好開始佈建您的 {{site.data.keyword.baremetal_short}}。關於後續步驟，請參閱[佈建 SAP NetWeaver 環境](/docs/infrastructure/sap-netweaver/sap-provision-environment.html)。
  
  


