---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-18"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.baremetal_short}}, ABAP, application server, SAP Product Availability Matrix, PAM, SAP Certified, SAP Content Server, SAP liveCache

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:note: .note}
{:faq: .faq}


# Sobre a infraestrutura do IBM Cloud certificado para SAP
{: #about_ibmcloud_for_sap}

A IBM e a SAP têm se unido, formado parcerias e colaborado em áreas que incluem hardware, software, nuvem, serviços e financiamento há mais de 45 anos. A primeira colaboração foi em 1972 e tem continuado a crescer com centenas de clientes SAP que usam o {{site.data.keyword.cloud}} como sua solução de infraestrutura como serviço (IaaS). A {{site.data.keyword.IBM_notm}} continua a otimizar seus produtos de infraestrutura em nuvem para incluir suporte para a plataforma computacional SAP NetWeaver.

É por causa desse relacionamento e de outros recursos do {{site.data.keyword.cloud_notm}} que a {{site.data.keyword.IBM_notm}} foi selecionada como um dos principais provedores estratégicos da SAP de serviços de infraestrutura em nuvem para seus aplicativos críticos aos negócios. O suporte para o conjunto de produtos do SAP NetWeaver está disponível por meio do {{site.data.keyword.cloud_notm}} altamente escalável, aberto e de segurança avançada. Com essa parceria, os aplicativos baseados no SAP NetWeaver puderam ser expandidos para os principais mercados, e isso só foi possível devido aos mais de 60 data centers da {{site.data.keyword.IBM_notm}} no mundo todo.

A oferta apresenta o {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} com oito opções de memória:
  * Soquete único de 32 GB
  * Soquete único de 64 GB
  * Soquete dual de 128 GB
  * Soquete dual de 256 GB
  * Soquete dual de 512 GB
  * Soquete dual de 192 GB
  * Soquete dual de 384 GB
  * Soquete dual 768 GB

As oito opções são certificadas para SAP NetWeaver e podem fornecer uma plataforma de nuvem corporativa global escalável, rica em segurança e aberta para implementar rapidamente aplicativos SAP.

É possível usar seus servidores para ambientes de produção, não produção ou prova de conceito (POC). Todos os produtos baseados em ABAP do SAP NetWeaver Application Server e produtos baseados em Java do SAP NetWeaver Application Server são suportados nos {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}. Para todos os outros componentes de software,
produtos SAP baseados em NetWeaver não SAP ou produtos de terceiros, entre em contato com o [Portal SAP ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://support.sap.com/home.html){: new_window} se os produtos forem suportados nas ofertas IaaS.

## Modelo de oferta {{site.data.keyword.cloud_notm}} for SAP NetWeaver
{: #offer_model}

A oferta {{site.data.keyword.cloud_notm}} for SAP Applications é ideal para praticamente todos os cenários suportados de caso de uso do SAP NetWeaver nos {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} na rede do {{site.data.keyword.cloud_notm}}.

A oferta consiste nos servidores, nos sistemas operacionais (S.O.) e nos bancos de dados a seguir:
  * O {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} em oito tamanhos e o software que acompanha cada servidor.
      * 4 núcleos com 32 GB de RAM
      * 4 núcleos com 64 GB de RAM
      * 24 núcleos com 128 GB de RAM
      * 24 núcleos com 256 GB de RAM
      * 28 núcleos com 512 GB de RAM
      * 36 núcleos com 192 GB de RAM
      * 36 núcleos com 384 GB de RAM
      * 36 núcleos com 768 GB de RAM

  * Sistema operacional ou hypervisor
      * VMware vSphere ESXi 6.0 ou 6.5 em seu servidor
      * O S.O. Red Hat Enterprise Linux (RHEL) for SAP Business Applications 6.X [O SAP Business Warehouse (SAP BW) é suportado em produção nos {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}]
      * SUSE Linux Enterprise Server (veja a [Nota SAP 2414097 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} para obter detalhes da versão)
      * Microsoft Windows Server (veja a [Nota SAP 2414097 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} para obter detalhes da versão)

  * Os bancos de dados oferecidos são
      * Microsoft SQL Server for Windows (veja a [Nota SAP 2414097 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} para obter detalhes da versão)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Linux (veja a [Nota SAP 101809 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/101809){: new_window}: versões e níveis de fix pack suportados)
      * {{site.data.keyword.Db2_on_Cloud_long_notm}} for Windows (veja [Nota SAP 101809-DB6 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/101809){: new_window}: versões e níveis de fix pack suportados)
      * SAP MaxDB (veja a [Nota SAP 2414097 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} para obter detalhes da versão)
      * SAP ASE 16.0 (veja a [Nota SAP 2414097 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} para obter detalhes)
      * SAP HANA

Os {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} implementados com o VMware ESXi podem executar as versões listadas do RHEL e do Windows, os bancos de dados referenciados e os produtos de software baseados no SAP NetWeaver. Os servidores podem executar outros sistemas operacionais ou produtos baseados no NetWeaver não SAP, como SAP liveCache, SAP Content Server, SAP Business One no Microsoft SQL e SAP BusinessObjects conforme listado na [Nota SAP 2279688 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/2279688){: new_window}.

No caso de executar produtos SAP baseados no SAP NetWeaver em seu {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}}, deve-se também executar um dos sistemas operacionais e bancos de dados suportados.
{: note}

Veja [SAP HANA no {{site.data.keyword.cloud_notm}}](/docs/infrastructure/sap-hana?topic=sap-hana-getting-started#getting-started) para obter informações sobre como implementar o SAP HANA.

Consulte a [Matriz de disponibilidade do produto (PAM) SAP ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: new_window} para os requisitos específicos de bancos de dados, sistema operacional e SAP NetWeaver para o {{site.data.keyword.cloud_notm}}. Um ID de usuário do SAP S é necessário para acessar o SAP PAM.

## Rede do {{site.data.keyword.cloud_notm}}
{: #ibm_cloud_network}

O {{site.data.keyword.cloud_notm}} fornece mais de 2.000 GB de conectividade em uma área de cobertura global de mais de 60 data centers do {{site.data.keyword.cloud_notm}} e 28 pontos de presença (PoPs). O {{site.data.keyword.cloud_notm}} tem conexões de rede de 20 Gbps em seus locais. Essas conexões são fornecidas pelos principais provedores de rede global e incluem múltiplos links públicos de peering para dezenas de redes de acesso à Internet adicionais.

A rede tem três arquiteturas de rede gigabit distintas e redundantes - pública, privada e data center para data center - perfeitamente integradas à primeira topologia de rede dentro de uma rede do mercado. Esse design fornece acessibilidade, segurança e controle máximos para sua infraestrutura de TI. Veja
[A rede IBM Cloud ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/cloud-computing/bluemix/our-network){: new_window} para obter mais informações.
