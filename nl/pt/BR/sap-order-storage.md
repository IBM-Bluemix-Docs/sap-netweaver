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

# 1. Pedindo armazenamento
{: #order_storage}

{{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}} e Network Attached Storage (NAS) são pedidos após a implementação dos {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}. 

## Pedindo armazenamento do {{site.data.keyword.cloud_notm}}
{: #ibm_storage}

É possível usar as etapas de [Provisionando e gerenciando o {{site.data.keyword.blockstorageshort}}](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) ou [Provisionando e gerenciando o {{site.data.keyword.filestorage_full_notm}}](https://console.bluemix.net/docs/infrastructure/FileStorage/provisioning-file-storage.html#provisioning-and-managing-ibm-file-storage-for-ibm-cloud) para pedir sua solução de armazenamento de backup e restauração. Você é guiado pelo processo de decisão de qual tipo de armazenamento usar, como pedir e como implementá-lo no servidor.

Os *Guias de consulta rápida do SAP NetWeaver (para Microsoft Windows* ou *para Red Hat Enterprise Linux*) levam por uma configuração e implementação completas do servidor, incluindo o {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}} e as etapas de configuração do iSCSI baseadas em uma implementação de amostra para Linux e Windows.

Para o VMware ESXi, o tipo de armazenamento do {{site.data.keyword.cloud_notm}} pode ser usado como armazenamentos de dados; nesse caso, ele é mapeado para o ESXi como um dispositivo iSCSI. Siga as etapas em [Montando o iSCSI VMware ESXi](https://console.bluemix.net/docs/infrastructure/vmware/mounting-iscsi-vmware-esxi.html#mounting-iscsi-vmware-esxi) para mapear dispositivos iSCSI para o ESXi.

## Pedindo o NAS
{: #order-nas}

O armazenamento NAS pode ser outra extensão valiosa do armazenamento local de seu servidor se você precisa de armazenamento para arquivos de log arquivados de seu banco de dados ou backups on-line e off-line frequentes. Visite [Pedindo armazenamento NAS/FTP](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#ordering-nas-ftp-storage) para pedir e configurar o NAS. Além disso, consulte [Montando o armazenamento NAS no Linux](https://console.bluemix.net/docs/infrastructure/network-attached-storage/mount-nas-storage-linux.html#mounting-nas-storage-in-linux) para ver como mapear o network file storage (NFS) para seu servidor Linux. [O armazenamento NAS também pode ser mapeado para o VMware ESXi como um armazenamento de dados por meio do NFS](https://console.bluemix.net/docs/infrastructure/network-attached-storage/connect-nas-storage-windows.html#connecting-to-nas-storage-in-windows).

## Próximas etapas

  [2. Protegendo seu ambiente](/docs/infrastructure/sap-netweaver/sap-secure-environment.html)

  [3. Instalando o S.O. guest no hypervisor do ESX (opcional)](/docs/infrastructure/sap-netweaver/sap-installing-guest-operating-system-VMware-deployments.html)

  [4. Fazendo download e instalando o software e aplicativos SAP](/docs/infrastructure/sap-netweaver/sap-installing-SAP-landscape.html)
  
  
