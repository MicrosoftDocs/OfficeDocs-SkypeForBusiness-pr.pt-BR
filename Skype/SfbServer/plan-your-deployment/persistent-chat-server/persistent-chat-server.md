---
title: Plano para Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Resumo: Leia este tópico para saber como planejar o Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 9195c149744b9aab9927f0b2a6e490442cff6573
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813661"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Plano para Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como planejar o Servidor de Chat Persistente no Skype for Business Server 2015.
  
O Servidor de Chat Persistente é uma função opcional que permite que vários usuários em sua organização participem de conversas de sala de chat que persistem ao longo do tempo. Embora os usuários possam se comunicar em tempo real durante uma sessão de chat, o conteúdo de cada sessão , incluindo texto, links e arquivos, é persistente, o que significa que os usuários podem exibir e pesquisar todo o conteúdo da sessão a qualquer momento.
  
O Servidor de Chat Persistente pode ajudar a melhorar a comunicação em sua organização:
  
- Ampliar a conscientização e a participação das informações em toda a organização
    
- Habilitando o compartilhamento eficiente de informações 
    
- Melhorar a comunicação entre equipes, incluindo equipes geograficamente dispersos e multifuncionais
    
- Reduzindo a sobrecarga de informações
    
- Seguindo as regulamentações de conformidade, opcionalmente implantando o serviço de Conformidade de Chat Persistente

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Arquitetura de alto nível do Servidor de Chat Persistente

O diagrama a seguir mostra uma visão de alto nível da arquitetura do Servidor de Chat Persistente. 
  
