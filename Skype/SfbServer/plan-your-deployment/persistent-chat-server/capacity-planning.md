---
title: Planejamento de capacidade para o Servidor de Chat Persistente Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Resumo: leia este tópico para saber mais sobre o planejamento de capacidade para o Servidor de Chat Persistente Skype for Business Server 2015.'
ms.openlocfilehash: 3b21ce2fdcb05101fb5a3fe1641e766003733fb7675331dbb12c273b1c44d7e6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334832"
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

|||
|:-----|:-----|
|Instâncias de serviço de Chat Persistente Ativo  <br/> |4   <br/> |
|Instâncias de serviço de Chat Persistente  <br/> |8 (apenas um máximo de 4 pode estar ativo; 4 deve estar inativo)  <br/> |
|Usuários ativos conectados  <br/> |80,000  <br/> |
|Total de usuários provisionados  <br/> |150,000  <br/> |
|Número de pontos de extremidade  <br/> |120,000  <br/> |
   
No exemplo anterior, o plano é dar suporte ao número máximo de usuários que o Servidor de Chat Persistente permite: quatro servidores/instâncias do serviço de Chat Persistente (pode ter mais quatro servidores passivos executando o Servidor de Chat Persistente para alta disponibilidade e recuperação de desastres) e 20.000 usuários por servidor, para um total de 80.000 usuários ativos.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planejar a capacidade de acesso à sala de chat

A tabela de exemplo a seguir pode ajudá-lo a planejar o gerenciamento do acesso à sala de chat em um pool do Servidor de Chat Persistente.
  
**Exemplo de gerenciamento de acesso à sala de chat**

||**Salas de Chat Pequenas**|**Salas de Chat Médias**|**Salas de Chat Grandes**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Tamanho das salas de chat (número de usuários conectados)  <br/> |30 por sala  <br/> |150 por sala  <br/> |16.000 por sala  <br/> ||
|Salas de chat  <br/> |32,000  <br/> |1,067  <br/> |10   <br/> |33,077  <br/> |
|% de salas que são auditórios  <br/> |1%  <br/> |1%  <br/> |50%  <br/> ||
|% das salas que estão abertas  <br/> |3%  <br/> |3%  <br/> |50%  <br/> ||
|Salas abertas (sem associação explícita)  <br/> |960  <br/> |32  <br/> |5   <br/> |997  <br/> |
|Salas não abertas (salas regulares com associação explícita)  <br/> |31,040  <br/> |1.035  <br/> |5   <br/> |32,080  <br/> |
|Salas de auditório (entrada de apresentadores adicionais)  <br/> |0  <br/> |32  <br/> |5   <br/> ||
|Salas gerenciadas por associação direta  <br/> |50%  <br/> |10%  <br/> |0%  <br/> ||
|Salas gerenciados por grupos de usuários  <br/> |50%  <br/> |90%  <br/> |100%  <br/> ||
|Grupos de usuários na lista de associação de cada sala de chat para salas abertas (não especificado explicitamente)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Usuários na lista de associação de cada sala de chat para salas não abertas  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Grupos de usuários na lista de associação de cada sala de chat para salas não abertas  <br/> |3  <br/> |5   <br/> |10   <br/> ||
|Usuários e grupos de usuários na lista de gerentes de cada sala de chat (para salas abertas e não abertas)  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Usuários e grupos de usuários na lista de apresentadores de cada sala de chat de auditório (para salas abertas e não abertas)  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Entidades de associação baseadas no usuário em todas as salas não abertas  <br/> |465,600  <br/> |15,520  <br/> |-  <br/> ||
|Entidades de associação baseadas em grupo de usuários em todas as salas não abertas  <br/> |46,560  <br/> |4656  <br/> |50  <br/> ||
|Entidades baseadas em usuários e grupos de usuários em todas as salas de chat de auditório  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Entidades de gerente baseadas em usuários e grupos de usuários em todas as listas de gerentes de salas de chat  <br/> |192,000  <br/> |6,400  <br/> |60  <br/> ||
|Usuários ativos por sala de chat  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Salas de chat por usuário  <br/> |12   <br/> |2  <br/> |2  <br/> |16   <br/> |
|Grupos de usuários na lista de associação de cada sala de chat  <br/> |10   <br/> |10   <br/> |15  <br/> ||
|Salas gerenciados por grupos de usuários  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Entidades de participação baseadas em grupos de usuário em todas as salas de chat  <br/> |155,200  <br/> |5173  <br/> |68  <br/> ||
|Entidades de participação baseadas em usuários em todas as salas de chat  <br/> |465,600  <br/> |77,600  <br/> |72,000  <br/> ||
|Usuários e grupos de usuários no gerenciador de cada sala de chat, apresentador e listas de escopo  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Usuários e grupos de usuários em todas as listas de gerente, apresentador e escopo das salas de chat  <br/> |192,000  <br/> |6400  <br/> |60  <br/> ||
|Entradas de controle de acesso  <br/> |704,160  <br/> |26,768  <br/> |160  <br/> |731,088  <br/> |
|Entradas de controle de máximo acesso  <br/> ||||2,000,000  <br/> |
   
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

