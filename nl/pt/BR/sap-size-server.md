---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, SAP Application Performance Standard, SAPS, SAP Quick Sizer

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}


# 4. Dimensionando o servidor
{: #size_the_server}

Depois de decidir quais soluções SAP você planeja usar, sua próxima etapa será determinar o número de {{site.data.keyword.baremetal_long}} necessários para dar suporte à paisagem da SAP e assegurar que os servidores estejam dimensionados corretamente.
{: shortdesc}

## Entendendo a metodologia de dimensionamento da SAP
{: #size_method}

A metodologia de dimensionamento da SAP para aplicativos centrados no SAP NetWeaver baseia-se em referências da SAP, como informações da SAP e experiências reais do cliente. A unidade de carga de trabalho base da SAP é um SAP Application Performance Standard (SAPS). O SAPS é uma definição de rendimento criada pela equipe de planejamento de capacidade e teste de desempenho da SAP. Por exemplo, 100 SAPS são definidos como 2.000 itens de linha de pedido processados totalmente em negócios por hora na referência de aplicativo padrão SAP Sales and Distribution (SAP SD). Isso é equivalente a 2.400 transações SAP por hora com a solução SAP Enterprise Resource Planning (SAP ERP). A capacidade de processadores é medida durante o teste de referência padrão (SAP SD) certificado pela SAP. Para obter mais detalhes sobre o teste de referência certificado pela SAP, veja [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://lenovopress.com/redp5073.pdf){: new_window}. O teste avalia o processo quanto à sua capacidade de processar trabalho perto de 100% de carga da CPU com um tempo de resposta abaixo de 1 segundo.

## Usando o SAP Quick Sizer
{: #quicksizer}

O [SAP Quick Sizer ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://service.sap.com/quicksizer){: new_window} é uma ferramenta baseada na web e é fornecido pelo SAP para todos os parceiros e clientes. As informações de dimensionamento são inseridas diretamente na ferramenta, na qual ela dimensiona aplicativos baseados no SAP NetWeaver e aplicativos não baseados no SAP NetWeaver. Ela requer um ID de usuário do SAP S.

Ela calcula a carga de trabalho (em SAPS) e ajusta-a para permitir o uso adequado do processador. Portanto, se uma carga de trabalho de 4.800 transações de referência SAP SD por hora era necessária, a ferramenta calculará isso como 200 SAPS. Se uma carga de processador de destino de 33% for permitida, ajuste isso para localizar um processador capaz de 600 SAPS a 100% (=200 em 33%). Para obter mais detalhes sobre o cálculo de SAPS, veja [*SAP Business Suite on IBM X6 Systems Reference Architecture* ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://lenovopress.com/redp5073.pdf){: new_window}.

Embora o método de dimensionamento possa ser considerado cauteloso, considere o fato de que os números SAPS para seus servidores foram calculados com base em sistemas SAP altamente ajustados, executando apenas cargas de trabalho específicas do SAP SD. Dependendo do tipo de aplicativo SAP, qualquer configuração customizada ou codificação customizada em seu sistema, seus resultados podem variar. Além disso, os requisitos para seu projeto, como prova de conceito (PoC) ou sobre desempenho e tempo de resposta, podem ser diferentes.

## Escolhendo um servidor bare metal do {{site.data.keyword.cloud_notm}}
{: #choose_server}

Depois de ter determinado os aplicativos SAP e os números SAPS que foram calculados por meio do SAP Quick Sizer ou com base em sua paisagem atual, você está pronto para escolher um servidor nos modelos oferecidos. A Tabela 1 contém os números SAPS para os {{site.data.keyword.baremetal_short}} que foram certificados para o SAP NetWeaver. Veja [SAP Standard Application Benchmarks ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.sap.com/about/benchmark.html){: new_window} para obter os documentos de certificação.

Todos os tipos de servidores suportados listados na Tabela 1 correspondem àqueles que foram certificados pela SAP com o nome publicado e são verificados na [Nota SAP 2414097 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://launchpad.support.sap.com/#/notes/2414097){: new_window}; clique [aqui ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.sap.com/dmc/exp/2014-09-02-hana-hardware/enEN/power-systems.html){: new_window} para obter uma listagem completa. Observe que os nomes publicados estão sujeitos a mudanças.

Tabela 1. {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} certificados para o SAP NetWeaver

| Tipo de servidor | SAPS | RAM |
| --- | --- | --- |
| BI.S1.NW32 | 10980 | 32 GB |
| BI.S1.NW128 | 54130 | 128 GB |
| BI.S1.NW256 | 55020 | 256 GB |
| BI.S2.NW512 | 65520 | 512 GB |
| BI.S3.NW32 | 11970 | 32 GB |
| BI.S3.NW64 | 12750 | 64 GB |
| BI.S3.NW192 | 78850 | 192 GB |
| BI.S3.NW384 | 79430 | 384 GB |
| BI.S3.NW768 | 79630 | 768 GB |

## Migrando um sistema SAP existente
{: #migrating}

Se você estiver planejando migrar um sistema SAP existente de qualquer origem para o ambiente do {{site.data.keyword.cloud_notm}}, será possível determinar os números de SAPS por meio dos números de SAPS de seu ambiente atual. Use as informações sobre sua carga de trabalho atual (as CPUs e RAM usadas) e obtenha os SAPS equivalentes para sua CPU dos [resultados de referência do SAP SD![Ícone de link externo]](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.sap.com/about/benchmark.html){: new_window}.

## Próximas etapas

 [5. Determinando sua configuração](/docs/infrastructure/sap-netweaver?topic=sap-netweaver-determine_configuration#determine_configuration)
