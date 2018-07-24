---
title: Planejamento de capacidade para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Resumo: Leia este tópico para saber mais sobre o planejamento de capacidade do servidor de Chat persistente no Skype para Business Server 2015.'
ms.openlocfilehash: 395beed6a295a76c781aa65c654bcbf2693bbc40
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026449"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planejamento de capacidade para o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre o planejamento de capacidade do servidor de Chat persistente no Skype para Business Server 2015.
  
Servidor de bate-papo persistente pode executar chat em tempo real de vários usuário, que poderá persistir para pesquisa e recuperação futura. Ao contrário de grupo mensagens instantâneas (IM) que tenha sido salva na caixa de correio de um usuário se o histórico da conversa estiver configurado, uma sessão de servidor de Chat persistente fica mais aberta e o conteúdo é salvo em um servidor, junto com as mensagens, arquivos, URLs e outros dados que fazem parte de um conversa em andamento.
  
Planejamento de capacidade é uma parte importante do Preparando para implantar o servidor de Chat persistente. Este tópico fornece tabelas de planejamento de capacidade que você pode usar para determinar a melhor configuração para a sua implantação. Também descreve como gerenciar melhor implantações de servidor de Chat persistente que requerem oferece maior capacidade em horários de pico.
  
Antes de ler esta seção, é importante você se familiarizar com as topologias do Chat Persistente. Para obter mais informações, consulte [topologia de planejar Persistent Chat Server](topology.md).

> [!NOTE] 
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Planejamento de capacidade de servidor de Chat persistente

As tabelas a seguir podem ajudá-lo com o planejamento de capacidade do servidor de Chat persistente, modelando como várias configurações de servidor de Chat persistente afetam a capacidade.
  
- Planejar capacidade para número de usuários
    
- Planejar capacidade para acesso à sala de chat
    
- Planejar a capacidade para acesso de sala de chat por convite
    
- Planejar a capacidade de desempenho
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planejar a capacidade para o número de usuários para o servidor de Chat persistente

Use a seguinte tabela de exemplo para determinar o número de usuários que você será capaz de suportar.
  
**Exemplo de capacidade máxima de pool de servidor de Chat persistente**

|||
|:-----|:-----|
|Instâncias de serviço de Chat persistente ativas  <br/> |4  <br/> |
|Instâncias de serviço de bate-papo persistentes  <br/> |8 (apenas 4, no máximo, podem estar ativos; 4 têm que estar inativos)  <br/> |
|Usuários ativos conectados  <br/> |80.000  <br/> |
|Total de usuários provisionados  <br/> |150.000  <br/> |
|Número de pontos de extremidade  <br/> |120.000  <br/> |
   
No exemplo anterior, o plano é suportar o número máximo de usuários que permite que o servidor de Chat persistente: quatro servidores/instâncias do serviço de Chat persistente (pode ter quatro servidores mais passivo executando o servidor de Chat persistente para alta disponibilidade e recuperação de desastre) e 20.000 usuários por servidor, para um total de 80.000 usuários ativos.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planejar capacidade para acesso à sala de chat

A tabela de exemplo a seguir pode ajudá-lo a planejar o gerenciamento de acesso da sala de bate-papo em um pool de servidor de bate-papo persistente.
  
**Gerenciando o exemplo de acesso da sala de chat**

