---
title: Planejamento de capacidade para o Servidor de Chat Persistente Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Resumo: leia este tópico para saber mais sobre o planejamento de capacidade para o Servidor de Chat Persistente Skype for Business Server 2015.'
ms.openlocfilehash: 4b84d06a7b6c7f20f26d22ed5718da9abf8108d9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834057"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planejamento de capacidade para o Servidor de Chat Persistente Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre o planejamento de capacidade para o Servidor de Chat Persistente Skype for Business Server 2015.
  
O Servidor de Chat Persistente pode executar um chat em tempo real com vários usuários que podem persistir para recuperação futura e pesquisa. Diferentemente do IM (mensagens instantâneas de grupo) que é salvo na caixa de correio de um usuário se o histórico da conversa estiver configurado, uma sessão do Servidor de Chat Persistente permanece aberta por mais tempo e o conteúdo é salvo em um servidor, juntamente com as mensagens, arquivos, URLs e outros dados que fazem parte de uma conversa em andamento.
  
O planejamento de capacidade é uma parte importante da preparação para implantar o Servidor de Chat Persistente. Este tópico fornece tabelas de planejamento de capacidade que você pode usar para determinar a melhor configuração para sua implantação. Ele também descreve como gerenciar melhor as implantações do Servidor de Chat Persistente que exigem maior capacidade nos horários de pico.
  
Antes de ler esta seção, você deve estar familiarizado com topologias de Chat Persistente. Para obter mais informações, consulte [Plan Persistent Chat Server topology](topology.md).

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Planejamento de capacidade do Servidor de Chat Persistente

As tabelas a seguir podem ajudá-lo com o planejamento de capacidade para o Servidor de Chat Persistente modelando como várias configurações do Servidor de Chat Persistente afetam a capacidade.
  
- Planejar capacidade para o número de usuários
    
- Planejar a capacidade de acesso à sala de chat
    
- Planejar a capacidade de acesso à sala de chat por convite
    
- Planejar capacidade para desempenho
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planejar capacidade para o número de usuários para o Servidor de Chat Persistente

Use a seguinte tabela de exemplo para determinar o número de usuários que você será capaz de suportar.
  
**Exemplo de capacidade máxima do pool do Servidor de Chat Persistente**

- Instâncias de serviço de Chat Persistente Ativo: 4  <br/> 
- Instâncias de serviço de Chat Persistente: 8 (no máximo 4 podem ser ativas; 4 devem estar inativas)  <br/>
- Usuários ativos conectados: 80.000  <br/>
- Total de usuários provisionados: 150.000  <br/>
- Número de pontos de extremidade: 120.000  <br/>
   
No exemplo anterior, o plano é dar suporte ao número máximo de usuários que o Servidor de Chat Persistente permite: quatro servidores/instâncias do serviço de Chat Persistente (pode ter mais quatro servidores passivos executando o Servidor de Chat Persistente para alta disponibilidade e recuperação de desastres) e 20.000 usuários por servidor, para um total de 80.000 usuários ativos.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planejar a capacidade de acesso à sala de chat

A tabela de exemplo a seguir pode ajudá-lo a planejar o gerenciamento do acesso à sala de chat em um pool do Servidor de Chat Persistente.
  
**Exemplo de gerenciamento de acesso à sala de chat**

