---
title: Planejar o painel de qualidade de chamada para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Resumo: saiba o que deve ser considerado ao planejar o painel de qualidade da chamada.'
ms.openlocfilehash: c98828f8fed3567a892e20dcab8040bb731c91f2
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328433"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planejar o painel de qualidade de chamada para o Skype for Business Server 
 
**Resumo:** Saiba mais sobre o que considerar ao planejar o painel de qualidade da chamada.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Visão geral do painel de qualidade da chamada do Skype for Business Server

O painel de qualidade de chamada do Skype for Business Server (CQD) é uma camada de relatório sobre o banco de dados de qualidade da experiência no servidor de monitoramento no Skype for Business Server. O CQD usa o Microsoft SQL Server Analysis Services para fornecer informações de uso agregado e de qualidade da chamada, bem como para filtragem e dinamização do conjunto de dados. Os recursos do CQD incluem:
  
- **Armazenamento de arquivamento de dados de QoE via componente de arquivamento QoE da CQD.** O componente de arquivo QoE pode armazenar dados de QoE por uma duração muito maior do que o Monitoring Server pode. Isso permite a tendência e a geração de relatórios de até sete meses de dados ao mesmo tempo, com a capacidade de deslizar a janela de relatório até o momento em que há dados.
- **Relatórios e análises usando o poder e a velocidade do Microsoft SQL Server Analysis Services.** O CQD utiliza o Microsoft SQL Analysis Services para fornecer recursos rápidos de resumo, filtragem e dinamização para poder usar o painel por meio de um cubo de análise. A velocidade de execução do relatório e a capacidade de fazer buscas detalhadas nos dados pode reduzir drasticamente o tempo de análise.
- **Novo esquema de dados otimizado para relatórios de qualidade de chamada.** O cubo tem um esquema projetado para relatórios e investigações de qualidade de voz. Os usuários do portal podem se concentrar nas tarefas de relatório em vez de descobrir como o esquema de banco de dados métricas de QoE é mapeado para os modos de exibição necessários. A combinação do arquivo de QoE e do cubo fornece uma abstração que reduz a complexidade de relatórios e análises via CQD. O esquema de banco de dados de QoE Archive também contém tabelas que podem ser preenchidas com dados específicos de implantação para melhorar o valor geral dos dados.
- **Designer de relatórios interno e edição de relatório in-loco.** O componente de portal vem com vários relatórios internos modelados após a metodologia de qualidade da chamada. Os usuários do portal podem modificar os relatórios e criar novos relatórios por meio da funcionalidade de edição do Portal.
- **Acesso à API Web para a estrutura do relatório e dados do cubo de análise.** A estrutura de relatórios do painel não é a única maneira de exibir os dados do cubo. O CQD fornece vários exemplos de como usar HTML e JavaScript para recuperar dados das APIs da Web do CQD e renderizar os dados em um formato personalizado. A combinação do editor de relatórios e das APIs da Web do CQD permite um protótipo rápido de relatórios e layout de relatório personalizado.

