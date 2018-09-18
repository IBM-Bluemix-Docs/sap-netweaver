---



copyright:
  years: 2018
lastupdated: "2018-06-28"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# 1. Speicher bestellen
{: #order_storage}

{{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}} und Network Attached Storage (NAS) werden nach der Bereitstellung von {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} bestellt. 

## {{site.data.keyword.cloud_notm}}-Speicher bestellen
{: #ibm_storage}

Sie können die Schritte unter [{{site.data.keyword.blockstorageshort}} bereitstellen und verwalten](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) oder [{{site.data.keyword.filestorage_full_notm}} bereitstellen und verwalten](https://console.bluemix.net/docs/infrastructure/FileStorage/provisioning-file-storage.html#provisioning-and-managing-ibm-file-storage-for-ibm-cloud) ausführen, um Ihre Speicherlösung für Sicherung und Wiederherstellung zu bestellen. Dabei können Sie entscheiden, welchen Speichertyp Sie verwenden möchten und wie Sie ihn bestellen und auf dem Server bereitstellen.

In den *Kurzübersichten zu SAP NetWeaver (für Microsoft Windows* bzw. *für Red Hat Enterprise Linux*) finden Sie umfassende Informationen zur Serverkonfiguration und -bereitstellung, einschließlich auf einer Beispielkonfiguration für Linux und Windows basierende Konfigurationsschritte für {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}} und iSCSI.

Für VMware ESXi kann der {{site.data.keyword.cloud_notm}}-Speichertyp als Datenspeicher genutzt werden; in diesem Fall wird er ESXi als iSCSI-Gerät zugeordnet. Die Schritte zum Zuordnen von iSCSI-Geräten zu ESXi finden Sie unter [iSCSI an VMware ESXi anhängen](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi).

## NAS bestellen
{: #order-nas}

NAS-Speicher kann eine weitere wertvolle Erweiterung des lokalen Speichers für den Server sein, falls Sie Speicher für archivierte Protokolldateien der Datenbank benötigen oder häufige Online- und Offline-Backups durchführen. Unter [NAS-/FTP-Speicher bestellen](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#ordering-nas-ftp-storage) können Sie NAS bestellen und einrichten. Informationen darüber, wie Sie Ihrem Server Network File Storage (NFS) zuordnen, finden Sie unter [NAS-Speicher unter Linux anhängen](https://console.bluemix.net/docs/infrastructure/network-attached-storage/mount-nas-storage-linux.html#mounting-nas-storage-in-linux). [NAS-Speicher kann zudem VMware ESXi als Datenspeicher über NFS zugeordnet werden](https://console.bluemix.net/docs/infrastructure/network-attached-storage/connect-nas-storage-windows.html#connecting-to-nas-storage-in-windows).

## Nächste Schritte

  [2. Umgebung sichern](/docs/infrastructure/sap-netweaver/sap-secure-environment.html)

  [3. Gastbetriebssystem auf dem ESX-Hypervisor installieren (optional)](/docs/infrastructure/sap-netweaver/sap-installing-guest-operating-system-VMware-deployments.html)

  [4. SAP-Software und -Anwendungen herunterladen und installieren](/docs/infrastructure/sap-netweaver/sap-installing-SAP-landscape.html)
  
  
