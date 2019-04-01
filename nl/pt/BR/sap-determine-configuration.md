---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, RDBMS, SAP Application Performance Standards, SAPS, SAP Certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 5. Determinando sua configuração
{: #determine_configuration}

Com um sistema SAP NetWeaver, você tem duas opções de implementação:
  * Sistema central, que é uma instalação em um único host (duas camadas)
  * Sistema distribuído, que é uma instalação de múltiplos hosts (três camadas)

As opções influenciam a escolha do servidor. Talvez você queira distribuir sua carga de trabalho por servidores diferentes ou manter a carga de trabalho em um servidor para simplificar. Veja [Configurando sua infraestrutura](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-set_up_infrastructure#set_up_infrastructure) para obter orientação passo a passo sobre como implementar seu servidor.

## Configuração de armazenamento
{: #storage_config}

A Tabela 1 é uma configuração de armazenamento de amostra para um servidor 256 GB com 50 mil [SAPS](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server), 1,5 TB a 6.000 IOPS para um sistema central com SAP, usando um banco de dados {{site.data.keyword.Db2_on_Cloud_long}} com[{{site.data.keyword.cloud_notm}} {{site.data.keyword.blockstorageshort}}](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted#GettingStarted) ou [{{site.data.keyword.cloud_notm}} {{site.data.keyword.filestorage_short}}](/docs/infrastructure/FileStorage?topic=FileStorage-GettingStarted#GettingStarted) externo (4 IOPS/GB). O cálculo para o IOPS é

  * 6.000 IOPS/1.500 GG = 4 IOPS/GB necessários para armazenamento externo. Há uma suposição de 3.000 GB para backup em 2 IOPS/GB (desempenho médio).

Tabela 1. Layout de armazenamento de amostra com base no cálculo de IOPS

| Sistema de arquivos | Nº de volumes | Tipo de armazenamento | IOPS/GB | GB | Nº de IOPS |
| --- | --- | --- | --- | --- | --- |
| `/` | 1 | Interno | N/A | 150 GB | N/A |
| `/boot` | 1 | Interno | N/A | 0,25 GB | N/A |
| `swap` | 1 | Interno | N/A | 256 GB | N/A |
| `/db2` (incluindo logs) | 1 | Interno | N/A | 250 GB | N/A |
| `sapdata` | 1 | Externo | 4 IOPS/GB | 1.500 GB | 6.000 IOPS |
| `backup/log e backup` | 1 | Externo | 2 IOPS/GB | 3.000 GB | 6.000 IOPS |

## Configuração de alta disponibilidade
{: #ha_config}

O ambiente do {{site.data.keyword.cloud_notm}} não suporta nenhum cenário de alta disponibilidade (HA) pré-configurado. No entanto, é possível configurar cenários de HA com base na extensão de HA para o sistema operacional escolhido. Inclua a extensão HA incluindo o hardware necessário e os componentes de software necessários em suas paisagens. Se você precisar de licenças de software
adicionais, acesse os repositórios de software diferentes, ou ambos, entre em contato com o [Suporte {{site.data.keyword.cloud_notm}}](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) para
ajudá-lo a configurar quaisquer requisitos adicionais.

Essas informações não se aplicam apenas ao software HA para SAP NetWeaver, mas também ao software HA para o sistema de gerenciamento de banco de dados relacional (RDBMS) escolhido. Isso inclui os mecanismos de alta disponibilidade e recuperação de desastre para seu RDBMS, por exemplo, replicação. Os procedimentos de configuração não diferem de nenhum procedimento de configuração em um ambiente local e requerem as mesmas etapas de configuração de hardware e software.

## Próximas etapas

Agora você está pronto para começar o Fornecimento dos {{site.data.keyword.baremetal_short}}. Veja [Provisionando o ambiente do SAP NetWeaver](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment) para conhecer as próximas etapas.
