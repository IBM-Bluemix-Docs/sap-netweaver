---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, SAP landscape, SAP Business Suite, SAP Business Warehouse, SAP BW

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:faq: .faq}

# Planejando a paisagem do sistema
{: #planning-your-system-landscape}

Uma *paisagem* SAP é um grupo de dois ou mais *sistemas* SAP que geralmente incluem desenvolvimento, qualidade e teste e produção. Um sistema SAP consiste em uma ou mais *instâncias da SAP*, que são um grupo de processos iniciados e interrompidos ao mesmo tempo. Para obter mais informações sobre as paisagens SAP, veja [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://lenovopress.com/redp5073.pdf){: new_window}.
{: shortdesc}

Há várias configurações possíveis de paisagem, como servidor (tamanho)/armazenamento (tamanho), para todas as soluções SAP no mercado. Essas soluções incluem produtos baseados no SAP NetWeaver, tais como [SAP Business Suite ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://open.sap.com/courses/suitehana1){: new_window}, SAP Business Warehouse e todos os complementos SAP específicos, que os servidores no {{site.data.keyword.cloud}} SAP-Certified Infrastructure suportam. Mais soluções a serem consideradas são quaisquer soluções SAP não baseadas no SAP NetWeaver e qualquer software de terceiros que possa ser integrado à SAP. Entre em contato com o [Suporte SAP ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://support.sap.com/en/index.html){: new_window} se você estiver planejando implementar software
baseado em NetWeaver não SAP ou de software de terceiros em sua paisagem do {{site.data.keyword.cloud}} IaaS.

Você deseja ser o mais detalhado possível ao determinar o tamanho do servidor com base nos aplicativos que planeja executar, potencial de crescimento e desempenho. Além disso, lembre-se dos requisitos de armazenamento e memória para seus aplicativos. Os sistemas SAP em uma paisagem têm requisitos específicos para conectividade, seja entre si ou com sistemas externos. Para obter mais informações, veja [Itens a serem considerados ao planejar a paisagem da SAP](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-considerations#considerations).

A Tabela 1 contém as etapas dentro do processo de planejamento. Use-a para ajudar a construir a paisagem de destino da SAP.

Tabela 1. Visão geral do processo de planejamento

| Etapa | Detalhes |
| --- | --- |
| 1 | [Obter as credenciais da SAP e do {{site.data.keyword.cloud_notm}} e criar contas](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-get_sap_ibm_credentials#get_sap_ibm_credentials) |
| 2 | [Revisar qualquer documentação relevante da SAP e do {{site.data.keyword.cloud_notm}}](/docs/infrastructure/sap-netweaver/sap-review-doc.html) |
| 3 | [Determine os aplicativos SAP NetWeaver](/docs/infrastructure/sap-netweaver/sap-determine-apps.html) |
| 4 | [Dimensionar o servidor](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-size_the_server#size_the_server) |
| 5 | [Determinar sua configuração](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration) |

## Próximas etapas

Selecione a etapa apropriada na Tabela 1 para começar a planejar a paisagem da SAP.
