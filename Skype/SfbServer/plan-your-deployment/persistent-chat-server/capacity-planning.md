---
title: Planejamento de capacidade para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Resumo: Leia este tópico para saber mais sobre o planejamento de capacidade para o servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 9f5571be81fbda47150bbde7edf5757ebdea8a4c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815769"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planejamento de capacidade para o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre o planejamento de capacidade para o servidor de chat persistente no Skype for Business Server 2015.
  
O servidor de chat persistente pode executar chats de vários usuários e em tempo real que podem persistir para recuperação futura e pesquisa. Ao contrário das mensagens instantâneas em grupo (IM) salvas na caixa de correio de um usuário, se o histórico da conversa estiver configurado, uma sessão persistente do servidor de chat permanecerá aberta e o conteúdo será salvo em um servidor, juntamente com as mensagens, arquivos, URLs e outros dados que fazem parte de um conversa em andamento.
  
O planejamento de capacidade é uma parte importante da preparação para a implantação do servidor de chat persistente. Este tópico fornece tabelas de planejamento de capacidade que você pode usar para determinar a melhor configuração para a sua implantação. Ele também descreve como gerenciar melhor implantações persistentes do servidor de chat que exigem maior capacidade nos horários de pico.
  
Antes de ler esta seção, é importante você se familiarizar com as topologias do Chat Persistente. Para obter mais informações, veja [Plan Persistent Chat Server topology](topology.md).

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Planejamento da capacidade do servidor de chat persistente

As tabelas a seguir podem ajudá-lo com o planejamento da capacidade do servidor de chat persistente por meio da modelagem de como as configurações de servidor de chat persistente afetam a capacidade.
  
- Planejar capacidade para número de usuários
    
- Planejar capacidade para acesso à sala de chat
    
- Planejar a capacidade de acesso à sala de chat por convite
    
- Planejar a capacidade de desempenho
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planejar a capacidade do número de usuários para o servidor de chat persistente

Use a seguinte tabela de exemplo para determinar o número de usuários que você será capaz de suportar.
  
**Exemplo de capacidade máxima do pool do servidor de chat persistente**

|||
|:-----|:-----|
|Instâncias ativas do serviço de chat persistente  <br/> |4  <br/> |
|Instâncias do serviço de chat persistente  <br/> |8 (apenas 4, no máximo, podem estar ativos; 4 têm que estar inativos)  <br/> |
|Usuários ativos conectados  <br/> |80,000  <br/> |
|Total de usuários provisionados  <br/> |150,000  <br/> |
|Número de pontos de extremidade  <br/> |120,000  <br/> |
   
No exemplo anterior, o plano é compatível com o número máximo de usuários que o chat do servidor de chat persistente permite: quatro servidores/instâncias do serviço de chat persistente (pode ter quatro servidores passivos executando o servidor de chat persistente para alta disponibilidade e recuperação de desastres) e os usuários do 20.000 por servidor, para um total de 80.000 usuários ativos.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planejar capacidade para acesso à sala de chat

A tabela de exemplo a seguir pode ajudá-lo a planejar o gerenciamento de acesso à sala de chat em um pool de servidores de chat persistente.
  
**Gerenciando o exemplo de acesso da sala de chat**