![Arquitetura de alto nível de servidor de bate-papo persistente](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
O Chat Persistente consiste em uma função de servidor front-end que fornece os serviços de Chat Persistente, bem como um componente de banco de dados SQL de back-end. Os componentes front-end e back-end estão incluídos em um pool de Chat Persistente dedicado. Cada computador que hospeda o Servidor de Chat Persistente deve ter acesso a uma topologia existente do Skype for Business Server 2015. Neste diagrama, há um pool de Servidor de Chat Persistente (A), que depende do Pool A do Skype for Business Server para roteamento de mensagens para ele.
  
Você pode implantar um ou mais pools de Servidor de Chat Persistente, cada um com até quatro Servidores de Chat Persistente ativos que suportam até 80 mil usuários simultâneos.
  
O Skype for Business Server 2015 se comunica com o serviço de Chat Persistente usando o PROTOCOLO SIP para registro e o protocolo XCCOS para chat. 
  
## <a name="persistent-chat-services"></a>Serviços de Chat Persistente

O diagrama a seguir mostra os serviços front-end do Servidor de Chat Persistente e como esses serviços se comunicam com os componentes do banco de dados back-end. Os componentes de front-end incluem os serviços de Chat Persistente e o serviço de Conformidade. Os componentes de back-end incluem o armazenamento de Chat Persistente e o armazenamento de conformidade de Chat Persistente.
  
![Serviços de alto nível de servidor de bate-papo persistente](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Serviço de chat

O serviço de Chat, também chamado de serviço de Canal, é o serviço principal responsável pelo Servidor de Chat Persistente. O serviço de Chat fornece as seguintes funções:
  
- Aceita as mensagens recebidas
    
- Registra e lista participantes online em uma sala de Chat Persistente
    
- Retransmite mensagens a outros assinantes do canal
    
- Implementa lógica para gerenciamento de canal, convites de sala de chat, pesquisa e novas notificações de conteúdo
    
O serviço de Chat Persistente armazena e acessa o conteúdo da sala de chat e outros metadados do sistema (regras de autorização e assim por diante) usando o armazenamento de Chat Persistente. O serviço armazena arquivos que são carregados em salas de chat no armazenamento de arquivos de Chat Persistente.
  
### <a name="compliance-service"></a>Serviço de conformidade

Se sua organização tiver regulamentos que exigem que a atividade de Chat Persistente seja arquivada, você poderá implantar o serviço opcional de Conformidade de Chat Persistente. O serviço de Conformidade é responsável pelo arquivamento de conteúdo e eventos de chat, como ingressar e sair de salas, para o armazenamento de arquivos de Conformidade de Chat Persistente. O serviço de Conformidade é instalado em cada Servidor de Chat Persistente em um pool de Chat Persistente. 
  
### <a name="web-services"></a>Serviços da Web

Os serviços Web de Chat Persistente são executados nos Servidores front-end do Skype for Business. Os serviços Web dependem dos Serviços de Informações da Internet (IIS) e são implementados como componentes da Web:
  
- Os serviços Web de Chat Persistente para upload e download de arquivos são responsáveis por postar e recuperar arquivos de salas de chat.
    
- Os serviços Web de Chat Persistente para gerenciamento de sala de chat são responsáveis por fornecer aos usuários a capacidade de gerenciar suas salas de chat e criar novas salas de chat.
    
## <a name="defining-requirements-for-your-organization"></a>Definindo requisitos para sua organização

Se você decidir implantar o Servidor de Chat Persistente, precisará determinar os requisitos de negócios da sua organização e, em seguida, definir a topologia, a infraestrutura e os requisitos técnicos para dar suporte às suas necessidades de negócios. Para otimizar sua implantação, você precisará responder às seguintes perguntas:
  
- Você está migrando de uma versão anterior do Servidor de Chat de Grupo ou de uma versão anterior do Servidor de Chat Persistente ou está implantando o Servidor de Chat Persistente pela primeira vez?
    
- Quem pode usar o Servidor de Chat Persistente? Você especifica políticas de Chat Persistente para determinar o acesso do usuário no nível global, de site ou de usuário.
    
- Quantos usuários exigirão acesso ao Servidor de Chat Persistente? O Servidor de Chat Persistente suporta 150.000 usuários provisionados (habilitados por política) e um máximo de 80.000 usuários simultâneos. Um único Servidor de Chat Persistente pode suportar 20.000 usuários conectados, e um único pool de Servidor de Chat Persistente pode ter até 4 servidores ativos para um total de 80.000 usuários conectados simultaneamente.
    
- Como você deseja controlar escopos, limites éticos e acesso? Você pode definir categorias para segregar esses limites e escolher quem tem permissão para estar em salas criadas em cada uma dessas categorias.
    
- Como você deseja controlar quem pode criar salas? Você pode definir criadores que podem criar salas. Os criadores podem atribuir outros membros como gerentes de sala de chat para gerenciamento contínuo das salas.
    
- Como você deseja criar salas? O Servidor de Chat Persistente fornece um recurso baseado na Web para criar e gerenciar salas. Isso pode ser lançado do cliente Skype for Business. Você pode optar por definir uma solução de cliente que implemente seus requisitos de negócios e fluxos de trabalho e configure o Servidor de Chat Persistente para direcionar os usuários para sua solução personalizada.
    
- Que tipo de suplementos você deseja provisionar? Os complementos aprimoram a experiência na sala aproveitando o painel de extensibilidade no cliente Skype for Business para fornecer contexto relevante para a sala. É possível escolher quais suplementos gerais podem ser mais úteis (por exemplo, o site da sua empresam documentos de colaboração interna e etc.). Os gerentes das salas de chat podem escolher um dos suplementos registrados e associá-lo às salas, se desejado. 
    
- Quais tipos de requisitos de alta disponibilidade e recuperação de desastres você tem? O Servidor de Chat Persistente dá suporte ao espelhamento do SQL Server e clustering do SQL Server para alta disponibilidade. Para recuperação de desastres, o Servidor de Chat Persistente suporta até 8 servidores (4 ativos e 4 em espera) em um pool estendido com envio de log do SQL Server. 
    
- Há requisitos da regulamentação? Se sua empresa estiver em um país ou região onde os dados precisam ser mantidos dentro do país, talvez seja necessário implantar vários pools de Servidor de Chat Persistente, cada um local para uma geografia específica. Uma sala, categoria ou um complemento não abrange pools – ele pertence a apenas um pool de Servidor de Chat Persistente. 
    
    > [!NOTE]
    > Ter vários pools de Servidor de Chat Persistente não lhe dá mais escala (você ainda pode ter apenas 80.000 usuários simultâneos em todos os seus pools de Servidor de Chat Persistente). O principal motivo para dar suporte a vários pools de Servidor de Chat Persistente é o suporte a preocupações regulatórias. 
  
## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre como instalar e configurar o Servidor de Chat Persistente, consulte os seguintes tópicos:
  
- Para obter detalhes sobre como implantar o Servidor de Chat Persistente, consulte [Deploy Persistent Chat Server in Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md) 
    
- Para obter detalhes sobre como definir configurações em sua implantação de Servidor de Chat Persistente, consulte Gerenciar Servidor de Chat Persistente no [Skype for Business Server 2015.](../../manage/persistent-chat/persistent-chat.md)
    

