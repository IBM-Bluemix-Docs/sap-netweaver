---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, SAP certified servers, SAP Certified, database,

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 入門指導教學
{: #getting-started}

{{site.data.keyword.IBM_notm}} 與 SAP 在硬體、軟體、雲端、服務，以及金融等多個領域分工合作已有 40 年。它們現在分工合作，在 {{site.data.keyword.baremetal_long}} 上執行 SAP NetWeaver 型的應用程式。此供應項目的特性為四個記憶體選項、單插槽 (32 GB) 及雙插槽（128 GB、256 GB 及 512 GB）。這些記憶體選項在全球超過 60 個的 {{site.data.keyword.cloud_notm}} 資料中心都有提供。
{: shortdesc}

此內容為您提供基礎架構佈建及安裝的建議，以便在 {{site.data.keyword.cloud_notm}} 上支援 SAP NetWeaver 型的 SAP 產品及訂閱。它並不取代任何 SAP NetWeaver 實作相關文件。其目的是協助您進行基礎架構規劃及佈建，以便您開始進行 SAP 安裝。SAP 安裝（包括資料庫安裝）與內部部署環境的安裝並沒有不同。會提供建議及準則，以協助您在 {{site.data.keyword.cloud_notm}} 環境中操作 SAP 系統。

表 1 包含的步驟可協助您快速建置 {{site.data.keyword.cloud_notm}} 基礎架構。
<table>
   <CAPTION>表 1. 快速入門步驟</CAPTION>
   <THEAD>
   <TR>
   <th>作業 </th>
   <th>詳細資料 </th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>1. 讀取與您的實作相關的 IBM Cloud 和 SAP 內容</td>
   <td>如果您的組織初次使用 IBM Cloud，請在規劃階段之前閱讀下列資訊。
   <li><a href="https://ibm.com/cloud-computing/">何謂 IBM Cloud</a></li>
   <li><a href="https://ibm.com/cloud/get-started">開始使用 IBM Cloud</a></li>
   <li><a href="https://help.sap.com/nw75#section2">SAP NetWeaver 7.5 安裝及升級資訊</a>：下載安裝手冊</li>

   下列 SAP 文件也可能對您有用：
   <li><a href="https://www.youtube.com/watch?v=4wICiRTP8u0/">如何建立 SAP S 使用者 ID</a>。請注意，只有超級管理者或具有必要授權的 S 使用者才會被容許建立 S 使用者 ID。</li>
   <li><a href="https://help.sap.com/netweaver">SAP NetWeaver 說明</a></li>
   <li><a href="https://support.sap.com">透過 SAP 支援中心入口網站提供的 SAP Notes</a>；需要 SAP S 使用者 ID</li>
   </td>
   <tr>
   <td>2. 註冊 IBM Cloud</td>
   <td>請參閱<a href="https://cloud.ibm.com/docs/account/adminpublic.html#signing-up-for-ibm-cloud">註冊 IBM Cloud</a> 來瞭解如何設定 IBM Cloud 帳戶。</td>
 <tr>
   <td>3. 存取 IBM Cloud 基礎架構客戶入口網站</td>
   <td><a href="https://control.softlayer.com">IBM Cloud 基礎架構客戶入口網站</a>是您所有基礎架構元件（運算、連線功能、儲存空間、網路及資料中心）的圖形閘道。您需要 <a href="https://console.bluemix.net/docs/customer-portal/getting-started.html#getting-started">IBMid 及密碼</a>才能存取客戶入口網站。</td>
   <tr>
   <td>4. 規劃系統架構</td>
   <td>請使用<a href="sap-netweaver?topic=sap-netweaver-planning-your-system-landscape#planning-your-system-landscape">規劃系統架構</a>中的資訊，來架構、調整大小及佈建 IBM Cloud 架構，以支援 SAP NetWeaver工作負載。</td>  
 <tr>
   <td>5. 佈建系統</td>
   <td>使用<a href="sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment">佈建 SAP NetWeaver 環境</a>中的步驟和資訊，來設定您的 IBM Cloud 基礎架構。您也可以使用「快速參照手冊」中的步驟。</td>
   <tr>
   <td>6. 安裝 SAP NetWeaver</td>
   <td>您將 SAP NetWeaver 安裝在 IBM Cloud 基礎架構上，就像伺服器為內部部署那樣。如需安裝 SAP NetWeaver 的相關資訊，請參閱<a href="sap-netweaver?topic=sap-netweaver-install_sap#install_sap">下載和安裝 SAP 軟體與應用程式</a>來取得詳細資訊。</td>
   </td>
   </tr>
   </TBODY>
   </table>
