---
title: Planejar o Painel de Qualidade da Chamada para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Resumo: Saiba o que considerar ao planejar o Painel de Qualidade da Chamada.'
ms.openlocfilehash: 6a1fc39dd26f6c4e9e455babcecb124888629179
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803171"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planejar o Painel de Qualidade da Chamada para o Skype for Business Server 
 
**Resumo:** Saiba mais sobre o que considerar ao planejar o Painel de Qualidade da Chamada.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Visão geral do Painel de Qualidade de Chamadas do Skype for Business Server

O Painel de Qualidade de Chamadas do Skype for Business Server (CQD) é uma camada de relatórios sobre o Banco de Dados de Qualidade da Experiência no Monitoring Server no Skype for Business Server. O CQD usa o Microsoft SQL Server Analysis Services para fornecer informações agregadas de uso e qualidade de chamada, bem como para filtragem e pivô no conjunto de dados. Os recursos do CQD incluem:
  
- **Armazenamento de arquivamento de dados de QoE por meio do componente arquivo QoE do CQD.** O componente arquivo morto QoE pode armazenar dados de QoE por uma duração muito maior do que o Monitoring Server pode. Isso permite tendências e relatórios de até sete meses de dados por vez, com a capacidade de deslizar a janela de relatório até o momento em que há dados.
- **Relatórios e análises usando o poder e a velocidade do Microsoft SQL Server Analysis Services.** O CQD utiliza o Microsoft SQL Analysis Services para fornecer recursos rápidos de resumo, filtro e pivô para a energia do painel por meio de um Cubo de Análise. Relatar a velocidade de execução e a capacidade de detalhar os dados pode reduzir significativamente o tempo de análise.
- **Novo esquema de dados otimizado para relatórios de qualidade de chamada.** O Cubo tem um esquema projetado para relatórios e investigações de qualidade de voz. Os usuários do portal podem se concentrar nas tarefas de relatório em vez de descobrir como o esquema de banco de dados de Métricas de QoE mapeia para as exibições de que precisam. A combinação entre o Arquivo de QoE e o Cubo fornece uma abstração que reduz a complexidade do relatório e da análise por meio do CQD. O esquema de banco de dados de Arquivo QoE também contém tabelas que podem ser preenchidas com dados específicos da implantação para aprimorar o valor geral dos dados.
- **Designer de relatório integrado e edição de relatório in-place.** O componente portal vem com vários relatórios integrados modelados após a Metodologia de Qualidade de Chamada. Os usuários do portal podem modificar os relatórios e criar novos relatórios por meio da funcionalidade de edição do Portal.
- **Acesso à API Web aos Dados de Cubo de Análise e Estrutura de Relatório.** A estrutura de relatórios do Painel não é a única maneira de exibir os dados do Cubo. O CQD fornece vários exemplos de uso de HTML e JavaScript para recuperar dados das APIs Web do CQD e renderizar os dados em um formato personalizado. A combinação do Editor de Relatórios e das APIs Web do CQD permite a criação rápida de protótipos de relatórios e layout de relatório personalizado.