||**Salas de chat pequenas**|**Salas de chat médias**|**Salas de chat grandes**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Tamanho das salas de chat (número de usuários conectados)  <br/> |30 por sala  <br/> |150 por sala  <br/> |16.000 por sala  <br/> ||
|Salas de chat  <br/> |32,000  <br/> |1,067  <br/> |254  <br/> |33,077  <br/> |
|% de salas que são auditórios  <br/> |1%  <br/> |1%  <br/> |50%  <br/> ||
|% de salas abertas  <br/> |3%  <br/> |3%  <br/> |50%  <br/> ||
|Salas abertas (para associação explícita)  <br/> |960  <br/> |32  <br/> |5  <br/> |997  <br/> |
|Salas não abertas (salas normais com associação explícita)  <br/> |31,040  <br/> |1.035  <br/> |5  <br/> |32,080  <br/> |
|Salas de auditório (ingresso de apresentadores adicionais)  <br/> |0  <br/> |32  <br/> |5  <br/> ||
|Salas gerenciadas pro associação direta  <br/> |50%  <br/> |10%  <br/> |0%  <br/> ||
|Salas gerenciadas por grupos de usuários  <br/> |50%  <br/> |90%  <br/> |100%  <br/> ||
|Grupos de usuários na lista de associação de cada sala de chat para salas abertas (sem especificação explícita)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Usuários na lista de associação de cada sala de chat para salas não abertas  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Grupos de usuários na lista de associação de cada sala de chat para salas não abertas  <br/> |3  <br/> |5  <br/> |254  <br/> ||
|Usuários e grupos de usuários na lista de gerentes de cada sala de chat (para salas abertas e não abertas)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Usuários e grupos de usuários na lista de apresentadores de cada sala de chat (para salas abertas e não abertas)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Entidades de associação com base em usuário em todas as salas não abertas  <br/> |465,600  <br/> |15,520  <br/> |-  <br/> ||
|Entidades de associação com base em grupo usuários em todas as salas não abertas  <br/> |46,560  <br/> |4656  <br/> |50  <br/> ||
|Entidades de usuários e grupos de usuários em todas as salas de chat de auditório  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Entidades de gerente com base em usuários e grupos de usuários em todas as listas de gerentes das salas de chat  <br/> |192,000  <br/> |6,400  <br/> |60  <br/> ||
|Usuários ativos por sala de chat  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Salas de chat por usuário  <br/> |12  <br/> |2  <br/> |2  <br/> |16  <br/> |
|Grupos de usuários na lista de associações de cada sala de chat  <br/> |254  <br/> |254  <br/> |15  <br/> ||
|Salas gerenciadas por grupos de usuários  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Entidades de participação baseadas em grupos de usuário em todas as salas de chat  <br/> |155,200  <br/> |5173  <br/> |68  <br/> ||
|Entidades de participação baseadas em usuários em todas as salas de chat  <br/> |465,600  <br/> |77,600  <br/> |72,000  <br/> ||
|Usuários e grupos de usuários no gerenciador de cada sala de chat, apresentador e listas de escopo  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Usuários e grupos de usuários em todas as listas de escopo, gerentes e apresentadores das salas de chat  <br/> |192,000  <br/> |6400  <br/> |60  <br/> ||
|Entradas de controle de acesso  <br/> |704,160  <br/> |26,768  <br/> |160  <br/> |731,088  <br/> |
|Entradas de controle de máximo acesso  <br/> ||||2,000,000  <br/> |
   
No exemplo anterior, quando você implanta os servidores de chat persistente de acordo com as diretrizes recomendadas, eles podem manipular até 80.000 usuários ativos em um pool de quatro servidores com conformidade habilitada.
  
Este exemplo mostra como salas de chat são categorizadas como pequenas (30 usuários ativos a qualquer momento), médias (150 usuários ativos) e grandes (16.000 usuários ativos). O número de salas de chat de um determinado tamanho com suporte é calculado com base no número total de:
  
- Usuários ativos no sistema
    
- Usuários ativos em salas de chat de determinado tamanho
    
- Salas de chat de um tamanho determinado onde ingressa um único usuário
    
Para cada sala de chat, a tabela de planejamento de capacidade anterior especifica o número de entradas de controle de acesso que estão associados com a sala de chat, incluindo entradas que são atribuídos diretamente para a sala de chat. Você pode controlar o acesso a salas de chat individuais usando listas de controle de acesso (ACLs). Você também pode controlar o acesso no nível de categoria. Em uma ACL, uma entrada de controle de acesso individual pode ser um grupo de usuários (por exemplo, um grupo de segurança, uma lista de distribuição) ou um único usuário. Você pode definir as entradas de controle de acesso aos membros, aos apresentadores e aos gerentes de sala de chat.
  
> [!IMPORTANT]
> No planejamento da estratégia de gerenciamento de salas de chat, tenha em mente que o número total de entradas de controle de acesso permitido é de dois milhões. Se as entradas de controle de acesso calculado excederem dois milhões, o desempenho do servidor pode degradar significativamente. Para evitar esse problema, sempre que possível, verifique se as entradas de controle de acesso são grupos de usuários em vez de usuários individuais. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planejar capacidade para acesso à sala de chat por convite

Você pode usar a tabela de planejamento de capacidade a seguir para compreender o número de convites que o servidor de chat persistente cria e armazena no banco de dados de chat persistente quando ele está configurado para enviar convites. Você gerencia convites na categoria usando a página de **configurações de categoria da sala de chat** no painel de controle do Skype for Business Server, ou usando o cmdlet do Windows PowerShell, **set-csPersistentChatCategory**. Você pode gerenciar convites em uma sala de chat (em linha com o que a categoria permite) usando a página de **Gerenciamento de salas** iniciada do cliente Skype for Business ou usando um cmdlet do Windows PowerShell, **set-csPersistentChatRoom**.
  
Os dados de exemplo na tabela a seguir pressupõem que, na página de  **configurações de sala de chat** para 50% de todas as salas de chat, a opção de  **convites** está definida como  **Sim**.
  
> [!IMPORTANT]
> Se o valor calculado para o número de convites gerado pelo servidor exceder 1 milhão, o desempenho do servidor pode degradar significativamente. Para evitar esse problema, certifique-se de minimizar o número de salas de chat que estão configuradas para enviar convites ou restringir o número de usuários que podem participar de salas de chat que foram configurados para enviar convites. 
  