||**Salas de Chat Pequenas**|**Salas de Chat Médias**|**Salas de Chat Grandes**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Usuários que podem acessar a sala de chat  <br/> |30 por sala  <br/> |150 por sala  <br/> |16.000 por sala  <br/> ||
|Porcentagem de salas que têm convites  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Salas de chat configuradas para enviar convites  <br/> |16,000  <br/> |533  <br/> |5   <br/> ||
|Usuários que podem acessar a sala de chat  <br/> |60  <br/> |225  <br/> |16,000  <br/> ||
|Convites gerados pelo Servidor de Chat Persistente  <br/> |960,000  <br/> |120,000  <br/> |80,000  <br/> |1,160,000  <br/> |
|Número de convites máximo permitido  <br/> ||||2,000,000  <br/> |
|Modelo 1 - Iniciar com o número esperado de mensagens por sala por dia  <br/> |||||
|Taxa de chat por sala (por dia)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Taxa de chat (por segundo) em todas as salas  <br/> |55.56  <br/> |18.52  <br/> |0.03  <br/> |74  <br/> |
|Modelo 2 - Iniciar com o número de mensagens postadas por usuário por dia  <br/> |||||
|Taxa de chat por usuário por dia  <br/> |15  <br/> |5   <br/> |0.1  <br/> |20  <br/> |
|Taxa de chat por sala (por dia)  <br/> |38  <br/> |375  <br/> |800  <br/> |1,213  <br/> |
|Taxa de chat (por segundo) em todas as salas  <br/> |41.67  <br/> |13.89  <br/> |0.28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Capacidade do plano para o desempenho do Servidor de Chat Persistente

A tabela a seguir descreve o modelo de usuário para o Servidor de Chat Persistente. Ele fornece a base para os requisitos de planejamento de capacidade e representa uma organização típica com 80.000 usuários simultâneos em quatro servidores.
  
**Modelo de usuário de desempenho do Servidor de Chat Persistente**

|||
|:-----|:-----|
|Número de usuários ativos conectados  <br/> |80,000  <br/> |
|Número de instâncias de serviço do Servidor de Chat Persistente  <br/> |4   <br/> |
|Tamanho de salas de chat pequenas  <br/> |30 usuários  <br/> |
|Tamanho médio de salas de chat  <br/> |150 usuários  <br/> |
|Tamanho grande de salas de chat  <br/> |16.000 usuários  <br/> |
|Número total de salas de chat  <br/> |33,077  <br/> |
|Número de salas de chat pequenas  <br/> |32,000  <br/> |
|Número de salas de chat médias  <br/> |1,067  <br/> |
|Número de salas de chat grandes  <br/> |10   <br/> |
|Número total de salas de chat por usuário  <br/> |16   <br/> |
|Número de salas de chat pequenas por usuário  <br/> |12   <br/> |
|Número de salas de chat médias por usuário  <br/> |2  <br/> |
|Número de salas de chat grandes por usuário  <br/> |2  <br/> |
|Número de salas ingressou por usuário  <br/> |24  <br/> |
|Taxa de pico de associação  <br/> |10/segundo  <br/> |
|Taxa de chat total  <br/> |24/segundo  <br/> |
|Taxa de chat para pequenas salas de chat  <br/> |22,22/segundo  <br/> |
|Taxa de chat para salas de chat médias  <br/> |1,67/segundo  <br/> |
|Taxa de chat para salas de chat grandes  <br/> |~0,15/segundo  <br/> |
|Porcentagem de salas de chat configuradas para convites  <br/> |50%  <br/> |
|Porcentagem de participação direta em  <br/> |50%  <br/> |
|Porcentagem de membros em grupo  <br/> |50%  <br/> |
|Número médio de filiações ancestrais nos Serviços de Domínio do Active Directory  <br/> |100 - 200  <br/> |
|Número de contatos inscritos por usuário  <br/> |80  <br/> |
|Número médio de pontos de extremidade por usuário  <br/> |1,5  <br/> |
|Número médio de salas de chat visíveis por ponto de extremidade  <br/> |1,5  <br/> |
|Número médio de salas de chat visíveis por usuário  <br/> |2,25 (50% para 1 sala e 50% para 2 salas); Até 6 salas abertas, uma por monitor  <br/> |
|Número de participantes sondados por intervalo  <br/> |25 por sala de chat visível  <br/> |
|Duração do intervalo de sondagem  <br/> |5 minutos  <br/> |
|Número de participantes sondados por segundo  <br/> |15.000  <br/> |
|Número de alterações de presença por hora por usuário  <br/> |6   <br/> |
|Número de alterações de presença por segundo  <br/> |133.33  <br/> |
   

