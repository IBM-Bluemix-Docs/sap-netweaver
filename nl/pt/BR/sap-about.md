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


# Sobre o IBM Cloud for SAP Applications 
{: #about_ibmcloud_for_sap}

A IBM e a SAP têm se unido, formado parcerias e colaborado em áreas que incluem hardware, software, nuvem, serviços e financiamento há mais de 45 anos. A primeira colaboração foi em 1972 e tem continuado a crescer com centenas de clientes SAP que usam o {{site.data.keyword.cloud}} como sua solução de infraestrutura como serviço (IaaS). A {{site.data.keyword.IBM_notm}} continua a otimizar seus produtos de infraestrutura em nuvem para incluir suporte para a plataforma computacional SAP NetWeaver. 

É por causa desse relacionamento e de outros recursos do {{site.data.keyword.cloud_notm}} que a {{site.data.keyword.IBM_notm}} foi selecionada como um dos principais provedores estratégicos da SAP de serviços de infraestrutura em nuvem para seus aplicativos críticos aos negócios. O suporte para o conjunto de produtos do SAP NetWeaver está disponível por meio do {{site.data.keyword.cloud_notm}} altamente escalável, aberto e de segurança avançada. Com essa parceria, os aplicativos baseados no SAP NetWeaver puderam ser expandidos para os principais mercados, e isso só foi possível devido aos mais de 60 data centers da {{site.data.keyword.IBM_notm}} no mundo todo.

A oferta apresenta os {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} com quatro opções de memória:
  * Soquete único de 32 GB
  * Soquete dual de 128 GB
  * Soquete dual de 256 GB
  * Soquete dual de 512 GB

As quatro opções são certificadas para o SAP NetWeaver e podem fornecer uma plataforma de nuvem corporativa global escalável, rica em segurança, aberta para a rápida implementação de aplicativos SAP.

É possível usar seus servidores para ambientes de produção, não produção ou prova de conceito (PoC). Todos os produtos baseados em ABAP do SAP NetWeaver Application Server e produtos baseados em Java do SAP NetWeaver Application Server são suportados nos {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}. Para todos os outros componentes de software, produtos SAP não baseados no SAP NetWeaver ou produtos de terceiros, entre em contato com o [Suporte da SAP](https://support.sap.com/home.html) se os produtos forem suportados nas ofertas IaaS.

## Modelo de oferta {{site.data.keyword.cloud_notm}} for SAP NetWeaver
{: #offer_model}

A oferta {{site.data.keyword.cloud_notm}} for SAP Applications é ideal para praticamente todos os cenários suportados de caso de uso do SAP NetWeaver nos {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} na rede do {{site.data.keyword.cloud_notm}}.

A oferta consiste nos servidores, nos sistemas operacionais (S.O.) e nos bancos de dados a seguir:
  * {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} em quatro tamanhos e o software que vem com cada servidor.
      * 4 núcleos com 32 GB de RAM
      * 24 núcleos com 128 GB de RAM
      * 24 núcleos com 256 GB de RAM
      * 28 núcleos com 512 GB de RAM
      
  * Sistema operacional ou hypervisor
      * VMware vSphere ESXi 6.0 ou 6.5 em seu servidor
      * O S.O. Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X [O SAP Business Warehouse (SAP BW) é suportado em produção nos {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}]
      * Microsoft Windows Server (veja a [Nota SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) para obter detalhes da versão)
      
  * Os bancos de dados oferecidos são
      * Microsoft SQL Server for Windows (veja a [Nota SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) para obter detalhes da versão)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Linux (veja a [Nota SAP 101809](https://launchpad.support.sap.com/#/notes/101809): Versões suportadas e níveis de fix pack)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Windows (veja a [Nota SAP 101809-DB6](https://launchpad.support.sap.com/#/notes/101809): Versões suportadas e níveis de fix pack)
      
Os {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} implementados com o VMware ESXi podem executar as versões listadas do RHEL e do Windows, os bancos de dados referenciados e os produtos de software baseados no SAP NetWeaver. Os servidores não podem executar nenhum outro sistema operacional ou produtos SAP não baseados no SAP NetWeaver.

Veja [SAP HANA no {{site.data.keyword.cloud_notm}}](https://console.bluemix.net/doc/infrastructure/sap-hana/hana-index.html#getting-started) para obter informações sobre como implementar o SAP HANA. As futuras versões da oferta {{site.data.keyword.cloud_notm}} for SAP Applications incluem suporte para outros bancos de dados, alta disponibilidade e recuperação de desastre.

Consulte o [SAP Product Availability Matrix (PAM)](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630) para obter requisitos específicos de bancos de dados, do sistema operacional e do SAP NetWeaver para o {{site.data.keyword.cloud_notm}}. Um ID de usuário do SAP S é necessário para acessar o SAP PAM.

## Rede do {{site.data.keyword.cloud_notm}}
{: #ibm_cloud_network}

O {{site.data.keyword.cloud_notm}} fornece mais de 2.000 GB de conectividade em uma área de cobertura global de mais de 60 data centers do {{site.data.keyword.cloud_notm}} e 28 pontos de presença (PoPs). O {{site.data.keyword.cloud_notm}} tem conexões de rede de 20 Gbps em seus locais. Essas conexões são fornecidas pelos principais provedores de rede global e incluem múltiplos links públicos de peering para dezenas de redes de acesso à Internet adicionais.

A rede tem três arquiteturas de rede gigabit distintas e redundantes - pública, privada e data center para data center - perfeitamente integradas à primeira topologia de rede dentro de uma rede do mercado. Esse design fornece acessibilidade, segurança e controle máximos para sua infraestrutura de TI. Veja [A rede do IBM Cloud](https://www.ibm.com/cloud-computing/bluemix/our-network) para obter mais informações.
