---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, data centers, {{site.data.keyword.baremetal_short}}, deployment, VLANs, SAP Certified, database

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Visão geral do SAP NetWeaver no IBM Cloud IaaS
Um ambiente de infraestrutura como serviço (IaaS) consiste em vários componentes: data center, cálculo, conectividade, armazenamento e rede.

## Datacenters

Com data centers na América do Sul e do Norte, Europa, Ásia e Austrália, é possível provisionar recursos em nuvem onde (e quando) forem necessários. Cada data center é conectado à rede privada global do {{site.data.keyword.cloud_notm}}, tornando as transferências de dados mais rápidas e mais eficientes em qualquer lugar no mundo.

Veja [Data Centers ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/cloud-computing/bluemix/data-centers){: new_window} para obter mais informações sobre os data centers {{site.data.keyword.cloud_notm}} e os pontos de presença (PoPs).

## Servidores bare metal

{{site.data.keyword.baremetal_long}} são servidores físicos com recursos de customização limitados. Os servidores são dedicados para seu uso ou do seu cliente e não são compartilhados em nenhuma parte, incluindo recursos do servidor, com outros clientes do {{site.data.keyword.cloud_notm}}. Esses servidores são gerenciados por você ou por seu cliente e são provisionados sem um hypervisor.

Como a customização é limitada em servidores bare metal, são obtidos tempos mais rápidos de fornecimento entre 1 e 4 horas. O fornecimento rápido é útil quando você está tentando colocar um app no mercado antes da competição.

É oferecida uma variedade de combinações de RAM e CPU, pois os servidores certificados pela SAP têm uma quantia pré-configurada de RAM e número de CPUs. A combinação *não pode* ser mudada durante o processo de solicitação ou por meio de um chamado de suporte depois que os servidores são implementados.

Se o seu projeto requerer uma camada de virtualização, a oferta SAP NetWeaver incluirá a opção para pedir {{site.data.keyword.baremetal_short}} que são implementados com o VMware ESXi. A instância ESX está sob seu controle total, já que é implementado em seu data center. O sistema é totalmente configurado em relação à rede (qualquer configuração adicional, como armazenamento, cabe a você). É altamente recomendável ter uma pessoa que conheça administração ESX na equipe para iniciar seu projeto com sucesso.

Veja [Sobre servidores bare metal](/docs/bare-metal?topic=bare-metal-about#about) para obter mais informações sobre servidores bare metal.

## Sistemas operacionais

É necessário consultar a [Nota SAP 2414097 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/2414097){: new window} para obter uma lista de sistemas operacionais (S.Os.) guest para implementar sistemas baseados no NetWeaver. Um ID de usuário do SAP S é necessário para acessar a Nota SAP. O licenciamento para o S.O. guest é de sua responsabilidade.

## Conectividade de rede

A conectividade da Rede privada virtual (VPN) com o {{site.data.keyword.cloud_notm}} Virtual Cloud Network é concedida automaticamente quando sua conta do {{site.data.keyword.cloud_notm}} é configurada. Por padrão, seu servidor tem um endereço IP público e privado. Se desejar que o servidor seja privado, será possível desativar a interface pública depois que o servidor for provisionado ou pedir que o servidor seja privado. Veja [Introdução à Rede privada virtual](/docs/infrastructure/iaas-vpn?topic=VPN-getting-started-with-virtual-private-networking-vpn-#getting-started-with-virtual-private-networking-vpn-) para obter mais informações sobre o {{site.data.keyword.cloud_notm}} VPN.

## Armazenamento
{: #storage}

O armazenamento local é fornecido com os {{site.data.keyword.baremetal_short}} e usa a LAN virtual (VLAN) de rede privada do {{site.data.keyword.cloud_notm}} para ajudar a fornecer segurança de nível corporativo sem obstrução do acesso de administrador. É ideal para aplicativos de armazenamento intensivo com altas necessidades de E/S, como um S.O., e banco de dados e software de aplicativo. O espaço em disco do servidor SAP NetWeaver depende de como o servidor está configurado. Entre em contato o [Suporte {{site.data.keyword.cloud_notm}}](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) para obter as opções de extensão se o armazenamento local no servidor for insuficiente para sua carga de trabalho.

Há dois tipos de armazenamento para o {{site.data.keyword.cloud_notm}} - de bloco e de arquivo - dos quais escolher para executar backups e restaurações para o SAP NetWeaver. Ambos os tipos usam operações de entrada/saída por segundo (IOPS), que são usadas para determinar as necessidades de armazenamento. Os IOPS são medidos com base no tamanho de bloco de 16 KB com uma combinação de leitura/gravação de 50/50. Para obter o IOPS máximo em um volume, recursos de rede adequados precisam estar em vigor. Outras considerações incluem o uso de rede privada fora do armazenamento e do lado do host e ajustes específicos do aplicativo (por exemplo, pilhas de IP e profundidades de fila). Veja [Introdução ao Block Storage](/docs/infrastructure/BlockStorage?topic=BlockStorage-GettingStarted#GettingStarted) e [Introdução ao File Storage](/docs/infrastructure/FileStorage?topic=FileStorage-GettingStarted#GettingStarted) para obter mais informações sobre camadas de armazenamento e desempenho.

## Implementação e gerenciamento

Os {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} são implementados por meio do portal do cliente de infraestrutura do {{site.data.keyword.cloud_notm}} ou da API depois de criar sua conta do cliente do {{site.data.keyword.cloud_notm}}. Os servidores podem ser gerenciados por meio do portal do cliente, da API ou da interface de linha de comandos (CLI). Mais informações podem ser localizadas em [Sobre servidores bare metal](/docs/bare-metal?topic=bare-metal-about#about).

## Versão

O [Suporte ao cliente do {{site.data.keyword.cloud_notm}}](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) manipula quaisquer perguntas e problemas de suporte que possam surgir usando vários pontos, incluindo bate-papo, telefone e suporte baseado em chamado. O Suporte ao cliente é oferecido gratuitamente a todos os clientes do {{site.data.keyword.cloud_notm}} e cobre a maioria dos chamados feitos todos os dias. Veja [Obtendo o Suporte ao cliente](/docs/get-support?topic=get-support-getting-customer-support#getting-customer-support) para obter mais informações.