> [!NOTE]
> Um administrador agora pode gerenciar o Skype for Business Server 2019 usando [o CQD](https://cqd.teams.microsoft.com) versão 3 (faça logoff com credenciais de Administrador). Isso requer uma implementação híbrida e o uso do CALL Data Connector (CALL Data Connector). Consulte [Planejar o Conector de Dados de Chamada](/SkypeForBusiness/hybrid/plan-call-data-connector) para obter mais informações sobre como habilenciar o TAMBÉM. Para obter a documentação do CQD versão 3, consulte Ativar e usar o Painel de Qualidade de Chamadas do Microsoft Teams e [do Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) para obter mais informações sobre o CQD versão 3.

## <a name="cqd-design-goals"></a>Metas de design do CQD

O CQD permite que os profissionais de IT usem dados agregados para identificar áreas de foco em seu ambiente com problemas de qualidade de mídia. Ele permite que um profissional de IT compare estatísticas para diferentes grupos de usuários e identifique tendências e padrões. Não se concentra na resolução de problemas de chamada individuais, mas na identificação de problemas e soluções que se aplicarão a muitos usuários em um determinado ambiente. 
  
## <a name="call-quality-dashboard-components"></a>Componentes do Painel de Qualidade da Chamada

O Painel de Qualidade da Chamada consiste em vários bancos de dados, trabalhos, processos e aplicativos Web do Microsoft SQL Agent. Os trabalhos do Microsoft SQL Agent copiam periodicamente os dados do banco de dados de Métricas de QoE para o banco de dados de Arquivo QoE e processam o Cubo com os dados no banco de dados de Arquivo QoE. O banco de dados repositório armazena as definições de relatório que a energia o Portal. O Portal fornece acesso do navegador aos dados do Cubo. 
  
Os componentes do CQD, incluindo os bancos de dados de Arquivo QoE, Cubo e Repositório, podem ser instalados no Monitoring Server, instalados em seu próprio servidor ou instalados em vários servidores. O método de instalação específico depende das demandas de desempenho do CQD, bem como do impacto em outros processos nos mesmos servidores. Para obter mais informações, consulte a seção "Componentes e topologias do CQD" posteriormente neste artigo.
  
### <a name="architectural-overview"></a>Visão Geral de Arquitetura

Para resumir, o CQD requer os seguintes elementos:
  
- Dois bancos de dados: um banco de dados de arquivo morto e um banco de dados de repositório.
    
- Um cubo SSAS visualizando dados agregados 
    
- O IIS hospeda o Portal da Web do CQD
    
![Componentes CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
A mesma arquitetura CQD dá suporte ao Lync Server 2013 e ao Skype for Business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD e Skype for Business vs. Lync 2013

 Somente em um ambiente do Skype for Business, os seguintes recursos estão disponíveis:
  
- Wi-Fi de intensidade do sinal
    
- Wi-Fi de drivers de chipset
    
- Rate my Call data 
    
## <a name="information-available-through-cqd"></a>Informações disponíveis por meio do CQD

O CQD pode mostrar contagens de fluxo de compartilhamento de áudio, vídeo e aplicativos do Skype for Business Server e contagem de chamadas boas versus ruins, bem como proporções de chamadas ruins para boas. As exibições podem ser cortadas e filtradas por muitas dimensões diferentes. O CQD desenha dados do banco de dados de Métricas de QoE no Monitoring Server. Os dados são mesclados com quaisquer dados fornecidos pelo cliente, como o mapeamento de sub-rede para construção de rede para tornar possíveis relatórios como "Qualidade da Chamada por Construção". 
  
O CQD também abstrai muitas das idiossyncrasies de dados QoE internas, como "chamador" e "chamado", de forma que o usuário possa se concentrar na criação de exibições de relatório em torno de "servidor" e "cliente". Seguindo a Metodologia de Qualidade da Chamada, o CQD é simplificado para ajudar a identificar as condições que grupos de chamadas ruins têm em comum— um dos princípios para melhorar a qualidade da chamada.
  
## <a name="viewing-data-in-cqd"></a>Exibindo dados no CQD

Os dados do CQD podem ser exibidos por meio do Portal CQD e acessados por meio de chamadas à API REST.
  
### <a name="cqd-portal"></a>CQD Portal

O Portal é a maneira mais rápida de exibir os dados no Cubo. O Portal vem com vários relatórios integrados que são imediatamente usáveis. Os relatórios integrados são vinculados de maneira estruturada para orientar o usuário a fatias sucessivamente menores e menores dos dados da chamada. Os relatórios integrados também destacam as várias maneiras diferentes pelas quais os dados podem ser mostrados demonstrando uma combinação de gráficos e tabelas com pivôs, filtros e medidas diferentes. Cada usuário que acessa o Portal pode ter seu próprio conjunto de relatórios que pode modificar e compartilhar. Para obter mais informações sobre o uso do Portal da Web do CQD, consulte Usar o Painel de Qualidade de Chamadas [do Skype for Business Server.](use.md)
  
Sistemas operacionais com suporte para o Portal CQD: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 e Windows Server 2016 (Skype for Business Server 2019 CQD apenas).
  
Navegadores com suporte para o Portal CQD: Internet Explorer 11, Internet Explorer 10 e Internet Explorer 9.
  
### <a name="rest-apis"></a>APIs REST

Os dados do Cubo também podem ser acessados por meio de chamadas à API REST. Os dados recuperados por meio das chamadas à API REST podem ser renderizados por meio de páginas HTML. Os usuários podem aproveitar a velocidade da consulta e o esquema de alto nível do CQD enquanto ainda criam relatórios personalizados adequados para suas necessidades comerciais. Para obter mais informações sobre a API e exemplos, consulte Desenvolver Painel de [Qualidade de Chamada para Skype for Business Server.](develop.md) 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definindo os requisitos da sua organização para o CQD

O CQD fornece arquivamento de dados de QoE e uma análise rápida e profunda dos dados de qualidade da chamada. O guia a seguir ajuda você a decidir quando e por que implantaria o CQD.
  
### <a name="when-to-deploy-cqd"></a>Quando implantar o CQD

 **O CQD pode ser implantado para estabelecer uma medição de qualidade de chamada de linha de base, mesmo se uma organização não tiver problemas de qualidade de chamada.** Estabelecer uma medição de qualidade de chamada de linha de base é importante porque cada organização tem uma combinação diferente de Wi-Fi versus com fio e remota versus funcionários do escritório. Quando surgirem problemas de qualidade de chamada, as medições de qualidade de chamada mais recentes podem ser comparadas a intervalos de tempo anteriores. Os recursos mais importantes do CQD permitem a detecção fácil de alterações na qualidade da chamada ao longo do tempo.
  
 **O CQD pode ser implantado para encontrar proativamente áreas problemáticas que possam afetar a qualidade da chamada.** Mesmo que a qualidade média de chamada de uma organização possa atender aos alvos definidos pela organização, pode haver grupos de problemas de qualidade de chamada ocultos atrás das métricas médias. O CQD permite detalhamento de tabela dinâmica de métricas de qualidade de chamada por muitas dimensões no banco de dados QoEMetrics. Identificar outliers em grupos de pares é uma maneira rápida de localizar proativamente problemas de qualidade de chamada.
  
 **O CQD deve ser implantado se houver problemas de qualidade de chamada na organização para reduzir o tempo necessário para solucionar problemas.** O CQD pode simplificar as investigações de qualidade de chamada existentes, oferecendo desempenho de relatórios rápido e recursos dinâmicos de busca. O CQD foi projetado para vários tipos de fluxos de trabalho na validação de investigações de qualidade de chamada de reparos no ambiente.
  
### <a name="why-deploy-cqd"></a>Por que implantar o CQD

 **O CQD deve ser implantado se o relatório de QoE precisar ocorrer por mais de 3 meses de dados.** O banco de dados QoEMetrics e os relatórios do servidor de monitoramento foram projetados para reter e relatar um pequeno conjunto de dados. O banco de dados de Métricas de QoE é otimizado para inserções rápidas e, portanto, o relatório de desempenho pode ser impedido por um grande volume de chamadas ou acesso de relatório concorrente ao banco de dados. O banco de dados de Arquivo de QoE do CQD fornece uma segunda cópia dos dados de Métricas de QoE com recursos de retenção muito mais longos. O Portal também é otimizado para mostrar até sete meses de dados por vez e pode relatar todos os dados no Arquivo QoE conforme necessário.
  
 **O CQD deve ser implantado se relatórios de QoE personalizados são necessários.** O Portal tem um recurso editor de relatórios para criar e criar relatórios de forma rápida e fácil. Ele também disponibiliza APIs REST para acesso programático aos dados do cubo, permitindo a apresentação personalizada usando HTML/JavaScript ou muitas outras estruturas. Não é mais necessário criar novas consultas SQL com a finalidade de criar exibições de dados personalizadas para relatórios.
  
 **O CQD deve ser implantado se a funcionalidade de relatório de QoE existente não atender à velocidade ou profundidade exigida pela organização.** O CQD vem com muitos relatórios integrados. Os relatórios são imediatamente úteis e demonstram como a análise progressiva dos dados pode oferecer informações adicionais em cada nível. A hierarquia de relatórios também ajuda no gerenciamento de vários relatórios de maneira lógica e promove a criação de muito mais relatórios que são facilmente acessíveis e compreensíveis. O CQD não oferece apenas velocidade e flexibilidade, mas também é otimizado para os fluxos de trabalho desenvolvidos pela Metodologia de Qualidade de Chamada.
  
## <a name="components-and-topologies-for-cqd"></a>Componentes e topologias para CQD

O CQD vem com vários componentes e ajuda a entender os requisitos de cada componente e sua relação entre si para obter a implantação mais simples e de melhor desempenho da ferramenta. A tabela a seguir descreve o componente dependente para cada componente CQD.
  

|**Nome do componente**|**Componente dependente**|
|:-----|:-----|
|Arquivo QoE  <br/> |Microsoft SQL Server  <br/> |
|Cubo  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Serviços de Informações da Microsoft  <br/> |
|Serviço de Repositório (parte da instalação do Portal)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Para o Arquivo QoE e o Cubo, determinadas opções de implantação exigem edições Business Intelligence ou Enterprise do Microsoft SQL Server. Consulte os [requisitos de infraestrutura para a seção CQD](plan.md#Infrastructure_Req) abaixo para obter mais detalhes.
  
![Componentes CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuração de servidor único

Todos os componentes do CQD e componentes dependentes podem ser instalados em uma máquina. A configuração de caixa única é a configuração mais simples e permite que o CQD seja independente. O CQD só precisa de acesso ao banco de dados de Métricas de QoE no Monitoring Server. O Servidor CQD pode ser uma máquina autônoma, uma máquina virtual ou até mesmo o Monitoring Server, dependendo dos recursos disponíveis da máquina host e dos requisitos de desempenho. 
  
Durante a instalação, o usuário que executa a instalação simplesmente precisa fornecer as instâncias do Microsoft SQL Server e do Microsoft SQL Server Analysis Services que foram configuradas anteriormente no computador em que o CQD deve ser instalado. Consulte Deploy [Call Quality Dashboard for Skype for Business Server](deploy-0.md) para obter mais informações.
  
### <a name="multiserver-configuration"></a>Configuração de vários servidores

Em uma configuração de vários servidores, o Arquivo QoE, o Cubo e o Portal podem estar em máquinas diferentes. Há dois usos principais para a configuração de vários servidores:
  
- Hospedagem do Portal da Web do CQD e do Cubo CQD em servidores diferentes.
    
- Hospedagem de um Portal de "desenvolvimento" separado do Portal de "produção". 
    
  **Hospedagem do Portal da Web do CQD e do Cubo CQD em diferentes máquinas.** As organizações que podem ter requisitos para separar o Portal CQD da instalação do SQL Server ou que talvez queira misturar e combinar edições do SQL Server para a instância do SQL Server e a instância do SQL Server Analysis Services podem optar por instalar o Portal CQD e o Cubo CQD em máquinas diferentes. O componente Arquivamento de QoE também pode ser o único componente CQD instalado se a organização simplesmente quiser ter um método sustentável para arquivar os dados de QoE sem atingir limites de desempenho no Monitoring Server.
  
![CQD de Servidor Único](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hospedagem de um Portal de "desenvolvimento" separado do Portal de "produção".** As organizações que desenvolvem seus próprios relatórios personalizados (por meio das APIs REST) podem preferir implantar instâncias adicionais do Portal do CQD junto com o Portal de produção que os usuários regulares acessam para monitoramento ou investigações de qualidade de chamada. O Portal de desenvolvimento pode isolar qualquer modificação no Portal do ambiente de produção. Os portais da Web adicionais podem ser implantados em diferentes máquinas (mostrados abaixo) ou implantados em diretórios da Web diferentes no mesmo computador (não mostrados). Para realizar o último, o portal da Web CQD adicional deve ser copiado para a máquina de produção manualmente porque o processo de instalação do CQD sempre implanta o Portal da Web do CQD no site padrão com nomes de aplicativos Web predefinidos.
  
![Planejar o CQD Multi Server](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologias suportadas

O CQD não mescla dados de vários bancos de dados QoEMetrics, como é o caso em que há várias topologias do Skype for Business Server, cada uma com seu próprio Monitoring Server. Cada instância do CQD deve apontar para um banco de dados QoEMetrics. No entanto, como o CQD move grande parte da carga de trabalho de relatório do Monitoring Server, grandes organizações que precisavam implantar um Monitoring Server por topologia do Skype for Business Server devem considerar o uso de um Monitoring Server para todas as topologias.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisitos de infraestrutura para CQD
<a name="Infrastructure_Req"> </a>

O CQD, incluindo todos os seus componentes e componentes dependentes, pode ser implantado em uma máquina virtual, em uma única máquina ou em várias máquinas. Os requisitos mínimos de software e hardware estão listados abaixo. A disponibilidade de dados e o desempenho da consulta podem variar de minutos para horas, dependendo do número de usuários ativos do Skype for Business Server e do hardware e da configuração, para que algumas medidas de desempenho sejam fornecidas abaixo.
  
|||
|:-----|:-----|
|Para o CQD 2015 <br/> |  <br/> |
|Sistemas operacionais com suporte   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|SQL Server com suporte  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Para o CQD 2019 <br/> |  <br/> |
|Sistemas operacionais com suporte   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|SQL Server com suporte  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
O CQD utiliza o Microsoft SQL Server, o Microsoft SQL Server Analysis Services e o Microsoft Internet Information Services para que os requisitos mínimos de hardware e software do CQD sejam basicamente os mesmos que esses componentes dependentes. No entanto, com base nos requisitos da organização sobre a data freshness (que dependerá em parte do volume de dados de QoE gerados pela organização) e no custo de implantação, considerações adicionais sobre a implantação devem ser feitas.
  
O processamento de dados no CQD é separado em dois estágios principais: 
  
- Processo de arquivamento de QoE
    
- Processamento de cubos CQD
    
  **Processamento de arquivo QoE.** A tarefa de processamento de Arquivo QoE copia os dados do banco de dados de Métricas de QoE no Monitoring Server para o banco de dados de Arquivo QoE. Há duas situações em que o tempo de processamento da tarefa teria características de desempenho fundamentalmente diferentes. A primeira é após a instalação inicial do CQD. Quando a tarefa for executado pela primeira vez após uma nova instalação, a tarefa de processamento do Arquivo QoE copiará todos os dados que estão no banco de dados de Métricas de QoE para o banco de dados de Arquivo QoE. O segundo é o processamento periódico após essa rodada inicial. A tarefa de processamento do Arquivo QoE será executado a cada 15 minutos e processará quaisquer novos registros de QoE que estão no banco de dados de Métricas de QoE. Geralmente, o tempo de processamento inicial não é uma preocupação, pois é executado somente na primeira vez, quando o CQD é instalado. No entanto, se o servidor CQD estiver gravemente sub-provisionado, essa tarefa poderá levar várias horas. Consulte a tabela abaixo para ver, por exemplo, tempos iniciais de processamento do Arquivo QoE.
  
  **Processamento de cubos CQD.** A tarefa de processamento de cubo agrega os dados do banco de dados de Arquivo QoE no Cubo. O tempo inicial de processamento do cubo e o tempo de processamento do cubo subsequente são determinados pela edição do SQL Server Analysis Services usada para o Cubo CQD. Se a edição Standard for usada, não haverá diferença entre o tempo inicial de processamento do cubo e o tempo de processamento do cubo subsequente, pois cada vez que os dados do Cubo são atualizados, ele sempre será um processamento completo de todos os dados disponíveis. (Isso significa que o tempo de processamento do Cubo aumenta à medida que a quantidade de dados no banco de dados de Arquivo QoE aumenta.) Como o Business Intelligence Edition e o Enterprise Edition do SQL Server têm suporte à partição, se qualquer uma das edições for usada, somente a inicialização processará todos os dados no banco de dados de Arquivo QoE. Em sequências subsequentes, quando a tarefa é disparada a cada 15 minutos, a tarefa processará apenas os novos registros adicionados ao banco de dados de Arquivo QoE desde a última vez em que a tarefa foi executado. Uma vez por dia, também haverá um processamento completo na partição que contém os dados do mês atual.
  
As características da máquina física podem afetar o desempenho do CQD, bem como os recursos de software disponíveis nos componentes do SQL Server. O componente arquivamento de QoE será mais intensivo em disco em comparação com outros componentes, enquanto o componente De cubo será mais CPU e memória. Todos esses fatores contribuem para o tempo total de processamento de dados do CQD, o que afeta diretamente a disponibilidade e a renovação dos dados. As organizações devem tomar decisões sobre o hardware e software com base nas necessidades individuais da organização. 
  
### <a name="tested-hardware-configurations"></a>Configurações de hardware testadas

Esta seção faz a suposição de que há um único banco de dados QoEMetrics no ambiente. 
  
**Perfis de computador**

|**Máquina**|**Núcleos da CPU**|**RAM**|**Arquivo QoE e Cubo no mesmo disco**|**Arquivo QoE e SQL Temp DB no mesmo disco**|
|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |4   <br/> |7 GB  <br/> |Sim  <br/> |Sim  <br/> |
|4 núcleos  <br/> |4   <br/> |20 GB  <br/> |Sim  <br/> |Não  <br/> |
|8 núcleos  <br/> |8   <br/> |32 GB  <br/> |Sim  <br/> |Não  <br/> |
|16 núcleos  <br/> |16   <br/> |128 GB  <br/> |Não  <br/> |Não  <br/> |
   
**Resultados de desempenho**

|**Máquina**|**Tamanho do banco de dados de métricas de QoE**|**Partições SQL**|**Tipo de disco**|**Número de fluxos**|**Processo inicial de arquivamento**|**Processo de cubo inicial**|**Processo de Arquivamento Subsequente**|**Processo de cubo subsequente**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |900 MB  <br/> |Único  <br/> |VHD (tamanho variável)  <br/> |0,5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Único  <br/> |VHD (tamanho variável)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Único  <br/> |VHD (tamanho fixo)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |Mais de 30 GB  <br/> |Único  <br/> |VHD (tamanho fixo)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 núcleos  <br/> |9 GB  <br/> |Único  <br/> |Vários discos  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 núcleos  <br/> |9 GB  <br/> |Vários  <br/> |Vários discos  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 núcleos  <br/> |Mais de 30 GB  <br/> |Único  <br/> |Vários discos  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 núcleos  <br/> |Mais de 30 GB  <br/> |Vários  <br/> |Vários discos  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 núcleos  <br/> |200 GB  <br/> |Único  <br/> |Vários discos  <br/> |125 M  <br/> |6+ dias  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 núcleos  <br/> |500 GB  <br/> |Vários  <br/> |Vários eixos  <br/> |250 M  <br/> |8 dias  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Não se espera que eles sejam encontrados em implantações reais porque o banco de dados de Métricas de QoE teria que ter 9 e 18 meses de dados, respectivamente, mas eles são fornecidos aqui para completar.
  
### <a name="service-account-requirements"></a>Requisitos da conta de serviço

Você precisará de uma conta (com acesso de leitura à QoEMetrics) que o SQL Agent no servidor CQD possa usar para importar dados para o QoEArchiveDB.
  
Você também pode precisar configurar uma conta separada para um trabalho SSAS para puxar dados de QoEArchiveDB (este é um processo opcional).
  
O IIS usa mais comumente o Serviço de Rede como Identidade do Pool de Aplicativos, mas pode ser configurado para uma Conta de Serviço.
  
### <a name="portal-access-control"></a>Controle de Acesso de Portal

Por padrão, qualquer usuário autenticado tem acesso. Isso pode ser alterado usando regras de Autorização do IIS para restringir a um grupo específico.
  
### <a name="pre-install-requirements"></a>Requisitos de pré-instalação

Estas instruções pressupom que um banco de dados de Métricas de QoE já foi instalado e está em execução em algum lugar na topologia do Skype for Business Server.
  
#### <a name="hardware-requirements"></a>Requisitos de hardware

O CQD utiliza o Microsoft SQL Server, o Microsoft SQL Analysis Server e o Microsoft Internet Information Server para que os requisitos mínimos de hardware e software do CQD sejam basicamente os mesmos que esses componentes dependentes. No entanto, com base nos requisitos da organização sobre a data freshness (que dependerá em parte do volume de dados de QoE gerados pela organização) e no custo de implantação, considerações adicionais sobre a implantação devem ser feitas.
  
#### <a name="software-requirements"></a>Requisitos de software

Os seguintes sistemas operacionais são necessários para o CQD:
  
- Windows Server 2008 R2 com IIS 7.5
    
- Windows Server 2012 com IIS 8.0
    
- Windows Server 2012 R2 com IIS 8.5

- Windows Server 2016 com IIS 10.0 (Skype for Business Server 2019 CQD somente)

- Windows Server 2019 (Skype for Business Server 2019 CQD somente)
    
A seguir estão os serviços de função IIS necessários (em ordem hierárquica):
  
- Servidor Web
    
  - Recursos HTTP comuns
    
  - Conteúdo estático
    
  - Documento padrão
    
  - Desenvolvimento de aplicativo
    
  - ASP.NET
    
  - Filtros ISAPI
    
  - Diagnóstico &amp; de Saúde
    
  - Log HTTP
    
  - Segurança
    
  - Autorização de URL
    
  - Autenticação do Windows
    
  - Ferramentas de gerenciamento
    
  - Console de gerenciamento do IIS
    
> [!NOTE]
>  Observe o seguinte para os requisitos acima: > versões 3.5 e 4.5 do .Net framework estão disponíveis. Ambos são necessários (mais especificamente, o 3.5 SP1 é necessário). > Em alguns sistemas, se o ASP.NET for configurado antes da instalação do IIS, o ASP.NET poderá não ser registrado no IIS. O problema se manifestou por meio da ausência de pools de aplicativos para a versão .Net correspondente e também sem a versão do CLR do .NET na configuração do pool de aplicativos. Para corrigir esse problema no Windows Server 2008 R2, `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru` execute. No Windows Server 2012 e no Windows Server 2012 R2, execute seguido pela remoção do módulo "ServiceModel" do Site Padrão no IIS Manager.> As ferramentas de Gerenciamento são opcionais, mas  `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` recomendadas.
  
Para instalar esses requisitos usando o PowerShell, execute o seguinte:
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Há suporte para as seguintes versões do SQL Server:
  
|||
|:-----|:-----|
| CQD 2015 <br/> |  SQL Server 2012, SQL Server 2014, SQL Server 2016  |
|CQD 2019 <br/> |  SQL Server 2017, SQL Server 2019  |
    
O Business Intelligence ou a edição Enterprise são recomendados por motivos de desempenho. Essas edições permitem o uso de vários arquivos de partição que podem ser processados em paralelo, o que é benéfico para o processamento de dados por vários meses ou mais. 
  
Embora não seja recomendável, a edição Standard também é suportada. O processamento será restrito a uma única partição (que precisa ser configurada durante a instalação). 
  
Em todos os casos, "Database Engine Services" e "Analysis Services" devem ser instalados. É recomendável, mas não é necessário instalar também o recurso "Ferramentas de Gerenciamento - Concluídas", que adiciona suporte ao SQL Server Management Studio para Analysis Services. A tela de seleção de recursos deve se parecer com a figura.
  
![Requisitos de recursos do SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Ao configurar o SSAS, na Configuração do Analysis Services, de definida "Modo de Servidor" como "Modo de Mineração de Dados e Multidimensionais". 
  
Para obter ajuda adicional na instalação e configuração dos Recursos de Business Intelligence do SQL Server, consulte Instalar o Analysis Services no modo de mineração de dados e [multidimensionais.](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx)
  
#### <a name="account-requirements"></a>Requisitos da conta

Três contas de serviço de domínio são recomendadas no princípio de privilégios mínimos: 
  
- Uma que já tenha uma entidade de segurança de logon para o banco de dados de Métricas de QoE (com privilégio db_datareader) e uma entidade de segurança de logon na Instância do SQL Server de Arquivo QoE (necessária para criar um objeto linked server durante a configuração). Essa conta será usada para executar a etapa "Dados de Arquivo QoE" do trabalho do SQL Server Agent.
    
    > [!NOTE]
    > Se você estiver trabalhando em um ambiente altamente bloqueado, precisará verificar se essa conta de serviço tem realmente os direitos de usuário "Logon como um trabalho em lotes" e "Permitir logon localmente" no banco de dados de Monitoramento de Métricas de QoE do SQL Server e no SQL Server de Arquivo QoE.
    
- Um que será usado para executar a etapa "Cubo de Processo" do trabalho do SQL Server Agent. A Instalação criará uma entidade de segurança de logon para o banco de dados de Arquivo QoE (com privilégio de leitura e gravação) e também criará um membro na Função QoE (com privilégios de controle total) para o Cubo.
    
- Um que será usado para executar o Processo de Trabalho do IIS para os portais da Web e APIs da Web. A Instalação criará uma entidade de segurança de logon para o banco de dados de Arquivo Morto QoE (com privilégio de leitura), uma entidade de segurança de logon no banco de dados do Repositório (com privilégio de leitura e gravação) e um membro do QoERole (com privilégio de controle total) para o Cubo. 
    
    > [!NOTE]
    > Quando o banco de dados de Arquivo QoE e o banco de dados repositório estão hospedados no mesmo SQL Server, apenas uma entidade de segurança de logon com dois mapeamentos de usuário é criada. 
  
As duas primeiras contas podem ser consideradas logicamente como "contas de serviço de back-end" e a última é uma "conta de serviço front-end". Embora não seja recomendável, é possível usar uma única conta em todos os casos.
  
> [!NOTE]
> A conta de usuário que inicia a instalação também deve ter acesso de leitura ao banco de dados de métricas de QoE (além de ter direitos de administrador de máquina no servidor QoE Archive DB onde a instalação deve ocorrer). 
  
## <a name="capacity-planning"></a>Planejamento de Capacidade
<a name="Infrastructure_Req"> </a>

O CQD foi projetado para um impacto mínimo sobre QoEMetrics: o código foi otimizado para não bloquear dados e os trabalhos de importação sãounizáveis.
  
O tipo de hardware a ser usado depende de seus requisitos para a rapidez com que as sincronizações devem ser executados. O tamanho do disco é o seguinte:
  
- QoEArchive é aproximadamente 1,5x maior que o banco de dados QoEMetrics inicialmente
    
- O cubo do SSIS compacta os dados em quase 10 x em comparação com o banco de dados
    
- Os dados são particionados mensalmente; partições podem ser excluídas
    

