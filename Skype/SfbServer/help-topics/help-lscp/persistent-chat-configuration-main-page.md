---
title: Página Principal da Configuração de Chat Persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: Sua implantação do servidor de Chat persistente pode hospedar várias salas de Chat persistente simultâneas. Essas salas podem ser organizadas em um conjunto de categorias no servidor. Cada sala de chat pertence a uma categoria e herda algumas configurações dessa categoria. Essa organização cria uma estrutura útil para identificar conversas, com base no objetivo comercial, bem como facilita a administração delegada e o gerenciamento simplificado.
ms.openlocfilehash: a1995f5d6049bc861e1aa79a3932d734d4002026
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879101"
---
# <a name="persistent-chat-configuration-main-page"></a>Página Principal da Configuração de Chat Persistente
 
Sua implantação do servidor de Chat persistente pode hospedar várias salas de Chat persistente simultâneas. Essas salas podem ser organizadas em um conjunto de categorias no servidor. Cada sala de chat pertence a uma categoria e herda algumas configurações dessa categoria. Essa organização cria uma estrutura útil para identificar conversas, com base no objetivo comercial, bem como facilita a administração delegada e o gerenciamento simplificado.
  
> [!NOTE]
> Apesar de muitos dos recursos de gerenciamento de salas de chat estarem disponíveis em computadores que executam o bate-papo persistente para o usuário, os administradores de bate-papo persistente (em função **cspersistentchatadministrator** ) deve usar os cmdlets do shell de gerenciamento ou do painel de controle para criar ou gerenciar categorias.
  
Administradores de bate-papo persistente use Skype para painel de controle do Business Server ou o Windows PowerShell cmdlets criar e gerenciar categorias e acesso de design para salas de chat para os usuários em suas organizações.
  
Gerentes de sala de Chat persistente, que têm a capacidade de gerenciar um ou mais salas de bate-papo, podem usar o cliente para iniciar um aplicativo Web para criar e gerenciar salas de gerenciamento de sala (ou os clientes podem criar soluções personalizadas e fluxos de trabalho a ser chamado). 
  
Os gerentes de salas de chat podem fazer alterações em todas as propriedades dessas salas, exceto alterar a sua categoria. Eles devem ter permissão para executar as seguintes ações:
  
- Desabilitar uma sala de chat
    
- Alterar o nome de uma sala de chat
    
- Alterar a descrição de uma sala de chat
    
- Alterar um tipo de sala de chat (Auditório versus Normal)
    
- Alterar a privacidade de uma sala (aberta verso fechada verso secreta)
    
- Adicionar ou remover membros
    
- Adicionar ou remover gerentes de salas de chat
    
- Adicionar ou remover um suplemento
    
- Alterar configurações como convites (de acordo com o que é permitido pela categoria)
    
## <a name="tasks-that-you-can-perform"></a>Tarefas que você pode executar

Você pode executar as seguintes tarefas na página **Configuração de Chat persistente** : configurar opções de servidor de Chat persistente globalmente ou para um pool específico
  
## <a name="to-configure-persistent-chat-options-globally"></a>Para configurar as opções de Chat persistente globalmente

1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Configuração do Chat Persistente**.
    
4. Na página **Configuração de Chat persistente** , clique em **novo** e clique em **configuração de Site**.
    
    > [!IMPORTANT]
    > Escolha esta opção se desejar que a configuração seja aplicada a todos os pools de servidor de Chat persistente implantados no site. Se desejar que a configuração a ser aplicado a um pool do servidor de Chat persistente específico, clique em **Configuração de Pool** .
  
5. Em **Selecionar um Site**, selecione o site a ser configurado para a configuração de site do servidor de Chat persistente.
    
