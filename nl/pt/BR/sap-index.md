---

copyright:
  years: 2017, 2019
lastupdated: "2019-03-01"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, SAP certified servers, SAP Certified, database,

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Tutorial de Introdução
{: #getting-started}

{{site.data.keyword.IBM_notm}} e SAP continuam uma colaboração de 40 anos em várias áreas, incluindo hardware, software, nuvem, serviços e finanças. Elas estão agora colaborando para executar aplicativos baseados no SAP NetWeaver nos {{site.data.keyword.baremetal_long}}. A oferta apresenta quatro opções de memória, soquete único (32 GB) e soquetes duplos (128 GB, 256 GB e 512 GB). Essas opções de memória estão todas disponíveis nos mais de 60 data center {{site.data.keyword.cloud_notm}} em todo o mundo.
{: shortdesc}

Esse conteúdo fornece recomendações para o fornecimento e a instalação da infraestrutura para suportar produtos SAP baseados no SAP NetWeaver e assinatura no {{site.data.keyword.cloud_notm}}. Ele não substitui nenhuma documentação relacionada à implementação do SAP NetWeaver. Seu propósito é ajudá-lo com o planejamento e fornecimento de infraestrutura para que você possa começar a instalação da SAP. A instalação da SAP (incluindo a instalação do banco de dados) não varia das instalações para os ambientes locais. São fornecidas recomendações e diretrizes para ajudá-lo a operar o sistema SAP no ambiente do {{site.data.keyword.cloud_notm}}.

A Tabela 1 contém etapas para ajudá-lo a construir sua infraestrutura do {{site.data.keyword.cloud_notm}} rapidamente.
<table>
   <CAPTION>Tabela 1. Etapas de iniciação rápida</CAPTION>
   <THEAD>
   <TR>
   <th>Tarefas</th>
   <th>Detalhes</th>
   </TR>
   </THEAD>
   <TBODY>
   <tr>
   <td>1. Ler o conteúdo do IBM Cloud e da SAP relacionado à sua implementação</td>
   <td>Se a sua organização for nova para o IBM Cloud, leia as informações a seguir antes de sua fase de planejamento.
   <li><a href="https://ibm.com/cloud-computing/">O que é IBM Cloud?</a></li>
   <li><a href="https://ibm.com/cloud/get-started">Introdução ao IBM Cloud</a></li>
   <li><a href="https://help.sap.com/nw75#section2">Informações de instalação e upgrade do SAP NetWeaver 7.5</a>: faça download do guia de instalação</li>

   Talvez a documentação a seguir da SAP poderá ser útil:
   <li><a href="https://www.youtube.com/watch?v=4wICiRTP8u0/">Como criar um ID do usuário do SAP S</a>. Observe que somente superadministradores ou usuários S com a autorização necessária têm permissão para criar IDs de usuário S.</li>
   <li><a href="https://help.sap.com/netweaver">Ajuda do SAP NetWeaver</a></li>
   <li><a href="https://support.sap.com">Notas do SAP por meio do Portal de suporte SAP</a>; requer um ID do usuário do SAP S</li>
   </td>
   <tr>
   <td>2. Inscrever-se para o IBM Cloud</td>
   <td>Veja <a href="https://cloud.ibm.com/docs/account/adminpublic.html#signing-up-for-ibm-cloud">Inscrevendo-se para o IBM Cloud</a> para obter as etapas sobre como configurar sua conta do IBM Cloud.</td>
 <tr>
   <td>3. Acessar o portal do cliente da infraestrutura do IBM Cloud</td>
   <td>O <a href="https://control.softlayer.com">Portal do cliente da infraestrutura do IBM Cloud</a> é o gateway gráfico para todos os componentes de infraestrutura - cálculo, conectividade, armazenamento, rede e data centers. Você precisa de um <a href="https://console.bluemix.net/docs/customer-portal/getting-started.html#getting-started">IBMid e uma senha</a> para acessar o portal do cliente.</td>
   <tr>
   <td>4. Planejar a paisagem do sistema</td>
   <td>Use as informações em <a href="sap-netweaver?topic=sap-netweaver-planning-your-system-landscape#planning-your-system-landscape">Planejando a paisagem do sistema</a> para projetar, dimensionar e provisionar o ambiente do IBM Cloud para suportar a carga de trabalho do SAP NetWeaver.</td>  
 <tr>
   <td>5. Provisionar o sistema</td>
   <td>Use as etapas e as informações em <a href="sap-netweaver?topic=sap-netweaver-provision_environment#provision_environment">Provisionando o ambiente do SAP NetWeaver</a> para configurar a infraestrutura do IBM Cloud. Também é possível usar as etapas nos Guias de referência rápida.</td>
   <tr>
   <td>6. Instalar o SAP NetWeaver</td>
   <td>Instale o SAP NetWeaver em sua infraestrutura IBM Cloud da mesma forma que se os servidores estivessem no local. Para obter mais informações sobre como instalar o SAP NetWeaver, veja <a href="sap-netweaver?topic=sap-netweaver-install_sap#install_sap">Fazendo download e instalando software e aplicativos SAP</a> para obter mais informações.</td>
   </td>
   </tr>
   </TBODY>
   </table>