||**Salas de chat pequenas**|**Salas de chat médias**|**Salas de chat grandes**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Tamanho das salas de chat (número de usuários conectados)  <br/> |30 por sala  <br/> |150 por sala  <br/> |16.000 por sala  <br/> ||
|Salas de chat  <br/> |32.000  <br/> |1,067  <br/> |10  <br/> |33,077  <br/> |
|% de salas que são auditórios  <br/> |1%  <br/> |1%  <br/> |50%  <br/> ||
|% de salas abertas  <br/> |3%  <br/> |3%  <br/> |50%  <br/> ||
|Salas abertas (para associação explícita)  <br/> |960  <br/> |32  <br/> |5  <br/> |997  <br/> |
|Salas não abertas (salas normais com associação explícita)  <br/> |31,040  <br/> |1.035  <br/> |5  <br/> |32,080  <br/> |
|Salas de auditório (ingresso de apresentadores adicionais)  <br/> |0  <br/> |32  <br/> |5  <br/> ||
|Salas gerenciadas pro associação direta  <br/> |50%  <br/> |10%  <br/> |0%  <br/> ||
|Salas gerenciadas por grupos de usuários  <br/> |50%  <br/> |90%  <br/> |100%  <br/> ||
|Grupos de usuários na lista de associação de cada sala de chat para salas abertas (sem especificação explícita)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Usuários na lista de associação de cada sala de chat para salas não abertas  <br/> |30  <br/> |150  <br/> |16.000  <br/> ||
|Grupos de usuários na lista de associação de cada sala de chat para salas não abertas  <br/> |3  <br/> |5  <br/> |10  <br/> ||
|Usuários e grupos de usuários na lista de gerentes de cada sala de chat (para salas abertas e não abertas)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Usuários e grupos de usuários na lista de apresentadores de cada sala de chat (para salas abertas e não abertas)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Entidades de associação com base em usuário em todas as salas não abertas  <br/> |465,600  <br/> |15,520  <br/> |-  <br/> ||
|Entidades de associação com base em grupo usuários em todas as salas não abertas  <br/> |46,560  <br/> |4656  <br/> |50  <br/> ||
|Entidades de usuários e grupos de usuários em todas as salas de chat de auditório  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Entidades de gerente com base em usuários e grupos de usuários em todas as listas de gerentes das salas de chat  <br/> |192,000  <br/> |6,400  <br/> |60  <br/> ||
|Usuários ativos por sala de chat  <br/> |30  <br/> |150  <br/> |16.000  <br/> ||
|Salas de chat por usuário  <br/> |12  <br/> |2  <br/> |2  <br/> |16  <br/> |
|Grupos de usuários na lista de associação de cada sala de chat  <br/> |10  <br/> |10  <br/> |15  <br/> ||
|Salas gerenciadas por grupos de usuários  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Entidades de participação baseadas em grupos de usuário em todas as salas de chat  <br/> |155,200  <br/> |5173  <br/> |68  <br/> ||
|Entidades de participação baseadas em usuários em todas as salas de chat  <br/> |465,600  <br/> |77,600  <br/> |72.000  <br/> ||
|Usuários e grupos de usuários no gerenciador de cada sala de chat, apresentador e listas de escopo  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Usuários e grupos de usuários em todas as listas de escopo, gerentes e apresentadores das salas de chat  <br/> |192,000  <br/> |6400  <br/> |60  <br/> ||
|Entradas de controle de acesso  <br/> |704,160  <br/> |26,768  <br/> |160  <br/> |731,088  <br/> |
|Entradas de controle de máximo acesso  <br/> ||||2.000.000  <br/> |
   
No exemplo anterior, quando você implanta os servidores de Chat persistente de acordo com as diretrizes recomendadas, eles podem lidar com até 80.000 usuários ativos em um pool de quatro servidores com a conformidade ativada.
  
Este exemplo mostra como salas de chat são categorizadas como pequenas (30 usuários ativos a qualquer momento), médias (150 usuários ativos) e grandes (16.000 usuários ativos). O número de salas de chat de um determinado tamanho com suporte é calculado com base no número total de:
  
- Usuários ativos no sistema
    
- Usuários ativos em salas de chat de determinado tamanho
    
- Salas de chat de um tamanho determinado onde ingressa um único usuário
    
Para cada sala de chat, a tabela de planejamento de capacidade anterior especifica o número de entradas de controle de acesso que estão associados com a sala de chat, incluindo entradas que são atribuídos diretamente para a sala de chat. Você pode controlar o acesso a salas de chat individuais usando listas de controle de acesso (ACLs). Você também pode controlar o acesso no nível de categoria. Em uma ACL, uma entrada de controle de acesso individual pode ser um grupo de usuários (por exemplo, um grupo de segurança, uma lista de distribuição) ou um único usuário. Você pode definir as entradas de controle de acesso aos membros, aos apresentadores e aos gerentes de sala de chat.
  
> [!IMPORTANT]
> No planejamento da estratégia de gerenciamento de salas de chat, tenha em mente que o número total de entradas de controle de acesso permitido é de dois milhões. Se as entradas de controle de acesso calculado excederem dois milhões, o desempenho do servidor pode degradar significativamente. Para evitar esse problema, sempre que possível, verifique se as entradas de controle de acesso são grupos de usuários em vez de usuários individuais. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planejar capacidade para acesso à sala de chat por convite

Você pode usar a seguinte tabela de planejamento de capacidade para compreender o número de convites para que o servidor de Chat persistente cria e armazena no banco de dados de Chat persistente quando ele é configurado para enviar convites. Você gerencia convites na categoria usando a página de **configurações de categoria de sala de bate-papo** no Skype para painel de controle do Business Server, ou usando o cmdlet do Windows PowerShell, **set-csPersistentChatCategory**. Você pode gerenciar convites em uma sala de chat (alinhado com o que permite a categoria) usando a página de **Gerenciamento de sala** iniciada a partir do Skype para o cliente de negócios ou usando um cmdlet do Windows PowerShell, **set-csPersistentChatRoom**.
  
Os dados de exemplo na tabela a seguir pressupõem que, na página de  **configurações de sala de chat** para 50% de todas as salas de chat, a opção de  **convites** está definida como  **Sim**.
  
