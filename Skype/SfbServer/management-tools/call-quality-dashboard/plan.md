---
title: Planejar o painel de qualidade de chamada para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Resumo: saiba o que deve ser considerado ao planejar o painel de qualidade da chamada.'
ms.openlocfilehash: 63b69d64624d13253badf1d3e6f44535afdc0993
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339436"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planejar o painel de qualidade de chamada para o Skype for Business Server 
 
**Resumo:** Saiba mais sobre o que considerar ao planejar o painel de qualidade da chamada.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Visão geral do painel de qualidade de chamada do Skype for Business Server

O painel de qualidade de chamada do Skype for Business Server (CQD) é uma camada de relatórios na parte superior do banco de dados de qualidade da experiência no servidor de monitoramento no Skype for Business Server. O CQD usa o Microsoft SQL Server Analysis Services para fornecer informações de uso agregado e qualidade de chamada, bem como para filtrar e dinamizar no conjunto de dados. Os recursos do CQD incluem:
  
- **Armazenamento de arquivamento de dados de QoE por meio do componente de arquivo QoE do CQD.** O componente de arquivo de QoE pode armazenar dados de QoE por uma duração muito maior do que o Monitoring Server. Isso permite a tendência e a geração de relatórios para até sete meses de dados de uma vez, com a capacidade de deslizar a janela de relatório no momento em que há dados.
- **Relatórios e análises usando o poder e a velocidade do Microsoft SQL Server Analysis Services.** O CQD utiliza o Microsoft SQL Analysis Services para fornecer recursos rápidos de resumo, filtro e dinâmica para alimentar o painel por meio de um cubo de análise. O relatório de velocidade de execução e a capacidade de aprofundar nos dados pode reduzir drasticamente o tempo de análise.
- **Novo esquema de dados otimizado para relatórios de qualidade de chamada.** O cubo tem um esquema projetado para investigações e relatórios de qualidade de voz. Os usuários do portal podem se concentrar nas tarefas de relatório em vez de descobrir como o esquema de banco de dados de métricas de QoE mapeia para os modos de exibição necessários. A combinação do arquivo QoE e o cubo fornece uma abstração que reduz a complexidade de relatórios e análises por meio do CQD. O esquema de banco de dados de arquivo de QoE também contém tabelas que podem ser preenchidas com dados específicos de implantação para melhorar o valor geral dos dados.
- **Designer de relatórios interno e edição de relatório in-loco.** O componente de portal vem com vários relatórios internos modelados após a metodologia de qualidade da chamada. Os usuários do portal podem modificar os relatórios e criar novos relatórios por meio da funcionalidade de edição do Portal.
- **Acesso à API Web à estrutura do relatório e aos dados do cubo de análise.** A estrutura de relatórios do painel não é a única maneira de exibir os dados do cubo. O CQD fornece vários exemplos de uso de HTML e JavaScript para recuperar dados das APIs Web do CQD e renderizar os dados em um formato personalizado. A combinação do editor de relatórios e das APIs Web do CQD permite o protótipo rápido de relatórios e layout de relatórios personalizados.