> [!NOTE]
> Um administrador agora pode gerenciar o Skype for Business Server 2019 usando o [CQD versão 3](https://cqd.teams.microsoft.com) (faça logon com credenciais de administrador). Isso requer uma implementação híbrida e o uso do conector de dados de chamada (CDC). Consulte [planejar o conector de dados de chamadas](/SkypeForBusiness/hybrid/plan-call-data-connector) para obter mais informações sobre como habilitar o CDC. Para obter a documentação do CQD versão 3, consulte [ativar e usar o painel de qualidade de chamada para Microsoft Teams e Skype for Business online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) para obter mais informações sobre o CQD versão 3.

## <a name="cqd-design-goals"></a>Metas de design do CQD

O CQD permite que os profissionais de TI utilizem dados agregados para identificar áreas de foco em seu ambiente com problemas de qualidade de mídia. Ele permite que um profissional de TI compare estatísticas de diferentes grupos de usuários e identifique tendências e padrões. O foco não está em resolver problemas de chamadas individuais, mas em identificar problemas e soluções que se apliquem a muitos usuários em um determinado ambiente. 
  
## <a name="call-quality-dashboard-components"></a>Componentes do painel de qualidade da chamada

O painel de qualidade de chamada consiste em vários bancos de dados, trabalhos do Microsoft SQL Agent, processos e aplicativos Web. Os trabalhos do Microsoft SQL Agent copiam dados periodicamente do banco de dados de métricas de QoE para o banco de dados de QoE e processam o cubo com os dados no banco de dados de QoE Archive. O banco de dados do repositório armazena as definições de relatório que alimentam o Portal. O portal fornece acesso do navegador aos dados do cubo. 
  
Os componentes CQD, incluindo o arquivo de QoE, cubo e bancos de dados de repositório, podem ser instalados no Monitoring Server, instalado em seu próprio servidor ou instalados em vários servidores. O método de instalação específico depende das demandas de desempenho do CQD, bem como do impacto para outros processos nos mesmos servidores. Para obter mais informações, consulte a seção "componentes e topologias para CQD" mais adiante neste artigo.
  
### <a name="architectural-overview"></a>Visão geral da arquitetura

Para resumir, o CQD exige os seguintes elementos:
  
- Dois bancos de dados: um banco de dados de arquivo morto e um banco de dados do repositório.
    
- Um cubo do SSAS Visualizando dados agregados 
    
- Portal da Web do IIS hospeda o CQD
    
![Componentes do CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
A mesma arquitetura CQD dá suporte ao Lync Server 2013 e ao Skype for Business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD e Skype for Business versus Lync 2013

 Em um ambiente Skype for Business apenas, os seguintes recursos estão disponíveis:
  
- Relatório de Wi-Fi da força do sinal
    
- Relatório de drivers de chipset Wi-Fi
    
- Classificar os dados da minha chamada 
    
## <a name="information-available-through-cqd"></a>Informações disponíveis por meio do CQD

CQD pode mostrar os números de fluxo de áudio, vídeo e compartilhamento de aplicativos do Skype for Business Server e a contagem de chamadas boas versus ruins, bem como razões de chamadas ruins para boas. Os modos de exibição podem ser divididos e filtrados por várias dimensões diferentes. CQD desenha dados do banco de dados métricas de QoE no Monitoring Server. Os dados são mesclados com qualquer dado fornecido pelo cliente, como o mapeamento de sub-rede para criação de uma rede para fazer com que os relatórios, como o "qualidade da chamada por prédio", seja possível. 
  
O CQD também abstrai muitas das idiossincrasias de dados internos de QoE, como "chamador" e "receptora", de forma que o usuário possa se concentrar em criar modos de exibição de relatório em "servidor" e "cliente". Seguindo a metodologia de qualidade da chamada, o CQD é simplificado para ajudar a identificar as condições que bolso de chamadas deficientes têm em comum, uma das filosofias para melhorar a qualidade das chamadas.
  
## <a name="viewing-data-in-cqd"></a>Exibindo dados no CQD

Os dados do CQD podem ser exibidos por meio do portal do CQD e acessados por meio de chamadas de API REST.
  
### <a name="cqd-portal"></a>Portal CQD

O portal é a maneira mais rápida de exibir os dados no cubo. O portal vem com vários relatórios internos que são utilizáveis imediatamente. Os relatórios internos são vinculados de forma estruturada para orientar o usuário em fatias menores e menores dos dados da chamada. Os relatórios internos também destacam as várias maneiras diferentes pelos quais os dados podem ser mostrados demonstrando uma combinação de gráficos e tabelas com pivôs, filtros e medidas diferentes. Cada usuário que acessa o portal pode ter seu próprio conjunto de relatórios que ele pode modificar e compartilhar. Para obter mais informações sobre o uso do portal da Web do CQD, consulte [usar o painel de qualidade de chamada para o Skype for Business Server](use.md).
  
Sistemas operacionais com suporte para o portal do CQD: Windows 8,1, Windows 8, Windows Server 2012 R2, Windows Server 2012 e Windows Server 2016 (Skype for Business Server 2019 somente CQD).
  
Navegadores com suporte para o portal do CQD: Internet Explorer 11, Internet Explorer 10 e Internet Explorer 9.
  
### <a name="rest-apis"></a>APIs REST

Os dados do cubo também podem ser acessados por meio de chamadas de API REST. Os dados recuperados por meio das chamadas de API REST podem ser renderizados por páginas HTML. Os usuários podem aproveitar a velocidade da consulta e o esquema de alto nível do CQD e, ao mesmo tempo, criar relatórios personalizados adequados para suas necessidades comerciais. Para obter mais informações sobre a API e os exemplos, consulte [desenvolver o painel de qualidade de chamada para o Skype for Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definindo os requisitos da sua organização para o CQD

O CQD oferece arquivamento de dados de QoE e análise rápida e profunda dos dados de qualidade da chamada. O guia a seguir o ajuda a decidir quando e por que você pode implantar o CQD.
  
### <a name="when-to-deploy-cqd"></a>Quando implantar o CQD

 **O CQD pode ser implantado para estabelecer uma medição de qualidade de chamada de linha de base, mesmo se uma organização não tiver problemas de qualidade de chamada.** O estabelecimento de uma medida de qualidade de chamada de linha de base é importante porque cada organização tem uma combinação diferente de Wi-Fi versus funcionários com fio e remotos do Office. Quando surgem problemas de qualidade de chamada, as medidas de qualidade de chamada mais recentes podem ser comparadas aos intervalos de tempo anteriores. Os recursos de tendências da CQD permitem a fácil detecção de alterações na qualidade das chamadas ao longo do tempo.
  
 **O CQD pode ser implantado para encontrar áreas problemáticas que possam afetar a qualidade da chamada.** Mesmo que a qualidade da chamada média de uma organização possa atender aos alvos definidos pela organização, pode haver bolso de problemas de qualidade de chamada que estão ocultos atrás das métricas médias. CQD permite a divisão de métricas de qualidade de chamada de tabela dinâmica de métricas de qualidade de chamada por várias dimensões no banco de dados do QoEMetrics. A localização de exceções em grupos de par é uma maneira rápida de localizar problemas com a qualidade da chamada de forma proativa.
  
 **O CQD deve ser implantado se houver problemas de qualidade de chamada na organização para reduzir o tempo necessário para solucionar problemas.** O CQD pode simplificar as investigações de qualidade de chamadas existentes, oferecendo desempenho rápido para relatórios e recursos dinâmicos de busca detalhada. O CQD foi projetado para vários tipos de fluxos de trabalho na validação de investigações de qualidade da chamada para o ambiente.
  
### <a name="why-deploy-cqd"></a>Por que implantar o CQD

 **O CQD deve ser implantado se o relatório de QoE precisar ocorrer por mais de três meses de dados.** Os relatórios do banco de dados do QoEMetrics e do Monitoring Server são projetados para reter e relatar um pequeno conjunto de dados. O banco de dados métricas de QoE é otimizado para inserções rápidas e, portanto, o desempenho dos relatórios pode ser impedido por grandes volumes de chamadas ou acesso de relatórios concorrentes ao banco de dados. O banco de dados de CQD do QoE oferece uma segunda cópia dos dados de métricas de QoE com recursos de retenção muito mais longos. O portal também é otimizado para mostrar até 7 meses de dados de cada vez e pode reportar todos os dados no arquivo de QoE conforme necessário.
  
 **O CQD deve ser implantado se forem necessários relatórios personalizados de QoE.** O portal tem um recurso de editor de relatório para criar e criar relatórios de protótipos com rapidez e facilidade. Ele também disponibiliza APIs REST disponíveis para acesso programático aos dados do cubo, permitindo uma apresentação personalizada usando HTML/JavaScript ou muitas outras estruturas. Não é mais necessário criar novas consultas SQL para a finalidade de criar modos de exibição de dados personalizados para relatórios.
  
 **O CQD deve ser implantado se a funcionalidade de relatório de QoE existente não atender a velocidade ou a profundidade exigida pela organização.** O CQD vem com muitos relatórios internos. Os relatórios são imediatamente úteis e demonstram como a análise progressiva dos dados pode oferecer informações adicionais em cada nível. A hierarquia de relatórios também ajuda a gerenciar os diversos relatórios de forma lógica e estimula a criação de muitos mais relatórios que são facilmente acessíveis e compreensíveis. O CQD não oferece apenas velocidade e flexibilidade, mas também é otimizado para os fluxos de trabalho desenvolvidos pela metodologia de qualidade da chamada.
  
## <a name="components-and-topologies-for-cqd"></a>Componentes e topologias para CQD

O CQD vem com vários componentes e ajuda a entender os requisitos de cada componente e sua relação entre eles para obter a implantação mais simples e de melhor desempenho da ferramenta. A tabela a seguir descreve o componente dependente para cada componente CQD.
  

|**Nome do componente**|**Componente dependente**|
|:-----|:-----|
|Arquivo de QoE  <br/> |Microsoft SQL Server  <br/> |
|Cubo  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Serviços de informações da Microsoft  <br/> |
|Serviço de repositório (parte da instalação do Portal)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Para o arquivo de QoE e o cubo, algumas opções de implantação exigem o Business Intelligence ou edições Enterprise do Microsoft SQL Server. Para obter mais detalhes, consulte a seção [requisitos de infraestrutura para CQD](plan.md#Infrastructure_Req) .
  
![Componentes do CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuração de servidor único

Todos os componentes do CQD e componentes dependentes podem ser instalados em um computador. A configuração de caixa única é a configuração mais simples e permite que o CQD seja independente. CQD só precisaria acessar o banco de dados métricas de QoE no servidor de monitoramento. O servidor CQD pode ser um computador autônomo, uma máquina virtual ou pode até mesmo ser o Monitoring Server, dependendo dos recursos disponíveis do computador host e dos requisitos de desempenho. 
  
Durante a instalação, o usuário que executa a instalação precisa simplesmente fornecer as instâncias do Microsoft SQL Server e do Microsoft SQL Server Analysis Services que foram configuradas anteriormente no computador em que o CQD deve ser instalado. Para obter mais informações, consulte o [painel implantar a qualidade da chamada para o Skype for Business Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>Configuração do MultiServer

Em uma configuração de vários servidores, o arquivo QoE, o cubo e o portal podem estar em máquinas diferentes. Há dois usos principais para a configuração do MultiServer:
  
- Hospedando o portal da Web do CQD e o cubo CQD em servidores diferentes.
    
- Hospedando um portal de "desenvolvimento" separado do portal de "produção". 
    
  **Hospedando o portal da Web do CQD e o cubo CQD em máquinas diferentes.** Organizações que podem ter requisitos para separar o portal do CQD da instalação do SQL Server ou que podem querer combinar e corresponder às edições do SQL Server para que a instância do SQL Server e a instância do SQL Server Analysis Services possam optar por instalar o portal do CQD e Cubo CQD em máquinas diferentes. O componente de arquivo QoE também pode ser o único componente CQD que é instalado se a organização simplesmente quer ter um método sustentável para arquivar os dados de QoE sem alcançar limites de desempenho no Monitoring Server.
  
![CQD de servidor único](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hospedando um portal de "desenvolvimento" separado do portal de "produção".** As organizações que desenvolvem seus próprios relatórios personalizados (por meio das APIs REST) podem preferir implantar instâncias de portal adicionais (CQD) junto com o portal de produção que os usuários regulares acessam para investigações ou monitoramento de qualidade de chamada. O portal de desenvolvimento pode isolar qualquer modificação no portal do ambiente de produção. Os portais adicionais da Web podem ser implantados em máquinas diferentes (mostradas abaixo) ou implantados em diferentes diretórios da Web na mesma máquina (não exibidos). Para fazer o último, o portal da Web CQD adicional deve ser copiado para o computador de produção manualmente porque o processo de instalação do CQD sempre implanta o portal da Web do CQD para o site padrão com nomes de aplicativos Web predefinidos.
  
![Plano CQD multi Server](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologias suportadas

O CQD não mescla dados de vários bancos de dados do QoEMetrics, como é o caso em que há várias topologias do Skype for Business Server, cada uma com seu próprio servidor de monitoramento. Cada instância do CQD deve apontar para um banco de dados do QoEMetrics. No entanto, como o CQD vai mover grande parte da carga de trabalho de relatórios do servidor de monitoramento, as organizações grandes que precisarem implantar um servidor de monitoramento por topologia do Skype for Business Server devem considerar o uso de um servidor de monitoramento para todas as topologias.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisitos de infraestrutura para CQD
<a name="Infrastructure_Req"> </a>

CQD, incluindo todos os componentes e componentes dependentes, podem ser implantados em uma máquina virtual, em uma única máquina ou em várias máquinas. Os requisitos mínimos de software e hardware estão listados abaixo. A disponibilidade de dados e o desempenho das consultas podem variar de minutos para horas, dependendo do número de usuários e configurações de hardware e configuração ativos do Skype for Business Server, para que algumas medidas de desempenho sejam fornecidas abaixo.
  
|||
|:-----|:-----|
|Para CQD 2015 <br/> |  <br/> |
|Sistemas operacionais com suporte  <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|SQL Server compatível  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Para CQD 2019 <br/> |  <br/> |
|Sistemas operacionais com suporte  <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|SQL Server compatível  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
O CQD utiliza o Microsoft SQL Server, o Microsoft SQL Server Analysis Services e o Microsoft Internet Information Services para que os requisitos mínimos de hardware e software da CQD sejam basicamente os mesmos que os componentes dependentes. No entanto, com base nos requisitos da organização em relação à atualização de dados (que dependerá em parte do volume de dados de QoE gerado pela organização) e no custo da implantação, considerações adicionais sobre a implantação devem ser feitas.
  
O processamento de dados no CQD está separado em dois estágios principais: 
  
- Processo de arquivo QoE
    
- Processamento de cubo CQD
    
  **Processamento de arquivo QoE.** A tarefa de processamento de arquivo QoE copia dados do banco de dados métricas de QoE no Monitoring Server para o banco de dados de sistema de QoE. Há duas situações em que o tempo de processamento da tarefa teria características de desempenho diferentes. O primeiro é após a instalação inicial do CQD. Quando a tarefa for executada pela primeira vez após uma instalação recente, a tarefa de processamento de arquivo QoE copiará todos os dados no banco de dados métricas de QoE para o banco de dados do QoE. O segundo é o processamento periódico após essa primeira rodada. A tarefa de processamento de arquivo QoE será executada a cada 15 minutos e processará quaisquer novos registros de QoE que estejam no banco de dados métricas de QoE. Geralmente, o tempo de processamento inicial não é uma preocupação porque ele é executado apenas na primeira vez, quando o CQD está instalado. No entanto, se o servidor CQD estiver severamente subvisionado, essa tarefa poderá levar várias horas. Consulte a tabela abaixo para obter os tempos de processamento de arquivo de QoE inicial.
  
  **Processamento de cubo CQD.** A tarefa de processamento de cubo agrega os dados do banco de dados de QoE do arquivo para o cubo. O tempo de processamento de cubo inicial e o tempo de processamento subsequente do cubo são determinados pela edição do SQL Server Analysis Services usadas para o cubo CQD. Se a edição padrão for usada, não haverá diferença entre o tempo inicial de processamento do cubo e o tempo de processamento do cubo subsequente, pois sempre que os dados do cubo são atualizados, ele sempre será um processamento completo de todos os dados disponíveis. (Isso significa que o tempo de processamento do cubo aumenta à medida que a quantidade de dados no banco de dados de arquivo de QoE aumenta.) Como a edição Business Intelligence Edition e Enterprise Edition do SQL Server têm suporte à partição, se qualquer uma das edições for usada, somente a execução inicial processará todos os dados no banco de dados de QoE Archiver. Em execuções subsequentes, quando a tarefa for disparada a cada 15 minutos, a tarefa só processará os novos registros adicionados ao banco de dados de arquivo de QoE desde a última vez que a tarefa foi executada. Uma vez por dia, também haverá um processamento completo na partição que contém os dados do mês atual.
  
As características da máquina física podem afetar o desempenho do CQD e os recursos de software disponíveis nos componentes do SQL Server. O componente de arquivo QoE será mais intensivo em disco em comparação a outros componentes, enquanto o componente de cubo será mais intensivo na CPU e na memória. Todos esses fatores contribuem para o tempo total de processamento de dados do CQD, que afeta diretamente a atualização e a disponibilidade dos dados. As organizações devem tomar decisões sobre o hardware e o software com base nas necessidades individuais da organização. 
  
### <a name="tested-hardware-configurations"></a>Configurações de hardware testadas

Esta seção pressupõe a pressuposição de que há um único QoEMetrics DB no ambiente. 
  
**Perfis de computador**

|**Machine**|**Núcleos de CPU**|**RAM**|**Arquivo de QoE e cubo no mesmo disco**|**Arquivo de QoE e SQL Temp DB no mesmo disco**|
|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |4  <br/> |7 GB  <br/> |Sim  <br/> |Sim  <br/> |
|4 núcleo  <br/> |4  <br/> |20 GB  <br/> |Sim  <br/> |Não  <br/> |
|8 núcleo  <br/> |08  <br/> |32 GB  <br/> |Sim  <br/> |Não  <br/> |
|16 núcleo  <br/> |16  <br/> |128 GB  <br/> |Não  <br/> |Não  <br/> |
   
**Resultados de desempenho**

|**Machine**|**Tamanho do BD de métricas de QoE**|**Partições SQL**|**Tipo de disco**|**Número de fluxos**|**Processo de arquivamento inicial**|**Processo inicial de cubo**|**Processo de arquivamento subsequente**|**Processo de cubo subsequente**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |900 MB  <br/> |Apenas  <br/> |VHD (tamanho variável)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Apenas  <br/> |VHD (tamanho variável)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Apenas  <br/> |VHD (tamanho fixo)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |30 + GB  <br/> |Apenas  <br/> |VHD (tamanho fixo)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 núcleo  <br/> |9 GB  <br/> |Apenas  <br/> |Vários discos  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 núcleo  <br/> |9 GB  <br/> |Muitos  <br/> |Vários discos  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 núcleo  <br/> |30 + GB  <br/> |Apenas  <br/> |Vários discos  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 núcleo  <br/> |30 + GB  <br/> |Muitos  <br/> |Vários discos  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 núcleo  <br/> |200 GB  <br/> |Apenas  <br/> |Vários discos  <br/> |125 M  <br/> |mais de 6 dias  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 núcleo  <br/> |500 GB  <br/> |Muitos  <br/> |Vários eixos  <br/> |250 M  <br/> |8 dias  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Eles não devem ser encontrados em implantações reais porque o banco de dados métricas de QoE precisaria ter 9 e 18 meses de dados, respectivamente, mas eles são fornecidos aqui para fins de integridade.
  
### <a name="service-account-requirements"></a>Requisitos da conta de serviço

Você precisará de uma conta (com acesso de leitura a QoEMetrics) que o agente SQL no servidor CQD pode usar para importar dados para o QoEArchiveDB.
  
Você também pode precisar configurar uma conta separada para que um trabalho do SSAS receba dados do QoEArchiveDB (esse é um processo opcional).
  
Geralmente, o IIS usa o serviço de rede como identidade do pool de aplicativos, mas pode ser configurado para uma conta de serviço.
  
### <a name="portal-access-control"></a>Controle de acesso do portal

Por padrão, qualquer usuário autenticado tem acesso. Isso pode ser alterado usando as regras de autorização do IIS para restringir a um grupo específico.
  
### <a name="pre-install-requirements"></a>Requisitos de pré-instalação

Essas instruções pressupõem que um banco de dados de métricas de QoE já foi instalado e está em algum lugar na topologia do Skype for Business Server.
  
#### <a name="hardware-requirements"></a>Requisitos de hardware

O CQD utiliza o Microsoft SQL Server, o Microsoft SQL Server e o Microsoft Internet Information Server para que os requisitos mínimos de hardware e software da CQD sejam basicamente os mesmos que os componentes dependentes. No entanto, com base nos requisitos da organização em relação à atualização de dados (que dependerá em parte do volume de dados de QoE gerado pela organização) e no custo da implantação, considerações adicionais sobre a implantação devem ser feitas.
  
#### <a name="software-requirements"></a>Requisitos de software

Os seguintes sistemas operacionais são necessários para o CQD:
  
- Windows Server 2008 R2 com IIS 7,5
    
- Windows Server 2012 com IIS 8,0
    
- Windows Server 2012 R2 com IIS 8,5

- Windows Server 2016 com IIS 10,0 (Skype for Business Server 2019 CQD somente)

- Windows Server 2019 (somente o Skype for Business Server 2019 CQD)
    
Estes são os serviços de função IIS necessários (em ordem hierárquica):
  
- Servidor Web
    
  - Recursos HTTP Comuns
    
  - Conteúdo estático
    
  - Documento padrão
    
  - Desenvolvimento do aplicativo
    
  - ASP.NET
    
  - Filtros ISAPI
    
  - Diagnóstico &amp; de integridade
    
  - Log HTTP
    
  - Segurança
    
  - Autorização de URL
    
  - Autenticação do Windows
    
  - Ferramentas de gerenciamento
    
  - Console de gerenciamento IIS
    
> [!NOTE]
>  Observe o seguinte para os requisitos acima: > versões 3,5 e 4,5 do .NET Framework estão disponíveis. Ambas são necessárias (mais especificamente, o 3,5 SP1 é necessário). > em alguns sistemas, se ASP.NET for configurado antes da instalação do IIS, então ASP.NET poderá não estar registrado no IIS. O problema manifesta-se pela ausência de pools de aplicativos para a versão .NET correspondente e também não tem a versão CLR do .NET na configuração do pool de aplicativos. Para corrigir esse problema no Windows Server 2008 R2, execute `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. No Windows Server 2012 e no Windows Server 2012 R2, `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` execute após remover o módulo "ServiceModel" do site padrão no Gerenciador do IIS. > ferramentas de gerenciamento é opcional, mas recomendado.
  
Para instalar esses requisitos usando o PowerShell, execute o seguinte:
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Há suporte para as seguintes versões do SQL Server:
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017

- SQL Server 2019 (Skype for Business Server 2019 CQD somente)
    
Business Intelligence ou Enterprise Edition é recomendado por motivos de desempenho. Essas edições permitem o uso de vários arquivos de partição que podem ser processados em paralelo, o que é benéfico para processar dados estendidos vários meses ou mais. 
  
Embora não seja recomendado, a edição padrão também tem suporte. O processamento será restringido a uma única partição (que precisa ser configurada durante a configuração). 
  
Em todos os casos, deve ser instalado "serviços de mecanismo de banco de dados" e "serviços de análise". É recomendável, mas não é necessário instalar também o recurso "ferramentas de gerenciamento-concluídas", que adiciona suporte ao SQL Server Management Studio para Analysis Services. A tela de seleção de recursos deve ter a aparência da figura.
  
![Requisitos de recursos do SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Ao configurar a configuração do SSAS, na configuração do Analysis Services, defina "modo de servidor" como "modo multidimensional e mineração de dados". 
  
Para obter ajuda adicional sobre como instalar e configurar os recursos de Business Intelligence do SQL Server, confira [instalar o Analysis Services no modo multidimensional e de mineração de dados](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Requisitos da conta

Três contas de serviço de domínio são recomendadas no princípio do privilégio mínimo: 
  
- Um que já tenha um objeto de segurança de logon para o banco de dados de métricas de QoE (com o privilégio db_datareader) e um objeto de segurança de logon no recurso QoE Archive SQL Server (necessário para criar um objeto de servidor vinculado durante a instalação). Esta conta será usada para executar a etapa "QoE Archive Data" do trabalho do SQL Server Agent.
    
- Um que será usado para executar a etapa "processar cubo" do trabalho do agente do SQL Server. A instalação criará uma entidade de segurança de logon para o arquivo de banco de dados de QoE (com privilégio de leitura e gravação) e também criará um membro na função QoE (com o privilégio controle total) para o cubo.
    
- Um que será usado para executar o processo de trabalho do IIS para portais da Web e APIs da Web. A instalação criará uma entidade de segurança de logon para o arquivo de banco de dados de QoE (com privilégio de leitura), uma entidade de segurança de logon para o banco de dados do repositório (com privilégio de leitura e gravação) e um membro no QoERole (com privilégio de controle total) para o cubo. 
    
    > [!NOTE]
    > Quando ambos os bancos de dados de QoE e repositório são hospedados no mesmo SQL Server, somente uma entidade de segurança de logon com dois mapeamentos de usuário é criada. 
  
As duas primeiras contas podem ser consideradas logicamente como "contas de serviço back-end" e a última conta é uma "conta de serviço de front-end". Embora não seja recomendado, é possível usar uma única conta em todos os casos.
  
> [!NOTE]
> A conta de usuário que inicia a instalação deve ter acesso de leitura ao BD de métricas de QoE também (além de ter direitos de administrador do computador no servidor de banco de dados de QoE em que a instalação deve ocorrer). 
  
## <a name="capacity-planning"></a>Planejamento da capacidade
<a name="Infrastructure_Req"> </a>

O CQD foi projetado para um impacto mínimo no QoEMetrics: o código foi otimizado para não bloquear dados e os trabalhos de importação são ajustáveis.
  
O tipo de hardware a ser usado depende de suas necessidades para a maneira como as sincronizações rápidas devem ser executadas. O dimensionamento de disco é o seguinte:
  
- QoEArchive é ~ 1,5 x maior do QoEMetrics DB inicialmente
    
- O cubo do SSIS compacta os dados praticamente 10x comparados ao DB
    
- Os dados são particionados mensalmente; as partições podem ser excluídas
    