> [!IMPORTANT]
> Se o valor calculado para o número de convites gerado pelo servidor exceder 1 milhão, o desempenho do servidor pode degradar significativamente. Para evitar esse problema, certifique-se de que você minimizar o número de salas de chat que estão configurados para enviar convites ou restringir o número de usuários que podem ingressar em salas de chat que tiverem sido configuradas para enviar convites. 
  
**Acesso à sala de chat por amostra de convite**

||**Salas de chat pequenas**|**Salas de chat médias**|**Salas de chat grandes**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Usuários que podem acessar a sala de chat  <br/> |30 por sala  <br/> |150 por sala  <br/> |16.000 por sala  <br/> ||
|Porcentagem de salas com convites  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Salas de chat configuradas para enviar convites  <br/> |16.000  <br/> |533  <br/> |5  <br/> ||
|Usuários que podem acessar a sala de chat  <br/> |60  <br/> |225  <br/> |16.000  <br/> ||
|Convites gerados pelo servidor de Chat persistente  <br/> |960,000  <br/> |120.000  <br/> |80.000  <br/> |1,160,000  <br/> |
|Número de convites máximo permitido  <br/> ||||2.000.000  <br/> |
|Modelo 1 - Iniciar com o número esperado de mensagens por sala/dia  <br/> |||||
|Taxa de chat por sala (por dia)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Taxa de chat (por segundo) em todas as salas  <br/> |55.56  <br/> |18.52  <br/> |0,03  <br/> |74  <br/> |
|Modelo 2 - Iniciar com um número de mensagens publicadas por usuário/dia  <br/> |||||
|Taxa de chat por usuário/dia  <br/> |15  <br/> |5  <br/> |0,1  <br/> |20  <br/> |
|Taxa de chat por sala (por dia)  <br/> |38  <br/> |375  <br/> |800  <br/> |1,213  <br/> |
|Taxa de chat (por segundo) em todas as salas  <br/> |41,67  <br/> |13.89  <br/> |0,28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planejar a capacidade de desempenho do servidor de Chat persistente

A tabela a seguir descreve o modelo de usuário para o servidor de Chat persistente. Ela fornece a base para requisitos de planejamento de capacidade e representa uma organização típica com 80.000 usuários simultâneos em quatro servidores.
  
**Modelo de usuário de desempenho de servidor de Chat persistente**

|||
|:-----|:-----|
|Número de usuários ativos conectados  <br/> |80.000  <br/> |
|Número de instâncias de serviço do servidor de Chat persistente  <br/> |4  <br/> |
|Tamanho de salas de chat pequenas  <br/> |30 usuários  <br/> |
|Tamanho médio de salas de chat  <br/> |150 usuários  <br/> |
|Tamanho grande de salas de chat  <br/> |16.000 usuários  <br/> |
|Número total de salas de chat  <br/> |33,077  <br/> |
|Número de salas de chat pequenas  <br/> |32.000  <br/> |
|Número de salas de chat médias  <br/> |1,067  <br/> |
|Número de salas de chat grandes  <br/> |10  <br/> |
|Número total de salas de chat por usuário  <br/> |16  <br/> |
|Número de salas de chat pequenas por usuário  <br/> |12  <br/> |
|Número de salas de chat médias por usuário  <br/> |2  <br/> |
|Número de salas de chat grandes por usuário  <br/> |2  <br/> |
|Número de salas com ingresso por usuário  <br/> |24  <br/> |
|Taxa de pico de associação  <br/> |10/segundo  <br/> |
|Taxa de chat total  <br/> |24/segundo  <br/> |
|Taxa de chat para pequenas salas de chat  <br/> |22.22/segundo  <br/> |
|Taxa de chat para salas de chat médias  <br/> |1,67/segundo  <br/> |
|Taxa de chat para salas de chat grandes  <br/> |~0.15/Second  <br/> |
|Porcentagem de salas de chat configuradas para convites  <br/> |50%  <br/> |
|Porcentagem de participação direta em  <br/> |50%  <br/> |
|Porcentagem de membros em grupo  <br/> |50%  <br/> |
|Número médio de afiliações ancestrais no Active Directory Domain Services  <br/> |100 - 200  <br/> |
|Número de contatos inscritos por usuário  <br/> |80  <br/> |
|Número médio de pontos de extremidade por usuário  <br/> |1,5  <br/> |
|Número médio de salas de chat visíveis por ponto de extremidade  <br/> |1,5  <br/> |
|Número médio de salas de chat visíveis por usuário  <br/> |2,25 (50% para uma sala e 50% para duas salas); até seis salas abertas, uma por monitor  <br/> |
|Número de participantes sondados por intervalo  <br/> |25 por sala de chat visível  <br/> |
|Duração do intervalo de sondagem  <br/> |5 minutos  <br/> |
|Número de participantes sondados por segundo  <br/> |15.000  <br/> |
|Número de alterações de presença por hora por usuário  <br/> |6  <br/> |
|Número de alterações de presença por segundo  <br/> |133.33  <br/> |
   

