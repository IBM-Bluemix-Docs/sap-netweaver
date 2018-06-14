---



copyright:
  years: 2017, 2018
lastupdated: "2018-01-25"


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

Veja [Data centers](https://www.ibm.com/cloud-computing/bluemix/data-centers){: new_window} para obter mais informações sobre os data centers do {{site.data.keyword.cloud_notm}} e pontos de presença (PoPs).

## Servidores bare metal

{{site.data.keyword.baremetal_long}} são servidores físicos com recursos de customização limitados. Os servidores são dedicados para seu uso ou do seu cliente e não são compartilhados em nenhuma parte, incluindo recursos do servidor, com outros clientes do {{site.data.keyword.cloud_notm}}. Esses servidores são gerenciados por você ou por seu cliente e são provisionados sem um hypervisor.

Como a customização é limitada em servidores bare metal, são obtidos tempos mais rápidos de fornecimento entre 1 e 4 horas. O fornecimento rápido é útil quando você está tentando colocar um app no mercado antes da competição.

É oferecida uma variedade de combinações de RAM e CPU, pois os servidores certificados pela SAP têm uma quantia pré-configurada de RAM e número de CPUs. A combinação *não pode* ser mudada durante o processo de solicitação ou por meio de um chamado de suporte depois que os servidores são implementados.

Se o seu projeto requerer uma camada de virtualização, a oferta SAP NetWeaver incluirá a opção para pedir {{site.data.keyword.baremetal_short}} que são implementados com o VMware ESXi. A instância ESX está sob seu controle total, já que é implementado em seu data center. O sistema é totalmente configurado em relação à rede (qualquer configuração adicional, como armazenamento, cabe a você). É altamente recomendável ter uma pessoa que conheça administração ESX na equipe para iniciar seu projeto com sucesso.

Veja [Sobre servidores bare metal](https://console.bluemix.net/docs/bare-metal/index.html#about-bare-metal-servers) para obter mais informações sobre servidores bare metal. 

## Sistemas operacionais

É necessário consultar a [Nota SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097){: new window} para obter uma lista de sistemas operacionais (S.O.) guest para implementar sistemas baseados no SAP NetWeaver. Um ID de usuário do SAP S é necessário para acessar a Nota SAP. O licenciamento para o S.O. guest é de sua responsabilidade.

## Conectividade de rede

A conectividade da Rede privada virtual (VPN) com o {{site.data.keyword.cloud_notm}} Virtual Cloud Network é concedida automaticamente quando sua conta do {{site.data.keyword.cloud_notm}} é configurada. Por padrão, seu servidor tem um endereço IP público e privado. Se desejar que o servidor seja privado, será possível desativar a interface pública depois que o servidor for provisionado ou pedir que o servidor seja privado. Veja [Introdução à Rede privada virtual](https://console.bluemix.net/docs/infrastructure/iaas-vpn/getting-started.html#getting-started-with-virtual-private-networking-vpn-) para obter mais informações sobre o {{site.data.keyword.cloud_notm}} VPN.

## Armazenamento
{: #storage}

O armazenamento local é fornecido com os {{site.data.keyword.baremetal_short}} e usa a LAN virtual (VLAN) de rede privada do {{site.data.keyword.cloud_notm}} para ajudar a fornecer segurança de nível corporativo sem obstrução do acesso de administrador. É ideal para aplicativos de armazenamento intensivo com altas necessidades de E/S, como um S.O., e banco de dados e software de aplicativo. O espaço em disco do servidor SAP NetWeaver depende de como o servidor está configurado. Entre em contato com o [Suporte do {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/support/index.html#getting-customer-support) para obter as opções de extensão se o armazenamento local no servidor for insuficiente para sua carga de trabalho.

Há dois tipos de armazenamento para o {{site.data.keyword.cloud_notm}} - de bloco e de arquivo - dos quais escolher para executar backups e restaurações para o SAP NetWeaver. Ambos os tipos usam operações de entrada/saída por segundo (IOPS), que são usadas para determinar as necessidades de armazenamento. Os IOPS são medidos com base no tamanho de bloco de 16 KB com uma combinação de leitura/gravação de 50/50. Para obter o IOPS máximo em um volume, recursos de rede adequados precisam estar em vigor. Outras considerações incluem o uso de rede privada fora do armazenamento e do lado do host e ajustes específicos do aplicativo (por exemplo, pilhas de IP e profundidades de fila). Veja [Introdução ao armazenamento de bloco](https://console.bluemix.net/docs/infrastructure/BlockStorage/index.html#getting-started-with-block-storage) e [Introdução ao armazenamento de arquivo](https://console.bluemix.net/docs/infrastructure/FileStorage/index.html#getting-started-with-file-storage) para obter mais informações sobre camadas de armazenamento e desempenho.

O {{site.data.keyword.cloud_notm}} também oferecerá Network Attached Storage (NAS) se você estiver procurando uma solução de backup rápida e de baixo custo para seus dispositivos. O NAS é compatível com
  * S.O. Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X
  * Protocolo de Transferência de Arquivos (FTP) com Parallels Plesk Panel e cPanel@WHM
  * Microsoft Windows Server por meio dos procedimentos padrão do Windows usando o Protocolo Common Internet File System (CIFS)
  
O armazenamento NAS e FTP são faturados mensalmente e estão disponíveis em vários tamanhos de armazenamento. É possível interagir principalmente com seu armazenamento NAS e FTP dentro da linha de comandos ou do terminal com o S.O. ou por meio de interações apontar e clicar nos painéis do portal do cliente de infraestrutura do {{site.data.keyword.cloud_notm}}.

Mais informações sobre o NAS em um ambiente do {{site.data.keyword.cloud_notm}} podem ser localizadas em [Introdução ao NAS](https://console.bluemix.net/docs/infrastructure/network-attached-storage/index.html#getting-started-with-nas).

## Implementação e gerenciamento

Os {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} são implementados por meio do portal do cliente de infraestrutura do {{site.data.keyword.cloud_notm}} ou da API depois de criar sua conta do cliente do {{site.data.keyword.cloud_notm}}. Os servidores podem ser gerenciados por meio do portal do cliente, da API ou da interface de linha de comandos (CLI). Mais informações podem ser localizadas em [Sobre servidores bare metal](https://console.bluemix.net/docs/bare-metal/index.html#about-bare-metal-servers).

## Versão

O [Suporte ao cliente do {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/docs/support/index.html#getting-customer-support) manipula quaisquer perguntas e problemas de suporte que possam surgir usando vários canais, incluindo suporte via bate-papo, telefone e chamado. O Suporte ao cliente é oferecido gratuitamente a todos os clientes do {{site.data.keyword.cloud_notm}} e cobre a maioria dos chamados feitos todos os dias. Veja [Obtendo o Suporte ao cliente](https://console.bluemix.net./docs/support/index.html#getting-customer-support) para obter mais informações.
