---



copyright:
  years: 2017, 2018
lastupdated: "2018-03-19"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Perguntas mais frequentes: SAP no IBM Cloud
{: #faqs}

## Preciso do DB2 para executar o SAP NetWeaver no {{site.data.keyword.cloud_notm}}?

Verifique a [Nota SAP 2414097](https://launchpad.support.sap.com/#/notes/2414097) regularmente e também consulte o [SAP Product Availability Matrix](https://apps.support.sap.com/sap/support/pam). Observe o sistema operacional fornecido na Nota SAP, porque são necessários diferentes conjuntos de pacotes de serviço para seu banco de dados.

## Por que o {{site.data.keyword.Db2_on_Cloud_short}} foi escolhido para certificação para o {{site.data.keyword.cloud_notm}}?

Como o {{site.data.keyword.Db2_on_Cloud_long_notm}} é um produto {{site.data.keyword.IBM_notm}} e o {{site.data.keyword.cloud_notm}} faz parte da {{site.data.keyword.IBM_notm}}, ele foi escolhido para a nossa certificação.

## Posso dividir meu ambiente SAP distribuído entre data centers diferentes?

Para uma instalação distribuída da SAP, é melhor ter todos os nós no mesmo data center e segmento VLAN. Variações podem render latência e tempos limite, o que tornaria o sistema SAP não responsivo.

## Posso obter alta disponibilidade da SAP conforme definido pela arquitetura SAP?

A única arquitetura de alta disponibilidade suportada é o ajuste de escala de servidores de aplicativos. Atualmente, não há hardware ativado para suporte de alta disponibilidade.

## Posso fazer download do software de distribuição SAP diretamente do {{site.data.keyword.cloud_notm}}?

Atualmente, não estamos oferecendo um link direto com o [SAP Service Marketplace](https://websmp201.sap-ag.de/). Portanto, é necessário fazer download dos DVDs de distribuição da mesma forma que faz hoje para uma implementação no local.
