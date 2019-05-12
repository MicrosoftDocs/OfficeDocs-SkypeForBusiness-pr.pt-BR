---
title: Planejar Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Resumo: Leia este tópico para saber como planejar o servidor de Chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: b3ca8125a69a94da3e0c707456d695c31eaf8c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910802"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planejar Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como planejar o servidor de Chat persistente no Skype for Business Server 2015.
  
Servidor de bate-papo persistente é uma função opcional que permite que vários usuários em sua organização participar de conversas de sala de chat que persistam ao longo do tempo. Embora os usuários possam se comunicar em tempo real durante uma sessão de chat, o conteúdo de cada sessão – incluindo texto, links e arquivos – é persistente, o que significa que os usuários podem visualizar e pesquisar todo o conteúdo da sessão a qualquer momento.
  
Servidor de Chat persistente pode ajudar a melhorar a comunicação dentro da sua organização por:
  
- Ampliar a visibilidade das informações e a participação por toda a organização
    
- Permitir o compartilhamento eficiente de informações 
    
- Melhorar a comunicação entre as equipes, incluindo equipes geograficamente dispersas e multifuncionais
    
- Reduzir a sobrecarga de informações
    
- Cumprir normas de conformidade por meio da implantação opcional de serviço de Conformidade de Chat Persistente

> [!NOTE] 
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Arquitetura de alto nível de Servidor de Chat Persistente

O diagrama a seguir mostra um modo de exibição de alto nível da arquitetura do servidor de Chat persistente. 
  
