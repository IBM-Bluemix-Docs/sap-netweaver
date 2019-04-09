---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-28"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, high availability, highly available, HA, disaster recovery, DR, Microsft Windows Server Failover Clustering, WFSC, bring your own license, BYOL, single point of failure, SPOF, Link Aggregation Control Protocol, LACP, VLANs, SAP Certified, database, Linux Pacemaker

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# Suporte de alta disponibilidade do IBM Cloud
{: #ha}

A Infraestrutura como serviço (IaaS) do {{site.data.keyword.cloud}} oferece um ambiente de cálculo robusto com uma implementação de sistema operacional opcional (S.O.) no topo que suporta soluções de alta disponibilidade (HA). A solução é baseada na versão suportada do S.O., que é discutida na [Nota do SAP 2414097![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}. A solução de alta disponibilidade é restrita às licenças de S.O. solicitadas que vêm com a sua implementação ou licenças de terceiros, tais como Bring Your Own License (BYOL). Certifique-se de discutir os detalhes da alta disponibilidade com o Suporte do {{site.data.keyword.cloud_notm}} antes de sua implementação.

Os sistemas operacionais suportados e implementados pelo {{site.data.keyword.cloud_notm}} para SAP são
* O Linux [Red Hat Enterprise Linux (RHEL) ou SUSE Enterprise Linux Server (SLES)] suporta as soluções de alta disponibilidade SAP NetWeaver e SAP HANA. Existem restrições secundárias no ambiente do {{site.data.keyword.cloud_notm}}, que são discutidas em [Visão geral das configurações de alta disponibilidade do SAP NetWeaver](#overview-configs).
* O Microsoft Windows suporta somente a solução de alta disponibilidade do SAP NetWeaver (devido a restrições do banco de dados SAP HANA).

## Visão geral das configurações de alta disponibilidade do SAP NetWeaver
{: #overview-configs}

Existem vários documentos que fornecem ajuda detalhada no planejamento e na instalação de um ambiente de alta disponibilidade para serviços SAP. Os documentos incluem informações sobre failover, replicação, ampliação e recuperação de desastres (DR). Referências a determinados documentos são fornecidas quando apropriado.

Todos os sistemas operacionais e distribuições suportados pelo {{site.data.keyword.cloud_notm}} para uma implementação SAP (Windows, Linux RHEL e SLES) são fornecidos com software de alta disponibilidade e extensões específicas. A seguir estão os sistemas operacionais e as distribuições suportados.

* [Novas melhorias de cluster de failover no Windows Server 2012 e seus benefícios para alta disponibilidade do SAP NetWeaver![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://blogs.sap.com/2013/10/16/new-failover-clustering-improvements-in-windows-server-2012-and-its-benefits-for-sap-netweaver-high-availability/){: new_window} fornecem uma descrição baseada no Microsoft Windows Server Failover Clustering (WFSC) no S.O. Windows com SAP NetWeaver.

* Há duas referências para orientação sobre a implementação do SAP NetWeaver em um ambiente de alta disponibilidade baseado no Linux com o Linux Pacemaker:
  * Guia de Configuração do SUSE SAP NetWeaver High Availability Cluster 7.40
  * Implementando servidores baseados no SAP NetWeaver altamente disponíveis usando o complemento de alta disponibilidade do Red Hat Enterprise Linux com o Pacemaker

* [Construindo alta disponibilidade para SAP NetWeaver e SAP HANA no Linux![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://support.sap.com/content/dam/SAAP/SAP_Activate/AGS_70.pdf){: new_window} é um documento de melhores práticas SAP e fornece uma descrição técnica detalhada com um forte foco no SAP HANA.

* [Alta disponibilidade e continuidade de negócios do SAP NetWeaver em ambientes virtuais com VMware e Hyper-V no Microsoft Windows![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.sap.com/documents/2015/07/508b62bc-5b7c-0010-82c7-eda71af511fa.html){: new_window} abrange os aspectos de virtualização se você estiver planejando implementar a alta disponibilidade em servidores virtualizados.

Para obter mais produtos de alta disponibilidade certificados pelos parceiros SAP para cenários de alta disponibilidade, veja [Informações do parceiro de alta disponibilidade![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://wiki.scn.sap.com/wiki/display/SI/High+Availability+Partner+Information){: new_window}.
Para bancos de dados não SAP HANA, mais informações sobre as configurações de failover de alta disponibilidade e de DR estão disponíveis em sua documentação do banco de dados.

Observe que o acesso compartilhado ao armazenamento Network File System (NFS)/Common Internet File System (CIFS) ou o acesso compartilhado ao armazenamento de número exclusivo lógico (LUNS) baseado em iSCSI geralmente é requerido para suportar failover do sistema. O armazenamento local, combinado com um método de replicação, geralmente é requerido para suportar uma configuração semelhante a DR. Assim como com instalações no local, verifique os requisitos de desempenho e latência do produto de banco de dados ao planejar sua implementação.

## Orientação extra
{: #extra-guide}

[Armazenamento baseado em quorum](#quorum) e [Considerações de rede](#network) fornecem orientação que você precisa considerar durante a implementação. Além das considerações descritas nessas seções, a instalação do SAP NetWeaver e de seu sistema de banco de dados em um ambiente de alta disponibilidade não difere de outras instalações no local.

### Armazenamento baseado em quorum
{: #quorum}

Devido às restrições de segurança no ambiente do {{site.data.keyword.cloud_notm}} IBM Cloud, o acesso baseado em rede a dispositivos de gerenciamento remoto por meio da Intelligent Platform Management Interface (IPMI) não está disponível. Os ambientes de cluster geralmente usam componentes baseados em IPMI para o “fencing de nós de cluster” para sempre assegurar um quorum. Na ausência de um dispositivo ativado por IPMI, os dispositivos de armazenamento compartilhados são usados. Em um ambiente do {{site.data.keyword.cloud_notm}}, os dispositivos de armazenamento compartilhados são instalados implementando uma LUN iSCSI em seus servidores como um dispositivo de quorum. Por exemplo, um File Share Witness (FSW) em um Microsoft Cluster e para storage-based death (SDB) para o Stonith do Linux Pacemaker.
* Clique [aqui ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://linux-ha.org/wiki/Cluster_Concepts){: new_window} para obter mais informações sobre os Conceitos de cluster de alta disponibilidade do Linux.
* Clique [aqui ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://docs.microsoft.com/en-us/windows-server/failover-clustering/manage-cluster-quorum){: new_window} para obter mais informações sobre a configuração e o gerenciamento de servidores de quorum para o Windows Server 2012 e Windows Server 2012 R2.

O {{site.data.keyword.cloud_notm}} Storage tem recursos de alta disponibilidade integrados, portanto, um único LUN iSCSI compartilhado não introduzirá um Single Point Of Failure (SPOF) porque seu layout de rede é redundante. No entanto, as especificações de seu produto de cluster podem requerer vários dispositivos de quorum.

### Considerações sobre a Rede
{: #network}

Uma instalação baseada no {{site.data.keyword.cloud_notm}} é fornecida com uma das configurações de rede a seguir:
* Rede privada
* Rede Pública
* Redes públicas e privadas
* Duas redes privadas (sob demanda especial)

Como instalações no local, adaptadores de rede extras podem ser solicitados, dependendo das restrições físicas do hardware. A restrição é a mesma para instalações no local. A solicitação de adaptadores de rede redundantes durante as implementações de hardware ajuda a evitar SPOF através de sua topologia de rede. Adaptadores redundantes são instalados em uma configuração de failover com Link Aggregation Control Protocol (LACP). Para Linux, a configuração usa interfaces de ligação e os adaptadores de equipes são usados para Microsoft Windows. A infraestrutura do comutador {{site.data.keyword.cloud_notm}} à qual esses adaptadores estão conectados é redundante, portanto, nenhum novo SPOF é introduzido. A infraestrutura redundante pode ser usada pelas VLANs solicitadas.

Dependendo dos requisitos de rede, como cenários de replicação em uma configuração de DR, deve-se verificar a localização dos dispositivos conectados e quaisquer novos requisitos de rede específicos para o produto em questão. Em alguns casos, a replicação baseada em armazenamento de captura instantânea do {{site.data.keyword.cloud_notm}} pode atender aos seus requisitos. Verifique com o Suporte {{site.data.keyword.cloud_notm}} para determinar qual solução funciona melhor para suas necessidades de processo de negócios.