> [!NOTE]
> Um administrador agora pode gerenciar o Skype for Business Server 2019 usando o [CQD versão 3](https://cqd.teams.microsoft.com) (faça logon com credenciais de administrador). Isso requer uma implementação híbrida e o uso do Call data Connector (CDC). Consulte [Plan Call data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) para obter mais informações sobre como habilitar o CDC. Para obter a documentação do CQD versão 3, consulte [ativar e usar o painel de qualidade de chamada para o Microsoft Teams e o Skype for Business online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) para obter mais informações sobre o CQD versão 3.

## <a name="cqd-design-goals"></a>Metas de design do CQD

O CQD permite que os profissionais de ti usem dados agregados para identificar as áreas de foco em seu ambiente com problemas de qualidade de mídia. Ele permite que um profissional de ti Compare estatísticas para diferentes grupos de usuários e identifique tendências e padrões. Ele não se concentra na solução de problemas de chamadas individuais, mas na identificação de problemas e soluções que serão aplicados a muitos usuários em um determinado ambiente. 
  
## <a name="call-quality-dashboard-components"></a>Componentes do painel de qualidade da chamada

O painel de qualidade de chamada consiste em vários bancos de dados, trabalhos do Microsoft SQL Agent, processos e aplicativos Web. Os trabalhos do Microsoft SQL Agent copiam periodicamente os dados do banco de dados de métricas de QoE para o banco de dados de arquivo de QoE e processa o cubo com os dados no banco de dados de arquivo de QoE. O banco de dados de repositório armazena as definições de relatório que alimentam o Portal. O portal fornece acesso do navegador aos dados do cubo. 
  
Os componentes do CQD, incluindo o arquivo de QoE, cubo e bancos de dados de repositório, podem ser instalados no Monitoring Server, instalados em seu próprio servidor ou instalados em vários servidores. O método de instalação específico depende das demandas de desempenho do CQD e do impacto em outros processos nos mesmos servidores. Para obter mais informações, consulte a seção "componentes e topologias para CQD", mais adiante neste artigo.
  
### <a name="architectural-overview"></a>Visão Geral de Arquitetura

Para resumir, o CQD exige os seguintes elementos:
  
- Dois bancos de dados: um banco de dados de arquivo morto e um banco de dados de repositório.
    
- Um cubo do SSAS Visualizando dados agregados 
    
- IIS hospeda o portal da Web do CQD
    
![Componentes do CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
A mesma arquitetura CQD é compatível com Lync Server 2013 e Skype for Business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD e Skype for Business vs. Lync 2013

 Somente em um ambiente do Skype for Business, os seguintes recursos estão disponíveis:
  
- Relatórios de Wi-Fi de intensidade do sinal
    
- Relatórios de controladores de chipset de Wi-Fi
    
- Classificar meus dados de chamada 
    
## <a name="information-available-through-cqd"></a>Informações disponíveis por meio do CQD

O CQD pode mostrar as contagens de fluxo de áudio, vídeo e compartilhamento de aplicativos do Skype for Business Server e a contagem de chamadas boas versus ruins, bem como as taxas de chamadas ruins em boas. Os modos de exibição podem ser divididos e filtrados por várias dimensões diferentes. CQD desenha dados do banco de dados de métricas de QoE no servidor de monitoramento. Os dados são mesclados com qualquer dado fornecido pelo cliente, como o mapeamento de sub-rede de rede para criar relatórios, como o "qualidade de chamada por compilação" possível. 
  
O CQD também abstrai muitas das idiossincrasias de dados de QoE internos, como "chamador" e "receptor", de forma que o usuário possa se concentrar na criação de modos de exibição de relatório em torno de "servidor" e "cliente". Após a metodologia de qualidade de chamada, o CQD é simplificado para ajudar a identificar as condições que o grupos de chamadas ruins têm em comum — uma das filosofias para melhorar a qualidade da chamada.
  
## <a name="viewing-data-in-cqd"></a>Exibindo dados no CQD

Os dados do CQD podem ser exibidos através do portal do CQD e acessados por meio de chamadas da API REST.
  
### <a name="cqd-portal"></a>Portal CQD

O portal é a maneira mais rápida de exibir os dados no cubo. O portal vem com vários relatórios internos que podem ser usados imediatamente. Os relatórios internos são vinculados de forma estruturada para orientar o usuário em fatias menores e menores dos dados da chamada. Os relatórios internos também realçam as várias maneiras diferentes que os dados podem ser mostrados, demonstrando uma combinação de gráficos e tabelas com dinâmicos, filtros e medidas diferentes. Cada usuário que acessa o portal pode ter seu próprio conjunto de relatórios que ele pode modificar e compartilhar. Para obter mais informações sobre o uso do portal da Web do CQD, consulte [usar o painel de qualidade de chamada para o Skype for Business Server](use.md).
  
Sistemas operacionais suportados para o portal do CQD: Windows 8,1, Windows 8, Windows Server 2012 R2, Windows Server 2012 e Windows Server 2016 (Skype for Business Server 2019 apenas CQD).
  
Navegadores com suporte para o portal do CQD: Internet Explorer 11, Internet Explorer 10 e Internet Explorer 9.
  
### <a name="rest-apis"></a>APIs REST

Os dados do cubo também podem ser acessados por meio de chamadas da API REST. Os dados recuperados por meio das chamadas da API REST podem ser renderizados por meio de páginas HTML. Os usuários podem aproveitar a velocidade de consulta e o esquema de alto nível do CQD e, ao mesmo tempo, criar relatórios personalizados adequados para suas necessidades de negócios. Para obter mais informações sobre a API e os exemplos, consulte [desenvolver o painel de qualidade de chamada para o Skype for Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definindo os requisitos de sua organização para o CQD

O CQD fornece arquivamento de dados de QoE e análise rápida e profunda dos dados de qualidade da chamada. A guia a seguir ajuda a decidir quando e por que você implantaria o CQD.
  
### <a name="when-to-deploy-cqd"></a>Quando implantar o CQD

 **O CQD pode ser implantado para estabelecer uma medição de qualidade de chamada de linha de base, mesmo se uma organização não tiver problemas de qualidade de chamada.** Estabelecer uma medição de qualidade de chamada de linha de base é importante porque cada organização tem uma combinação diferente de Wi-Fi versus com fio e remota em relação a funcionários do Office. Quando ocorrem problemas de qualidade de chamada, as medidas de qualidade de chamada mais recentes podem ser comparadas aos intervalos de tempo anteriores. Os recursos de tendência do CQD permitem a fácil detecção de alterações na qualidade da chamada ao longo do tempo.
  
 **O CQD pode ser implantado para encontrar áreas problemáticas que possam afetar a qualidade da chamada.** Mesmo que a qualidade de chamada média de uma organização possa atender aos destinos definidos pela organização, pode haver grupos de problemas de qualidade de chamada que estão ocultos atrás das métricas médias. O CQD permite a divisão de métrica de qualidade de chamada de tabela dinâmica, como de várias dimensões no banco de dados do QoEMetrics. A localização de exceções nos grupos de pontos é uma maneira rápida de localizar problemas de qualidade de chamada de forma proativa.
  
 **O CQD deve ser implantado se houver problemas de qualidade de chamada na organização para reduzir o tempo necessário para solucionar problemas.** O CQD pode simplificar as investigações de qualidade de chamadas existentes, oferecendo desempenho de relatórios rápidos e recursos de aprofundamento dinâmicos. O CQD é projetado para vários tipos de fluxos de trabalho na validação de investigações de qualidade de chamada para o ambiente.
  
### <a name="why-deploy-cqd"></a>Por que implantar o CQD

 **CQD deve ser implantado se o relatório de QoE precisar ocorrer por mais de três meses de dados.** O banco de dados do QoEMetrics e os relatórios do Monitoring Server foram projetados para reter e relatar um pequeno conjunto de dados. O banco de dados de métricas de QoE é otimizado para inserções rápidas e, portanto, o desempenho do relatório pode ser impedida por grandes volumes de chamadas ou acesso de relatórios concorrentes ao banco de dados. O banco de dados de arquivo de QoE do CQD fornece uma segunda cópia dos dados de métricas de QoE com recursos de retenção muito mais longos. O portal também é otimizado para mostrar até 7 meses de dados por vez e pode relatar todos os dados no arquivo de QoE, conforme necessário.
  
 **O CQD deve ser implantado se os relatórios personalizados de QoE forem necessários.** O portal tem um recurso editor de relatórios para criar relatórios de protótipos e de forma rápida e fácil. Ele também disponibiliza APIs REST disponíveis para acesso programático aos dados do cubo, permitindo a apresentação personalizada usando HTML/JavaScript ou muitas outras estruturas. Não é mais necessário criar novas consultas SQL para a finalidade de criar modos de exibição de dados personalizados para relatórios.
  
 **CQD deve ser implantado se a funcionalidade de relatórios QoE existente não atender à velocidade ou à profundidade exigida pela organização.** O CQD vem com vários relatórios internos. Os relatórios são imediatamente úteis e demonstram como a análise progressiva dos dados pode oferecer insights adicionais em cada nível. A hierarquia de relatórios também ajuda no gerenciamento dos vários relatórios de maneira lógica e estimula a criação de muitos outros relatórios que são facilmente acessíveis e compreensíveis. O CQD não oferece apenas velocidade e flexibilidade, mas também é otimizado para os fluxos de trabalho desenvolvidos pela metodologia de qualidade de chamada.
  
## <a name="components-and-topologies-for-cqd"></a>Componentes e topologias do CQD

O CQD vem com vários componentes e ajuda a entender os requisitos de cada componente e sua relação entre eles para obter a implantação mais simples e de melhor desempenho da ferramenta. A tabela a seguir descreve o componente dependente para cada componente do CQD.
  

|**Nome do componente**|**Componente dependente**|
|:-----|:-----|
|Arquivo de QoE  <br/> |Microsoft SQL Server  <br/> |
|Simples  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Serviços de informações da Microsoft  <br/> |
|Serviço de repositório (parte da instalação do Portal)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Para o arquivo de QoE e o cubo, determinadas opções de implantação exigem Business Intelligence ou Enterprise Editions do Microsoft SQL Server. Consulte a seção [requisitos de infraestrutura para a CQD](plan.md#Infrastructure_Req) abaixo para obter mais detalhes.
  
![Componentes do CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuração de servidor único

Todos os componentes e componentes dependentes do CQD podem ser instalados em um computador. A configuração de caixa única é a configuração mais simples e permite que o CQD seja autônomo. CQD apenas precisaria acessar o banco de dados de métricas de QoE no servidor de monitoramento. O servidor do CQD pode ser um computador autônomo, uma máquina virtual ou pode até mesmo ser o servidor de monitoramento, dependendo dos recursos disponíveis da máquina host e dos requisitos de desempenho. 
  
Durante a instalação, o usuário que está executando a instalação precisa apenas fornecer as instâncias do Microsoft SQL Server e do Microsoft SQL Server Analysis Services que foram configuradas anteriormente no computador onde o CQD deve ser instalado. Para obter mais informações, consulte [implantar o painel de qualidade de chamada para o Skype for Business Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>Configuração de MultiServer

Em uma configuração de vários servidores, o arquivo de QoE, o cubo e o portal podem estar em máquinas diferentes. Há dois usos principais para a configuração de MultiServer:
  
- Hospedagem do portal Web do CQD e do cubo do CQD em servidores diferentes.
    
- Hospedagem de um portal de "desenvolvimento" separado do portal de "produção". 
    
  **Hospedagem do portal Web do CQD e do cubo do CQD em máquinas diferentes.** As organizações que podem ter requisitos para separar o portal do CQD da instalação do SQL Server ou podem querer misturar e corresponder às edições do SQL Server para a instância do SQL Server e a instância do SQL Server Analysis Services podem optar por instalar o portal do CQD e CQD cubo em máquinas diferentes. O componente de arquivo de QoE também pode ser o único componente do CQD que é instalado se a organização simplesmente quer ter um método sustentável para arquivar os dados de QoE sem atingir limites de desempenho no Monitoring Server.
  
![CQD de servidor único](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hospedagem de um portal de "desenvolvimento" separado do portal de "produção".** As organizações que desenvolvem seus próprios relatórios personalizados (por meio das APIs REST) podem preferir implantar instâncias de portal adicionais (CQD), junto com o portal de produção, que os usuários normais acessam para investigação ou investigações de qualidade de chamada. O portal de desenvolvimento pode isolar quaisquer modificações no portal do ambiente de produção. Os portais da Web adicionais podem ser implantados em máquinas diferentes (mostradas abaixo) ou implantados em diferentes diretórios da Web no mesmo computador (não mostrados). Para fazer o último, o portal da Web CQD adicional deve ser copiado manualmente para o computador de produção porque o processo de instalação do CQD sempre implanta o portal da Web do CQD no site padrão com nomes de aplicativos Web predefinidos.
  
![Planejar vários servidores do CQD](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologias suportadas

O CQD não mescla dados de vários bancos de dados do QoEMetrics, como é o caso em que há várias topologias do Skype for Business Server, cada uma com seu próprio servidor de monitoramento. Cada instância do CQD deve apontar para um banco de dados do QoEMetrics. No entanto, como o CQD moverá grande parte da carga de trabalho de relatórios do servidor de monitoramento, grandes organizações que precisam implantar um servidor de monitoramento por topologia do Skype for Business Server devem considerar o uso de um servidor de monitoramento para todas as topologias.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisitos de infraestrutura para o CQD
<a name="Infrastructure_Req"> </a>

CQD, incluindo todos os seus componentes e componentes dependentes, podem ser implantados em uma máquina virtual, em uma única máquina ou em várias máquinas. Os requisitos mínimos de software e hardware estão listados abaixo. A disponibilidade de dados e o desempenho de consultas podem variar de minutos para horas, dependendo do número de usuários e hardwares ativos do Skype for Business Server, para que algumas medidas de desempenho sejam fornecidas abaixo.
  
|||
|:-----|:-----|
|Para CQD 2015 <br/> |  <br/> |
|Sistemas operacionais com suporte   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|SQL Server com suporte  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Para CQD 2019 <br/> |  <br/> |
|Sistemas operacionais com suporte   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|SQL Server com suporte  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
O CQD utiliza o Microsoft SQL Server, o Microsoft SQL Server Analysis Services e o Microsoft Internet Information Services para que os requisitos mínimos de hardware e software do CQD sejam basicamente os mesmos dos componentes dependentes. No entanto, com base nos requisitos da organização em relação à atualização de dados (que dependerá de parte do volume de dados de QoE que a organização gera) e do custo de implantação, devem ser feitas considerações de implantação adicionais.
  
O processamento de dados no CQD é separado em dois estágios principais: 
  
- Processo de arquivo de QoE
    
- Processamento de cubo CQD
    
  **Processamento de arquivo de QoE.** A tarefa de processamento de arquivo QoE copia dados do banco de dados de métricas de QoE no servidor de monitoramento para o banco de dados de arquivo de QoE. Há duas situações em que o tempo de processamento da tarefa teria características de desempenho fundamentalmente diferentes. O primeiro é após a instalação inicial do CQD. Quando a tarefa é executada pela primeira vez após uma instalação recente, a tarefa de processamento de arquivo de QoE copiará todos os dados no banco de dados de métricas de QoE para o banco de dados de arquivo de QoE. O segundo é o processamento periódico após essa rodada inicial. A tarefa de processamento de arquivo de QoE será executada a cada 15 minutos e processará quaisquer novos registros de QoE que estejam no banco de dados de métricas de QoE. Geralmente, o tempo de processamento inicial não é uma preocupação porque é executado somente na primeira vez, quando o CQD é instalado. No entanto, se o servidor CQD estiver seriamente provisionado, essa tarefa poderá levar várias horas. Consulte a tabela abaixo para obter os tempos de processamento de arquivo morto de QoE inicial.
  
  **Processamento de cubo CQD.** A tarefa de processamento de cubo agrega os dados do banco de dados de arquivo de QoE no cubo. O tempo de processamento de cubo inicial e o tempo de processamento subsequente do cubo são determinados pelo SQL Server Analysis Services Edition usado para o cubo CQD. Se a Standard Edition for usada, não haverá diferença entre o tempo de processamento inicial do cubo e o tempo de processamento do cubo subsequente, porque cada vez que os dados do cubo são atualizados, ele sempre será um processamento completo de todos os dados disponíveis. (Isso significa que o tempo de processamento do cubo aumenta à medida que a quantidade de dados no banco de dados de arquivo de QoE aumenta.) Como o Business Intelligence Edition e Enterprise Edition do SQL Server têm suporte à partição, se a edição for usada, somente a execução inicial processará todos os dados no banco de dados de arquivo QoE. Em execuções subsequentes, quando a tarefa é disparada a cada 15 minutos, a tarefa só processará os novos registros adicionados ao banco de dados de arquivo de QoE desde a última vez em que a tarefa foi executada. Uma vez por dia, também haverá um processamento completo na partição que contém os dados do mês atual.
  
As características da máquina física podem afetar o desempenho do CQD, bem como os recursos de software disponíveis nos componentes do SQL Server. O componente de arquivamento QoE será mais intenso em disco em comparação com outros componentes, enquanto o componente de cubo será mais intensivo de CPU e memória. Todos esses fatores contribuem para o tempo total de processamento de dados do CQD, que afeta diretamente a atualização e a disponibilidade dos dados. As organizações devem tomar decisões sobre o hardware e o software com base nas necessidades individuais da organização. 
  
### <a name="tested-hardware-configurations"></a>Configurações de hardware testadas

Esta seção faz a suposição de que há um único QoEMetrics DB no ambiente. 
  
**Perfis de máquina**

|**Máquina**|**Núcleos de CPU**|**RAM**|**Arquivo de QoE e cubo no mesmo disco**|**Arquivo de QoE e SQL Temp DB no mesmo disco**|
|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |quatro  <br/> |7 GB  <br/> |Sim  <br/> |Sim  <br/> |
|4 núcleo  <br/> |quatro  <br/> |20 GB  <br/> |Sim  <br/> |Não  <br/> |
|8 núcleo  <br/> |8  <br/> |32 GB  <br/> |Sim  <br/> |Não  <br/> |
|16 núcleos  <br/> |16   <br/> |128 GB  <br/> |Não  <br/> |Não  <br/> |
   
**Resultados de desempenho**

|**Máquina**|**Tamanho do BD de métricas de QoE**|**Partições SQL**|**Tipo de disco**|**Número de fluxos**|**Processo de arquivo morto inicial**|**Processo de cubo inicial**|**Processo de arquivo morto subsequente**|**Processo de cubo subsequente**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |900 MB  <br/> |Único  <br/> |VHD (tamanho variável)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Único  <br/> |VHD (tamanho variável)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Único  <br/> |VHD (tamanho fixo)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |30 + GB  <br/> |Único  <br/> |VHD (tamanho fixo)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 núcleo  <br/> |9 GB  <br/> |Único  <br/> |Vários discos  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 núcleo  <br/> |9 GB  <br/> |Vários  <br/> |Vários discos  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 núcleo  <br/> |30 + GB  <br/> |Único  <br/> |Vários discos  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 núcleo  <br/> |30 + GB  <br/> |Vários  <br/> |Vários discos  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 núcleo  <br/> |200 GB  <br/> |Único  <br/> |Vários discos  <br/> |125 M  <br/> |6 + dias  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 núcleos  <br/> |500 GB  <br/> |Vários  <br/> |Vários eixos  <br/> |250 M  <br/> |8 dias  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Não é esperado que eles sejam encontrados em implantações reais porque o banco de dados de métricas de QoE teria que ter 9 e 18 meses de dados, respectivamente, mas eles são fornecidos aqui para fins de integridade.
  
### <a name="service-account-requirements"></a>Requisitos da conta de serviço

Você precisará de uma conta (com acesso de leitura para QoEMetrics) que o agente SQL no servidor CQD pode usar para importar dados para o QoEArchiveDB.
  
Você também pode precisar configurar uma conta separada para que um trabalho do SSAS receba dados do QoEArchiveDB (esse é um processo opcional).
  
O IIS geralmente usa o serviço de rede como identidade do pool de aplicativos, mas pode ser configurado para uma conta de serviço.
  
### <a name="portal-access-control"></a>Controle de acesso do portal

Por padrão, qualquer usuário autenticado tem acesso. Isso pode ser alterado usando regras de autorização do IIS para restringir a um grupo específico.
  
### <a name="pre-install-requirements"></a>Requisitos de pré-instalação

Estas instruções pressupõem que um banco de dados de métricas de QoE já tenha sido instalado e esteja em algum lugar na topologia do Skype for Business Server.
  
#### <a name="hardware-requirements"></a>Requisitos de hardware

O CQD utiliza o Microsoft SQL Server, o Microsoft SQL Analysis Server e o Microsoft Internet Information Server para que os requisitos mínimos de hardware e software do CQD sejam basicamente os mesmos dos componentes dependentes. No entanto, com base nos requisitos da organização em relação à atualização de dados (que dependerá de parte do volume de dados de QoE que a organização gera) e do custo de implantação, devem ser feitas considerações de implantação adicionais.
  
#### <a name="software-requirements"></a>Requisitos de software

Os sistemas operacionais a seguir são necessários para o CQD:
  
- Windows Server 2008 R2 com IIS 7,5
    
- Windows Server 2012 com IIS 8,0
    
- Windows Server 2012 R2 com IIS 8,5

- Windows Server 2016 com IIS 10,0 (Skype for Business Server 2019 CQD apenas)

- Windows Server 2019 (Skype for Business Server 2019 CQD apenas)
    
Estes são os serviços de função do IIS necessários (em ordem hierárquica):
  
- Servidor Web
    
  - Recursos HTTP comuns
    
  - Conteúdo estático
    
  - Documento padrão
    
  - Desenvolvimento de aplicativo
    
  - ASP.NET
    
  - Filtros ISAPI
    
  - Diagnóstico &amp; de integridade
    
  - Log HTTP
    
  - Segurança
    
  - Autorização de URL
    
  - Autenticação do Windows
    
  - Ferramentas de gerenciamento
    
  - Console de gerenciamento do IIS
    
> [!NOTE]
>  Observe o seguinte para os requisitos acima: > 3,5 e 4,5 versões do .NET Framework estão disponíveis. Ambos são necessários (mais especificamente, 3,5 SP1 é necessário). > em alguns sistemas, se o ASP.NET for configurado antes da instalação do IIS, o ASP.NET pode não estar registrado no IIS. O problema manifesta através da ausência de pools de aplicativos para a versão do .NET correspondente e também não tem a versão do .NET CLR na configuração do pool de aplicativos. Para corrigir esse problema no Windows Server 2008 R2, execute `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. No Windows Server 2012 e no Windows Server 2012 R2, `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` execute o depois de remover o módulo "ServiceModel" do site da Web padrão no Gerenciador do IIS. as ferramentas de gerenciamento do > são opcionais, mas recomendadas.
  
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
    
O Business Intelligence ou Enterprise Edition é recomendado por motivos de desempenho. Essas edições permitem o uso de vários arquivos de partição que podem ser processados em paralelo, o que é benéfico para processar dados que abrangem vários meses ou mais. 
  
Embora não seja recomendado, Standard Edition também é compatível. O processamento será restrito a uma única partição (que precisa ser configurada durante a instalação). 
  
Em todos os casos, os "serviços de mecanismo de banco de dados" e "serviços de análise" devem ser instalados. É recomendável, mas não é necessário instalar também o recurso "ferramentas de gerenciamento-concluídas", que adiciona suporte ao SQL Server Management Studio para o Analysis Services. A tela de seleção de recurso deve ser semelhante à da figura.
  
![Requisitos de recurso do SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Ao configurar a configuração do SSAS, na configuração do Analysis Services, defina "modo do servidor" como "modo de mineração multidimensional e de dados". 
  
Para obter ajuda adicional sobre como instalar e configurar os recursos de Business Intelligence do SQL Server, consulte [instalar o Analysis Services no modo multidimensional e de mineração de dados](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Requisitos de conta

Três contas de serviço de domínio são recomendadas no princípio de privilégio mínimo: 
  
- Um que já tenha uma entidade de segurança de logon para o banco de dados de métricas de QoE (com db_datareader privilégio) e uma entidade de segurança de logon na instância de QoE do SQL Server (necessário para criar um objeto de servidor vinculado durante a instalação). Essa conta será usada para executar a etapa "dados de arquivo de QoE" do trabalho do SQL Server Agent.
    
- Um que será usado para executar a etapa "processar cubo" do trabalho do SQL Server Agent. A instalação criará uma entidade de segurança de logon para o banco de dados de arquivo de QoE (com o privilégio de leitura e gravação) e também criará um membro na função QoE (com o privilégio controle total) para o cubo.
    
- Um que será usado para executar o processo de trabalho do IIS para os portais da Web e as APIs Web. O programa de instalação criará uma entidade de segurança de logon para o banco de dados de arquivo de QoE (com privilégio de leitura), uma entidade de segurança de logon para o banco de dados de repositório (com privilégio de leitura e gravação) e um membro em QoERole (com privilégio de controle total) para o cubo. 
    
    > [!NOTE]
    > Quando o banco de dados de arquivo de QoE e o banco de dados de repositório são hospedados no mesmo SQL Server, apenas uma entidade de segurança de logon com dois mapeamentos de usuário é criada. 
  
As duas primeiras contas podem ser logicamente consideradas como "contas de serviço back-end" e a última conta é uma "conta de serviço de front end". Embora não seja recomendado, é possível usar uma única conta em todos os casos.
  
> [!NOTE]
> A conta de usuário que inicia a instalação deve ter acesso de leitura ao banco de arquivos de métricas de QoE também (além de ter direitos de administrador de máquina no servidor de banco de arquivo de administração de QoE em que a instalação deve ocorrer). 
  
## <a name="capacity-planning"></a>Planejamento de Capacidade
<a name="Infrastructure_Req"> </a>

O CQD foi projetado para um impacto mínimo no QoEMetrics: o código foi otimizado para não bloquear dados, e os trabalhos de importação são ajustáveis.
  
O tipo de hardware a ser usado depende dos requisitos de como as sincronizações rápidas devem ser executadas. O dimensionamento de disco é o seguinte:
  
- QoEArchive é ~ 1,5 x maior do que o QoEMetrics DB inicialmente
    
- O cubo do SSIS compacta os dados quase 10x comparados ao DB
    
- Os dados são particionados mensalmente; as partições podem ser excluídas
    

