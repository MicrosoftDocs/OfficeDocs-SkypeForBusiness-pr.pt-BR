---
title: Planejar o Servidor de Chat Persistente no Skype for Business Server 2015
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
ms.localizationpriority: medium
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Resumo: leia este tópico para saber como planejar o Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: cb584fc1b618794d9956c2d91c004b8ecc008aa0
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731090"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planejar o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como planejar o Servidor de Chat Persistente no Skype for Business Server 2015.
  
O Servidor de Chat Persistente é uma função opcional que permite que vários usuários em sua organização participem de conversas de sala de chat que persistem ao longo do tempo. Embora os usuários possam se comunicar em tempo real durante uma sessão de chat, o conteúdo de cada sessão, incluindo texto, links e arquivos, é persistente, o que significa que os usuários podem exibir e pesquisar todo o conteúdo da sessão a qualquer momento.
  
O Servidor de Chat Persistente pode ajudar a melhorar a comunicação dentro da sua organização:
  
- Ampliando a conscientização e a participação de informações em toda a organização
    
- Habilitando o compartilhamento eficiente de informações 
    
- Melhorar a comunicação entre equipes, incluindo equipes geograficamente dispersos e entrefuncionais
    
- Reduzindo a sobrecarga de informações
    
- Seguindo os regulamentos de conformidade, opcionalmente implantando o serviço de Conformidade de Chat Persistente

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Arquitetura de alto nível do Servidor de Chat Persistente

O diagrama a seguir mostra uma exibição de alto nível da arquitetura do Servidor de Chat Persistente. 
  