![Arquitetura de alto nível de servidor de bate-papo persistente](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
O Chat Persistente consiste em uma função de servidor de front-end que fornece os serviços de Chat Persistente, bem como componentes do banco de dados SQL de back-end. Tanto os componentes de front-end quanto de back-end estão incluídos em um pool dedicado de Chat Persistente. Cada computador que hospeda o servidor de Chat persistente deve ter acesso a um Skype existente para a topologia de negócios Server 2015. Neste diagrama, há um pool de servidor de Chat persistente (A), que é dependente do Skype para um Pool de servidores corporativos para roteamento de mensagens a ela.
  
Você pode implantar um ou mais pools de servidor de Chat persistente, cada um com até quatro ativo servidores de Chat persistente suportando até aos usuários simultâneos de 80 mil.
  
Skype para Business Server 2015 se comunica com o serviço de Chat persistente usando o protocolo de iniciação de sessão (SIP) para o registro e o protocolo Extensible bate-papo comunicação via SIP (XCCOS) para o bate-papo. 
  
## <a name="persistent-chat-services"></a>Serviços de Chat Persistente

O diagrama a seguir mostra os serviços de front-end do servidor de Chat persistente e como esses serviços se comunicam com os componentes de banco de dados de back-end. Os componentes de front-end incluem serviços de Chat Persistente e o serviço de Conformidade. Os componentes de back-end incluem o repositório de Chat Persistente e o repositório de conformidade de Chat Persistente.
  
![Serviços de alto nível de servidor de bate-papo persistente](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Serviço de Chat

O serviço de Chat, também chamado de serviço de Canal, é o serviço principal responsável pelo Servidor de Chat Persistente. O serviço de Chat fornece as seguintes funções:
  
- Aceita as mensagens recebidas
    
- Registra e lista os participantes em uma sala do Chat Persistente
    
- Retransmite mensagens a outros assinantes do canal
    
- Implementa lógica para gerenciamento de canal, convites para sala de bate-papo, pesquisa e notificações de novo conteúdo
    
O serviço de Chat Persistente armazena e acessa o conteúdo da sala de bate-papo e outros metadados do sistema (regras de autorização etc) utilizando o repositório de Chat Persistente. O serviço armazena arquivos que são carregados nas salas de bate-papo no repositório de arquivos de Chat Persistente.
  
### <a name="compliance-service"></a>Serviço de conformidade

Se a sua organização tiver regulamentos que exigem que a atividade de Chat Persistente seja arquivada, você pode implantar o serviço opcional de Conformidade de Chat Persistente. O serviço de Conformidade é responsável pelo arquivamento de conteúdo de chat e eventos, tais como ingressar e sair de salas, no repositório de arquivos de Conformidade de Chat Persistente. O serviço de conformidade é instalado em cada servidor de Chat persistente em um pool de Chat persistente. 
  
### <a name="web-services"></a>Serviços Web

Os serviços web de Chat persistente executar no Skype para negócios servidores Front-End. Os serviços Web dependem dos Serviços de Informações da Internet (IIS) e são implementados como componentes da Web:
  
- Os serviços Web de Chat Persistente para download e upload de arquivos são responsáveis pela publicação e recuperação de arquivos em salas de chat.
    
- Os serviços Web de Chat Persistente para gerenciamento de sala de chat são responsáveis por proporcionar aos usuários a capacidade de gerenciar suas salas de chat e criar novas salas de chat.
    
## <a name="defining-requirements-for-your-organization"></a>Definindo requisitos para sua organização

Se você decidir implantar o servidor de Chat persistente, você precisará determinar os requisitos de negócios da sua organização, então, definir a topologia, infraestrutura e os requisitos técnicos para atender às suas necessidades de negócios. Para otimizar sua implantação, você precisará responda às seguintes perguntas:
  
- Você está migrando de uma versão anterior do servidor de Chat de grupo ou uma versão anterior do servidor de Chat persistente, ou está implantando o servidor de Chat persistente pela primeira vez?
    
- Quem pode usar o Servidor de Chat Persistente? Você especifica políticas de Chat Persistente para determinar o acesso do usuário no nível global, de site ou de usuário.
    
- Quantos usuários terão que acessar o Servidor de Chat Persistente? O Servidor de Chat Persistente suporta 150.000 usuários provisionados (habilitados por política) e um máximo de 80.000 usuários simultâneos. Um único Servidor de Chat Persistente pode suportar 20.000 usuários conectados e um único pool de Servidor de Chat Persistente pode ter até 4 servidores ativos para um total de 80.000 usuários conectados simultâneos.
    
- Como você deseja controlar escopos, limites éticos e acesso? É possível definir categorias para segregar esses limites e escolher quem estará habilitado para estar nas salas que forem criadas para cada uma dessas categorias.
    
- Como você deseja controlar quem pode criar salas? Você pode definir criadores que podem criar salas. Os criadores podem designar outros membros como gerentes de sala de chat para gerenciamento contínuo das salas.
    
- Como você deseja criar salas? Servidor de Chat persistente fornece um recurso baseado na web para criar e gerenciar salas. Isso pode ser iniciado do Skype para o cliente de negócios. Você pode optar por definir uma solução de cliente que implementa a seus requisitos corporativos e fluxos de trabalho e configura o servidor de Chat persistente para direcionar os usuários à sua solução personalizada.
    
- Que tipo de suplemento você deseja provisionar? Suplementos aprimoram a experiência na sala aproveitando o painel de extensibilidade no cliente Skype for Business para fornecer contexto que seja relevante à sala. É possível escolher quais suplementos gerais podem ser mais úteis (por exemplo, o site da sua empresa, documentos de colaboração interna etc.). Os gerentes das salas de chat podem escolher um dos suplementos registrados e associá-lo às salas, se desejado. 
    
- Que tipo de requisito de alta disponibilidade e recuperação de desastre você tem? Servidor de Chat persistente suporta o espelhamento do SQL Server e SQL Server clustering para alta disponibilidade. Recuperação de desastres, Persistent Chat Server suporta até 8 servidores (4 ativas e 4 espera) em um pool alongado com o SQL Server envio de logs. 
    
- Há requisitos regulatórios? Se sua empresa estiver em um país ou região onde os dados precisam ser mantidas dentro do país, você pode precisar implantar vários pools de servidor de Chat persistente, em cada local em uma região geográfica específica. Uma sala, categoria ou suplemento não abranger pools – ele pertence a apenas um pool de servidor de Chat persistente. 
    
    > [!NOTE]
    > Ter vários pools de servidor de Chat persistente não oferecer mais escala (você ainda pode ter apenas 80.000 usuários simultâneos em todos os seus pools de servidor de Chat persistente). O principal motivo para dar suporte a vários pools de servidor de Chat persistente é para oferecer suporte a preocupações normas. 
  
## <a name="for-more-information"></a>Para obter mais informações

Para mais informações sobre como instalar e configurar o Servidor de Chat Persistente, consulte os seguintes tópicos:
  
- Para obter detalhes sobre como implantar o servidor de Chat persistente, consulte [Implantar Persistent Chat Server in Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Para obter detalhes sobre como definir as configurações na sua implantação do servidor de Chat persistente, consulte [Gerenciar Persistent Chat Server in Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
    