|&nbsp;|Salas de Chat Pequenas|Salas de Chat Médias|Salas de Chat Grandes|Total|
|:-----|:-----|:-----|:-----|:-----|
|Tamanho das salas de chat (número de usuários conectados)   |30 por sala   |150 por sala   |16.000 por sala   ||
|Salas de chat   |32,000   |1,067   |10    |33,077   |
|% de salas que são auditórios   |1%   |1%   |50%   ||
|% das salas que estão abertas   |3%   |3%   |50%   ||
|Salas abertas (sem associação explícita)   |960   |32   |5   |997   |
|Salas não abertas (salas regulares com associação explícita)   |31,040   |1.035   |5   |32,080   |
|Salas de auditório (entrada de apresentadores adicionais)   |0   |32   |5   ||
|Salas gerenciadas por associação direta   |50%   |10%   |0%   ||
|Salas gerenciados por grupos de usuários   |50%   |90%   |100%   ||
|Grupos de usuários na lista de associação de cada sala de chat para salas abertas (não especificado explicitamente)   |0   |0   |0   ||
|Usuários na lista de associação de cada sala de chat para salas não abertas   |30   |150   |16,000   ||
|Grupos de usuários na lista de associação de cada sala de chat para salas não abertas   |3   |5   |10    ||
|Usuários e grupos de usuários na lista de gerentes de cada sala de chat (para salas abertas e não abertas)   |6    |6    |6    ||
|Usuários e grupos de usuários na lista de apresentadores de cada sala de chat de auditório (para salas abertas e não abertas)   |6    |6    |6    ||
|Entidades de associação baseadas no usuário em todas as salas não abertas   |465,600   |15,520   |-   ||
|Entidades de associação baseadas em grupo de usuários em todas as salas não abertas   |46,560   |4656   |50   ||
|Entidades baseadas em usuários e grupos de usuários em todas as salas de chat de auditório   |0   |192   |50   ||
|Entidades de gerente baseadas em usuários e grupos de usuários em todas as listas de gerentes de salas de chat   |192,000   |6,400   |60   ||
|Usuários ativos por sala de chat   |30   |150   |16,000   ||
|Salas de chat por usuário   |12    |2   |2   |16   |
|Grupos de usuários na lista de associação de cada sala de chat   |10    |10    |15    ||
|Salas gerenciados por grupos de usuários   |50%   |50%   |50%   ||
|Entidades de participação baseadas em grupos de usuário em todas as salas de chat   |155,200   |5173   |68   ||
|Entidades de participação baseadas em usuários em todas as salas de chat   |465,600   |77,600   |72,000   ||
|Usuários e grupos de usuários no gerenciador de cada sala de chat, apresentador e listas de escopo   |6    |6    |6    ||
|Usuários e grupos de usuários em todas as listas de gerente, apresentador e escopo das salas de chat   |192,000   |6400   |60   ||
|Entradas de controle de acesso   |704,160   |26,768   |160   |731,088   |
|Entradas de controle de máximo acesso   ||||2,000,000   |
   
No exemplo anterior, quando você implanta os Servidores de Chat Persistente de acordo com as diretrizes recomendadas, eles podem lidar com até 80.000 usuários ativos em um pool de quatro servidores com a conformidade habilitada.
  
Este exemplo mostra salas de chat categorizadas como pequenas (30 usuários ativos a qualquer momento), média (150 usuários ativos) e grandes (16.000 usuários ativos). O número suportado de salas de chat de um determinado tamanho na tabela acima é calculado com base no número total de:
  
- Usuários ativos no sistema
    
- Usuários ativos em salas de chat de determinado tamanho
    
- Salas de chat de um tamanho determinado onde ingressa um único usuário
    
Para cada sala de chat, a tabela de planejamento de capacidade anterior especifica o número de entradas de controle de acesso associadas à sala de chat, incluindo entradas atribuídas diretamente à sala de chat. Você pode controlar o acesso a salas de chat individuais usando listas de controle de acesso (ACLs). Você também pode controlar o acesso no nível de categoria. Em uma ACL, uma entrada de controle de acesso individual pode ser um grupo de usuários, por exemplo, um grupo de segurança, uma lista de distribuição ou um único usuário. Você pode definir as entradas de controle de acesso aos membros, aos apresentadores e aos gerentes de sala de chat.
  
> [!IMPORTANT]
> Ao planejar sua estratégia para gerenciar salas de chat, tenha em mente que o número total de entradas de controle de acesso permitido é de 2 milhões. Se as entradas de controle de acesso calculadas excederem 2 milhões, o desempenho do servidor poderá degradar significativamente. Para evitar esse problema, sempre que possível, certifique-se de que suas entradas de controle de acesso sejam grupos de usuários em vez de usuários individuais. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planejar capacidade para gerenciar o acesso à sala de chat por convite

Você pode usar a tabela de planejamento de capacidade a seguir para entender o número de convites que o Servidor de Chat Persistente cria e armazena no banco de dados de Chat Persistente quando ele é configurado para enviar convites. Você gerencia convites na categoria usando a página De configurações de Categoria da Sala de **Chat** no Painel de Controle Skype for Business Server ou usando o cmdlet Windows PowerShell, **set-csPersistentChatCategory**. Você pode gerenciar convites em uma sala de chat (em  linha com o que a categoria permite) usando a página Gerenciamento de Salas lançada a partir do cliente Skype for Business ou usando um cmdlet Windows PowerShell, **set-csPersistentChatRoom**.
  
Os dados de exemplo na tabela a seguir pressuem que, na página Configurações da sala de **Chat** para 50% de todas as salas de chat, a opção **Convites** é definida como **Sim**.
  
