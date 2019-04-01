---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.blockstorageshort}}, {{site.data.keyword.filestorage_full_notm}}, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.baremetal_short}}

subcollection: sap-netweaver

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

Sie können die Schritte unter [{{site.data.keyword.blockstorageshort}} bereitstellen und verwalten](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted#GettingStarted) oder [{{site.data.keyword.filestorage_full_notm}} bereitstellen und verwalten](/docs/infrastructure/FileStorage?topic=FileStorage-orderingConsole#orderingConsole) ausführen, um Ihre Speicherlösung für Sicherung und Wiederherstellung zu bestellen. Dabei können Sie entscheiden, welchen Speichertyp Sie verwenden möchten und wie Sie ihn bestellen und auf dem Server bereitstellen.

In den *Kurzübersichten zu SAP NetWeaver (für Microsoft Windows* bzw. *für Red Hat Enterprise Linux*) finden Sie umfassende Informationen zur Serverkonfiguration und -bereitstellung, einschließlich auf einer Beispielkonfiguration für Linux und Windows basierende Konfigurationsschritte für {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}} und iSCSI.

Für VMware ESXi kann der {{site.data.keyword.cloud_notm}}-Speichertyp als Datenspeicher genutzt werden; in diesem Fall wird er ESXi als iSCSI-Gerät zugeordnet. Die Schritte zum Zuordnen von iSCSI-Geräten zu ESXi finden Sie unter [iSCSI an VMware ESXi anhängen](/docs/infrastructure/vmware?topic=VMware-mounting-iscsi-vmware-esxi#mounting-iscsi-vmware-esxi).

## Nächste Schritte

  [2. Umgebung sichern](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. Gastbetriebssystem auf dem ESX-Hypervisor installieren (optional)](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. SAP-Software und -Anwendungen herunterladen und installieren](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
