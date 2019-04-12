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

# 1. Pedindo armazenamento
{: #order_storage}

{{site.data.keyword.blockstoragefull}}, {{site.data.keyword.filestorage_full_notm}} e Network Attached Storage (NAS) são pedidos após a implementação dos {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}.

## Pedindo armazenamento do {{site.data.keyword.cloud_notm}}
{: #ibm_storage}

É possível usar as etapas de [Provisionando e gerenciando o {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-getting-started#getting-started) ou [Provisionando e gerenciando o {{site.data.keyword.filestorage_full_notm}}](/docs/infrastructure/FileStorage?topic=FileStorage-orderingConsole#orderingConsole) para pedir sua solução de armazenamento de backup e restauração. Você é guiado pelo processo de decisão de qual tipo de armazenamento usar, como pedir e como implementá-lo no servidor.

Os *Guias de consulta rápida do SAP NetWeaver (para Microsoft Windows* ou *para Red Hat Enterprise Linux*) levam por uma configuração e implementação completas do servidor, incluindo o {{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}} e as etapas de configuração do iSCSI baseadas em uma implementação de amostra para Linux e Windows.

Para o VMware ESXi, o tipo de armazenamento do {{site.data.keyword.cloud_notm}} pode ser usado como armazenamentos de dados; nesse caso, ele é mapeado para o ESXi como um dispositivo iSCSI. Siga as etapas em [Montando o iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mount-iscsi-esxi#mount-iscsi-esxi) para mapear dispositivos iSCSI para o ESXi.

## Próximas etapas

  [2. Protegendo seu ambiente](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-secure_environment#secure_environment)

  [3. Instalando o S.O. guest no hypervisor do ESX (opcional)](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_guest_os#install_guest_os)

  [4. Fazendo download e instalando o software e aplicativos SAP](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-install_sap#install_sap)