> [!IMPORTANT]
> Se o valor calculado para o número de convites gerados pelo servidor exceder 1 milhão, o desempenho do servidor poderá degradar significativamente. Para evitar esse problema, minimize o número de salas de chat configuradas para enviar convites ou restringir o número de usuários que podem ingressar em salas de chat que foram configuradas para enviar convites. 
  
**Acesso à sala de chat por exemplo de convite**

|&nbsp;|Salas de Chat Pequenas|Salas de Chat Médias|Salas de Chat Grandes|Total|
|:-----|:-----|:-----|:-----|:-----|
|Usuários que podem acessar a sala de chat   |30 por sala   |150 por sala   |16.000 por sala   ||
|Porcentagem de salas que têm convites   |50%   |50%   |50%   ||
|Salas de chat configuradas para enviar convites   |16,000   |533   |5   ||
|Usuários que podem acessar a sala de chat   |60   |225   |16,000   ||
|Convites gerados pelo Servidor de Chat Persistente   |960,000   |120,000   |80,000   |1,160,000   |
|Número de convites máximo permitido   ||||2,000,000   |
|Modelo 1 - Iniciar com o número esperado de mensagens por sala por dia   |||||
|Taxa de chat por sala (por dia)   |50   |500   |100   |650   |
|Taxa de chat (por segundo) em todas as salas   |55.56   |18.52   |0.03   |74   |
|Modelo 2 - Iniciar com o número de mensagens postadas por usuário por dia   |||||
|Taxa de chat por usuário por dia   |15    |5   |0.1   |20   |
|Taxa de chat por sala (por dia)   |38   |375   |800   |1,213   |
|Taxa de chat (por segundo) em todas as salas   |41.67   |13.89   |0.28   |56   |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Capacidade do plano para o desempenho do Servidor de Chat Persistente

A tabela a seguir descreve o modelo de usuário para o Servidor de Chat Persistente. Ele fornece a base para os requisitos de planejamento de capacidade e representa uma organização típica com 80.000 usuários simultâneos em quatro servidores.
  
**Modelo de usuário de desempenho do Servidor de Chat Persistente**

- Número de usuários ativos conectados: 80.000  <br/>
- Número de instâncias de serviço do Servidor de Chat Persistente: 4  <br/>
- Tamanho de salas de chat pequenas: 30 usuários  <br/> 
- Tamanho de salas de chat médias: 150 usuários  <br/>
- Tamanho de salas de chat grandes: 16.000 usuários  <br/>
- Número total de salas de chat: 33.077  <br/> 
- Número de salas de chat pequenas: 32.000  <br/> 
- Número de salas de chat médias: 1.067  <br/> 
- Número de salas de chat grandes: 10  <br/> 
- Número total de salas de chat por usuário: 16  <br/> 
- Número de salas de chat pequenas por usuário: 12  <br/> 
- Número de salas de chat médias por usuário: 2  <br/> 
- Número de salas de chat grandes por usuário: 2  <br/> 
- Número de salas ingressados por usuário: 24  <br/>
- Taxa de junção de pico: 10/segundo  <br/> 
- Taxa total de chat: 24/segundo  <br/> 
- Taxa de chat para salas de chat pequenas: 22,22/segundo  <br/> 
- Taxa de chat para salas de chat médias: 1,67/segundo  <br/> 
- Taxa de chat para salas de chat grandes: ~0,15/segundo  <br/> 
- Porcentagem de salas de chat configuradas para convites: 50%  <br/>
- Porcentagem de associações diretas: 50%  <br/>
- Porcentagem de associações de grupo: 50%  <br/> 
- Número médio de filiações ancestrais nos Serviços de Domínio do Active Directory: 100 - 200  <br/>
- Número de contatos inscritos por usuário: 80  <br/> 
- Número médio de pontos de extremidade por usuário: 1,5  <br/> 
- Número médio de salas de chat visíveis por ponto de extremidade: 1,5  <br/> 
- Número médio de salas de chat visíveis por usuário: 2,25 (50% para 1 sala e 50% para 2 salas); Até 6 salas abertas, uma por monitor  <br/> 
- Número de participantes sondados por intervalo: 25 por sala de chat visível  <br/> 
- Comprimento do intervalo de sondagem: 5 minutos  <br/> 
- Número de participantes sondados por segundo: 15.000  <br/>
- Número de alterações de presença por hora por usuário: 6  <br/> 
- Número de alterações de presença por segundo: 133,33  
   