6. Em **Nova Configuração de Chat Persistente**, siga este procedimento:
    
   - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do site já existe.
    
   - Em **Histórico de chat padrão**, defina o número de mensagens de chat que serão processadas para cada sala após a primeira solicitação. Por padrão, esse número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
    
     > [!IMPORTANT]
     > Servidor de Chat persistente irá armazenar em cache essas mensagens na memória, portanto, se você aumentar esse número, mais mensagens serão armazenada na cache. Você sempre pode acessar conteúdo histórico pela pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao se conectar a uma sala de bate-papo. 
  
   - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo de arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo de arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual os carregamentos de arquivo estão habilitados pela configuração de **Categoria** correspondente).
    
   - Em **Limite de atualizações do participante**, selecione o limite para atualizações de participantes. Persistent Chat Server envia informações de lista de participação (que estão conectadas a uma sala de bate-papo) para todos os participantes, até que o número de usuários conectados atinge esse número. Por padrão, o número é 75. Esse limite indica o número máximo de participantes em uma determinada sala além da qual servidor de Chat persistente interrompe o envio de atualizações da lista de participação para os clientes conectados sobre quem está presente na sala.
    
   - (Opcional). Na **URL de gerenciamento de sala**, selecione a URL de gerenciamento de sala. Essa é a URL para o gerenciamento personalizado de salas baseado na Web. Se você não precisa personalizar o gerenciamento de sala e é simplesmente usar a configuração padrão, deixe essa opção em branco. Uma vez definida a URL, ela será aplicada como a URL interna e externa de gerenciamento de salas.
    
     Se desejar personalizar a sua experiência de criação de sala e incluir o fluxo de trabalho de negócios específicos, você pode criar uma solução de gerenciamento de sala personalizado usando o Persistent Chat Server Software Development Kit (SDK), hospedá-lo em algum lugar e insira a URL aqui. Essa URL será enviada para o cliente de modo que, quando um usuário tentar exibir ou criar uma sala, ele será direcionado para sua solução personalizada de gerenciamento de salas.
    
7. Clique em **Confirmar**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar as opções de Chat persistente para um pool específico do servidor de Chat persistente

1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do servidor de negócios, ou abra uma janela de navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Configuração do Chat Persistente**.
    
4. Na página **Configuração do Chat Persistente**, clique em **Novo** e, em seguida, clique em **Configuração do pool**.
    
5. Em **Selecionar um serviço**, selecione o serviço associado ao pool do servidor de Chat persistente a ser configurado.
    
6. Em **Nova Configuração de Chat Persistente**, siga este procedimento:
    
   - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do pool do site já existe.
    
   - Em **Histórico de chat padrão**, defina o número de mensagens de chat que serão processadas para cada sala após a primeira solicitação. Por padrão, esse número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
    
     > [!IMPORTANT]
     > Servidor de Chat persistente irá armazenar em cache essas mensagens na memória, portanto, se você aumentar esse número, mais mensagens serão armazenada na cache. Você sempre pode acessar conteúdo histórico pela pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao se conectar a uma sala de bate-papo. 
  
   - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo de arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo de arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual os carregamentos de arquivo estão habilitados pela configuração de **Categoria** correspondente).
    
   - Em **Limite de atualizações do participante**, selecione o limite para atualizações de participantes. Persistent Chat Server envia informações de lista de participação (que estão conectadas a uma sala de bate-papo) para todos os participantes, até que o número de usuários conectados atinge esse número. Por padrão, o número é 75. Esse limite indica o número máximo de participantes em uma determinada sala além da qual servidor de Chat persistente interrompe o envio de atualizações da lista de participação para os clientes conectados sobre quem está presente na sala.
    
   - Em **URL de gerenciamento de salas**, selecione a URL de gerenciamento de salas. Essa é a URL para uma implantação de gerenciamento de salas baseado na Web. Se você não precisa personalizar o gerenciamento de sala e é simplesmente usar a configuração padrão, deixe essa opção em branco.
    
     Se desejar personalizar a sua experiência de criação de sala e incluir o fluxo de trabalho de negócios específicos, você pode criar uma solução de gerenciamento de sala personalizado usando o Persistent Chat Server Software Development Kit (SDK), hospedá-lo em algum lugar e insira a URL aqui. Essa URL será enviada para o cliente de modo que, quando um usuário tentar exibir ou criar uma sala, ele será direcionado para sua solução personalizada de gerenciamento de salas.
    
7. Clique em **Confirmar**.
    
## <a name="see-also"></a>Consulte Também

Para obter detalhes sobre os recursos de servidor de Chat persistente e recursos, consulte [Plan for Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server na Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Gerenciar o servidor de Chat persistente no Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