![Arquitetura do High-Level de Chat Persistente.](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
O Chat Persistente consiste em uma função de servidor front-end que fornece os serviços de Chat Persistente, bem como um componente de banco de dados SQL back-end. Os componentes front-end e back-end estão incluídos em um pool de Chat Persistente dedicado. Cada computador que hospeda o Servidor de Chat Persistente deve ter acesso a uma topologia Skype for Business Server 2015 existente. Neste diagrama, há um pool de Servidor de Chat Persistente (A), que depende Skype for Business Server Pool A para rotear mensagens para ele.
  
Você pode implantar um ou mais pools de Servidor de Chat Persistente, cada um com até quatro Servidores de Chat Persistente ativos que suportam até 80.000 usuários simultâneos.
  
Skype for Business Server 2015 se comunica com o serviço de Chat Persistente usando o Protocolo de Iniciação de Sessão (SIP) para registro e o protocolo XCCOS (Extensible Chat Communication Over SIP) para chat. 
  
## <a name="persistent-chat-services"></a>Serviços de Chat Persistente

O diagrama a seguir mostra os serviços front-end do Servidor de Chat Persistente e como esses serviços se comunicam com os componentes do banco de dados back-end. Os componentes front-end incluem os serviços de Chat Persistente e o serviço de Conformidade. Os componentes back-end incluem o armazenamento de Chat Persistente e o armazenamento de conformidade de Chat Persistente.
  
![Serviços de Servidor de Chat Persistente High-Level Chat.](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Serviço de chat

O serviço de Chat, também chamado de serviço canal, é o principal serviço responsável pelo Servidor de Chat Persistente. O serviço chat fornece as seguintes funções:
  
- Aceita as mensagens recebidas
    
- Registra e lista participantes online em uma sala de Chat Persistente
    
- Retransmite mensagens a outros assinantes do canal
    
- Implementa lógica para gerenciamento de canal, convites de sala de chat, pesquisa e novas notificações de conteúdo
    
O serviço de Chat Persistente armazena e acessa o conteúdo da sala de chat e outros metadados do sistema (regras de autorização e assim por diante) usando o armazenamento de Chat Persistente. O serviço armazena arquivos carregados em salas de chat no armazenamento de arquivos de Chat Persistente.
  
### <a name="compliance-service"></a>Serviço de conformidade

Se sua organização tiver regulamentos que exigem que a atividade de Chat Persistente seja arquivada, você poderá implantar o serviço opcional de Conformidade de Chat Persistente. O serviço de Conformidade é responsável pelo arquivamento de conteúdos e eventos de chat, como ingressar e sair de salas, para o armazenamento de arquivos de Conformidade de Chat Persistente. O serviço de Conformidade é instalado em cada Servidor de Chat Persistente em um pool de Chat Persistente. 
  
### <a name="web-services"></a>Serviços da Web

Os serviços Web de Chat Persistente são executados nos servidores Skype for Business front-end. Os serviços Web dependem do Serviços de Informações da Internet (IIS) e são implementados como componentes da Web:
  
- Os serviços web de Chat Persistente para carregamento e download de arquivos são responsáveis pela postagem e recuperação de arquivos das salas de chat.
    
- Os serviços Web de Chat Persistente para gerenciamento de sala de chat são responsáveis por fornecer aos usuários a capacidade de gerenciar suas salas de chat e criar novas salas de chat.
    
## <a name="defining-requirements-for-your-organization"></a>Definindo requisitos para sua organização

Se você decidir implantar o Servidor de Chat Persistente, precisará determinar os requisitos de negócios da sua organização e definir a topologia, a infraestrutura e os requisitos técnicos para dar suporte às suas necessidades comerciais. Para otimizar sua implantação, você precisará responder às seguintes perguntas:
  
- Você está migrando de uma versão anterior do Servidor de Chat de Grupo ou de uma versão anterior do Servidor de Chat Persistente ou está implantando o Servidor de Chat Persistente pela primeira vez?
    
- Who pode usar o Servidor de Chat Persistente? Você especifica políticas de Chat Persistente para determinar o acesso do usuário no nível global, do site ou do usuário.
    
- Quantos usuários exigirão acesso ao Servidor de Chat Persistente? O Servidor de Chat Persistente dá suporte a 150.000 usuários provisionados (habilitados por política) e no máximo 80.000 usuários simultâneos. Um único Servidor de Chat Persistente pode dar suporte a 20.000 usuários conectados, e um único pool de Servidor de Chat Persistente pode ter até 4 servidores ativos para um total de 80.000 usuários conectados simultaneamente.
    
- Como você deseja controlar escopos, limites éticos e acesso? Você pode definir categorias para segregar esses limites e escolher quem tem permissão para estar em salas criadas em cada uma dessas categorias.
    
- Como você deseja controlar quem pode criar salas? Você pode definir criadores que podem criar salas. Os criadores podem atribuir outros membros como gerentes de sala de chat para o gerenciamento contínuo das salas.
    
- Como você deseja criar salas? O Servidor de Chat Persistente fornece um recurso baseado na Web para criar e gerenciar salas. Isso pode ser lançado a partir do Skype for Business cliente. Você pode optar por definir uma solução de cliente que implemente seus requisitos de negócios e fluxos de trabalho e configure o Servidor de Chat Persistente para direcionar os usuários para sua solução personalizada.
    
- Que tipo de suplementos você deseja provisionar? Os complementos aprimoram a experiência na sala aproveitando o painel de extensibilidade no cliente Skype for Business para fornecer um contexto relevante para a sala. É possível escolher quais suplementos gerais podem ser mais úteis (por exemplo, o site da sua empresam documentos de colaboração interna e etc.). Os gerentes das salas de chat podem escolher um dos suplementos registrados e associá-lo às salas, se desejado. 
    
- Quais tipos de requisitos de alta disponibilidade e recuperação de desastres você tem? O Servidor de Chat Persistente dá suporte SQL Server espelhamento e SQL Server clustering para alta disponibilidade. Para recuperação de desastres, o Servidor de Chat Persistente oferece suporte a até 8 servidores (4 ativos e 4 em espera) em um pool estendido com SQL Server envio de log. 
    
- Há requisitos da regulamentação? Se sua empresa estiver em um país ou região onde os dados precisem ser mantidos no país, talvez seja necessário implantar vários pools de Servidor de Chat Persistente, cada local para uma geografia específica. Uma sala, categoria ou um complemento não abrange pools, ele pertence a apenas um pool de Servidor de Chat Persistente. 
    
    > [!NOTE]
    > Ter vários pools de Servidor de Chat Persistente não dá mais escala (você ainda pode ter apenas 80.000 usuários simultâneos em todos os pools do Servidor de Chat Persistente). O principal motivo para dar suporte a vários pools de Servidores de Chat Persistente é dar suporte a preocupações regulatórias. 
  
## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre como instalar e configurar o Servidor de Chat Persistente, consulte os seguintes tópicos:
  
- Para obter detalhes sobre como implantar o Servidor de Chat Persistente, consulte [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Para obter detalhes sobre como configurar configurações em sua implantação do Servidor de Chat Persistente, consulte [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
    

