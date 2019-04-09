---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, network connectivity, VLANs, hybrid, STMS, SAProuter, SAP Solution Manager, SAP certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Itens a serem considerados ao planejar a paisagem da SAP
{: #considerations}

Os sistemas SAP em uma paisagem têm requisitos específicos para conectividade, seja entre si ou com sistemas externos. Também será necessário considerar armazenamento externo para sua paisagem e o que fazer se você decidir implementar o VMware no servidor.

## Conectividade de rede
{: #network_connectivity}

A [rede {{site.data.keyword.cloud_notm}}](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-ibm_cloud_network#ibm_cloud_network) forneceu uma visão geral da abordagem do {{site.data.keyword.cloud}} para conectividade de rede. Problemas com a conectividade de rede poderão causar atrasos significativos para seu projeto se você não planejar adequadamente, independentemente de como planejar usar o sistema.

Em geral, você tem duas opções de interface para seus servidores {{site.data.keyword.cloud_notm}} provisionados pelo IaaS - a primeira é uma interface externa com um IP público. A segunda é uma interface interna fornecida com um "IP privado" em conformidade com a Solicitação de Comentários (RFC) 1918. Também é possível escolher uma única interface interna com um "IP privado". Ambas as opções podem se tornar redundantes por meio de uma "interface de ligação" Linux ou por meio da Equipe de Placa da interface de rede Windows (NIC) e podem ser disponibilizadas em uma velocidade de 100 Mb/s, 1 Gb/s e 10 Gb/s.

Dependendo do seu caso de uso, um IP público pode ser aceitável para paisagens de prova de conceito (PoC) porque o IP externo pode ser mais fácil de usar. Existe um risco de segurança em potencial, embora haja um firewall básico instalado e pré-configurado. Se desejar usar uma interface pública, certifique-se de escolher um valor suficientemente alto para **Largura de banda pública** quando pedir seu servidor. Esse valor determina a quantia total de dados que podem ser transferidos por meio da interface durante um período de um mês. Embora a comunicação de rede normal, interface gráfica com o usuário (GUI) SAP ou tráfego de chamada de função remota (RFC) da SAP, possa somar apenas alguns megabytes por dia, os uploads de dados em massa podem facilmente exceder 1.000 GB por mês. Você precisará saber a quantia de dados transferidos pelo menos pela ordem de magnitude ou alternar para a segunda opção.

A segunda opção acessa o {{site.data.keyword.cloud_notm}} Virtual Private Network (VPN) por meio do portal do cliente da infraestrutura do {{site.data.keyword.cloud_notm}} ou implementa um dispositivo de segurança na paisagem. Os dispositivos de segurança são oferecidos para firewalls, conversão de endereço de rede, acesso VPN e outras funções de rede. Além disso, esses dispositivos de segurança podem fornecer uma largura de banda maior, que ajuda na transferência de grandes quantias de dados para um data center do {{site.data.keyword.cloud_notm}}. É aconselhável que o seu departamento de rede fale com o [Suporte {{site.data.keyword.cloud_notm}}](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) após o layout de sua paisagem e a conectividade necessária na camada de aplicativo SAP serem determinados.

### VLANs
{: #vlans}

Se desejar separar diferentes tipos de tráfego de rede em sua paisagem, será possível pedir mais LANs virtuais (VLANs). Lembre-se de que as VLANs adicionais apenas levam à segregação de tráfego, não ao aumento de desempenho. A segregação de tráfego precisa ser considerada com implementações elaboradas baseadas no VMware, em que diferentes tipos de tráfego de rede podem precisar ser mais estritamente separados por motivos de segurança.

Para os casos de uso a seguir, talvez você queira ter certeza de que todos os servidores estejam na mesma VLAN durante a implementação:
  *	Múltiplos servidores trocando dados, como uma configuração de três camadas da SAP - banco de dados e instâncias do aplicativo SAP em servidores diferentes
  *	Múltiplos sistemas que trocam grandes quantias de dados

Para uma implementação SAP com armazenamento local, mesmo para configurações de três camadas, redes baseadas em 1 Gb são suficientes. Mais fatores podem ser considerados; veja [Armazenamento externo](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations#external_storage) para obter mais informações sobre suas opções de armazenamento de rede.

### Configurações híbridas
{: #hybrid}

A oferta {{site.data.keyword.cloud_notm}} for SAP Applications pode ser considerada como um data center externo, especialmente se você está pensando em implementar uma paisagem híbrida com alguns sistemas SAP em um data center do {{site.data.keyword.cloud_notm}} e outros sistemas no local. Alguns itens de configuração específicos que precisam ser considerados como parte da fase de planejamento de seu projeto com uma configuração híbrida:

  *	[SAP Transport Management System (STMS) ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.sap.com/products/transportation-logistics.html){: new_window}. Configure-o com base em Grupos de transporte para evitar o compartilhamento de arquivos nos data centers.
  *	[SAProuter ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://support.sap.com/en/tools/connectivity-tools/saprouter.html){: new_window}. Fornece acesso ao SAP On-line Service System (OSS). Use o SAProuter local, que já está disponível, para acessar o OSS. Esse SAProuter poderá ser usado por meio de hops adicionais do SAProuter se o roteamento baseado em IP não for permitido entre os sistemas baseados no {{site.data.keyword.cloud_notm}} e seu SAProuter local. Como alternativa, é possível considerar a configuração de outro SAProuter que se baseia em um servidor baseado no {{site.data.keyword.cloud_notm}} com um IP público e conectá-lo ao sistema SAP OSS por meio da Internet.
  *	[SAP Solution Manager ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://support.sap.com/en/solution-manager.html){: new_window}. O acesso ao SAP Solution Manager possui requisitos de conectividade diferentes entre um SAP Solution Manager e seus sistemas gerenciados, dependendo do cenário de uso. Esses cenários requerem um entendimento da conectividade de rede necessária.  

## Armazenamento externo
{: #external_storage}

O armazenamento local fornece o melhor desempenho para sua implementação de banco de dados. Além do armazenamento local, pode ser necessário mais armazenamento externo para executar backups ou o banco de dados dos sistemas SAP pode exceder a capacidade de armazenamento dos discos internos. Outro exemplo é que os requisitos de seu projeto podem exigir armazenamento externo, como para múltiplos servidores baseados no ESX, que desejam compartilhar máquinas virtuais (VMs). Para esses requisitos, é possível pedir armazenamento de bloco ou o Network Attached Storage (NAS), conforme descrito em [Armazenamento](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-storage#storage). Como o armazenamento extra de bloco e os dados do NAS são transferidos por meio dos mesmos adaptadores físicos de todo o outro tráfego de rede, o impacto precisa ser considerado. Os números de desempenho comparáveis aos números medidos nas referências de certificação podem ser meramente alcançáveis.

Recomenda-se escolher um data center baseado em 10 Gb para sua implementação caso você esteja planejando usar principalmente o armazenamento externo em vez do armazenamento local. Por exemplo, o armazenamento externo é usado para backup e para seu banco de dados e caso você esteja planejando colocar uma alta carga no sistema SAP. Se você estiver perto de sobrecarregar uma rede de 1 Gb com uma carga de E/S de 90 MB/s.

Outra recomendação é usar pelo menos 4 IOPS/GB se seu banco de dados reside principalmente no armazenamento externo. O armazenamento mais lento só deverá ser usado se o desempenho do banco de dados não for crítico para seu projeto ou para propósitos de backup.

Se você estiver planejando usar armazenamento externo como armazenamentos de dados para o VMware ESX, siga as diretrizes de decisão em [Armazenamento para usar com Sistemas VMware](/docs/infrastructure/vmware?topic=VMware-storage-to-use-with-vmware-systems#storage-to-use-with-vmware-systems) para determinar o tipo de armazenamento ideal para seu caso de uso.

## Implementações do servidor VMware ESXi
{: #vmware_server}

As implementações baseadas em VMware ESXi no {{site.data.keyword.cloud_notm}} são diferentes de outras implementações baseadas em nuvem. O {{site.data.keyword.cloud_notm}} não fornece VMs em execução a seus clientes; você assume o controle de seu ambiente e configura-o para atender às suas necessidades. Você recebe um servidor configurado ao pedir um servidor VMware ESX. Os links a seguir fornecem informações sobre armazenamento adicional e VMs guest em execução.

  *	[Armazenamento para usar com Sistemas VMware](/docs/infrastructure/vmware?topic=VMware-storage-to-use-with-vmware-systems#storage-to-use-with-vmware-systems) fornece orientação adicional sobre como integrar o armazenamento em um ambiente ESX.
  * [Montando o iSCSI VMware ESXi](/docs/infrastructure/vmware?topic=VMware-mounting-iscsi-vmware-esxi#mounting-iscsi-vmware-esxi) descreve as etapas para integrar o armazenamento baseado em iSCSI ao ESX.
  * [Criando uma máquina virtual VMware ESX](/docs/infrastructure/vmware?topic=VMware-creating-a-vmware-esx-virtual-machine#creating-a-vmware-esx-virtual-machine) fornece orientação durante o processo de implementação de sua primeira VM.

Tenha em mente que, para implementar o software baseado no SAP NetWeaver no S.O. guest, você
deve escolher o S.O. guest nos sistemas operacionais mencionados na [Nota SAP 2414097 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}.