**Acesso à sala de chat por amostra de convite**

||**Salas de chat pequenas**|**Salas de chat médias**|**Salas de chat grandes**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Usuários que podem acessar a sala de chat  <br/> |30 por sala  <br/> |150 por sala  <br/> |16.000 por sala  <br/> ||
|Porcentagem de salas com convites  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Salas de chat configuradas para enviar convites  <br/> |16,000  <br/> |533  <br/> |5  <br/> ||
|Usuários que podem acessar a sala de chat  <br/> |60  <br/> |225  <br/> |16,000  <br/> ||
|Convites gerados pelo servidor de chat persistente  <br/> |960,000  <br/> |120,000  <br/> |80,000  <br/> |1,160,000  <br/> |
|Número de convites máximo permitido  <br/> ||||2,000,000  <br/> |
|Modelo 1 - Iniciar com o número esperado de mensagens por sala/dia  <br/> |||||
|Taxa de chat por sala (por dia)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Taxa de chat (por segundo) em todas as salas  <br/> |55.56  <br/> |18.52  <br/> |0.03  <br/> |74  <br/> |
|Modelo 2 - Iniciar com um número de mensagens publicadas por usuário/dia  <br/> |||||
|Taxa de chat por usuário/dia  <br/> |15  <br/> |5  <br/> |0.1  <br/> |cedido  <br/> |
|Taxa de chat por sala (por dia)  <br/> |38  <br/> |375  <br/> |800  <br/> |1,213  <br/> |
|Taxa de chat (por segundo) em todas as salas  <br/> |41.67  <br/> |13.89  <br/> |0.28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planejar a capacidade de desempenho persistente do servidor de chat

A tabela a seguir descreve o modelo de usuário para o servidor de chat persistente. Ela fornece a base para requisitos de planejamento de capacidade e representa uma organização típica com 80.000 usuários simultâneos em quatro servidores.
  
**Modelo de usuário de desempenho persistente do servidor de chat**

|||
|:-----|:-----|
|Número de usuários ativos conectados  <br/> |80,000  <br/> |
|Número de instâncias de serviço do servidor de chat persistente  <br/> |4  <br/> |
|Tamanho de salas de chat pequenas  <br/> |30 usuários  <br/> |
|Tamanho médio de salas de chat  <br/> |150 usuários  <br/> |
|Tamanho grande de salas de chat  <br/> |16.000 usuários  <br/> |
|Número total de salas de chat  <br/> |33,077  <br/> |
|Número de salas de chat pequenas  <br/> |32,000  <br/> |
|Número de salas de chat médias  <br/> |1,067  <br/> |
|Número de salas de chat grandes  <br/> |254  <br/> |
|Número total de salas de chat por usuário  <br/> |16  <br/> |
|Número de salas de chat pequenas por usuário  <br/> |12  <br/> |
|Número de salas de chat médias por usuário  <br/> |2  <br/> |
|Número de salas de chat grandes por usuário  <br/> |2  <br/> |
|Número de salas com ingresso por usuário  <br/> |24  <br/> |
|Taxa de pico de associação  <br/> |10/segundo  <br/> |
|Taxa de chat total  <br/> |24/segundo  <br/> |
|Taxa de chat para pequenas salas de chat  <br/> |22.22/second  <br/> |
|Taxa de chat para salas de chat médias  <br/> |1.67/second  <br/> |
|Taxa de chat para salas de chat grandes  <br/> |~0.15/second  <br/> |
|Porcentagem de salas de chat configuradas para convites  <br/> |50%  <br/> |
|Porcentagem de participação direta em  <br/> |50%  <br/> |
|Porcentagem de membros em grupo  <br/> |50%  <br/> |
|Número médio de afiliações ancestrais nos serviços de domínio Active Directory  <br/> |100 - 200  <br/> |
|Número de contatos inscritos por usuário  <br/> |80  <br/> |
|Número médio de pontos de extremidade por usuário  <br/> |1.5  <br/> |
|Número médio de salas de chat visíveis por ponto de extremidade  <br/> |1.5  <br/> |
|Número médio de salas de chat visíveis por usuário  <br/> |2,25 (50% para uma sala e 50% para duas salas); até seis salas abertas, uma por monitor  <br/> |
|Número de participantes sondados por intervalo  <br/> |25 por sala de chat visível  <br/> |
|Duração do intervalo de sondagem  <br/> |5 minutos  <br/> |
|Número de participantes sondados por segundo  <br/> |15,000  <br/> |
|Número de alterações de presença por hora por usuário  <br/> |6  <br/> |
|Número de alterações de presença por segundo  <br/> |133.33  <br/> |
   

