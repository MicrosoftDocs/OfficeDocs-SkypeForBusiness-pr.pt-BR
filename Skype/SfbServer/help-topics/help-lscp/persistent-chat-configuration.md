---
title: Configuração de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: Sua implantação do servidor de chat persistente pode hospedar muitas salas de chat persistentes persistentes. Essas salas podem ser organizadas em um conjunto de categorias no servidor. Cada sala de chat pertence a uma categoria e herda algumas configurações dessa categoria. Essa organização cria uma estrutura útil para identificar conversas, com base no objetivo comercial, bem como facilita a administração delegada e o gerenciamento simplificado.
ms.openlocfilehash: 07c1043a67d5f1a64dbb53540fbd902341067b32
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686224"
---
# <a name="persistent-chat-configuration"></a>Configuração de Chat Persistente
 
Sua implantação do servidor de chat persistente pode hospedar muitas salas de chat persistentes persistentes. Essas salas podem ser organizadas em um conjunto de categorias no servidor. Cada sala de chat pertence a uma categoria e herda algumas configurações dessa categoria. Essa organização cria uma estrutura útil para identificar conversas, com base no objetivo comercial, bem como facilita a administração delegada e o gerenciamento simplificado.
  
> [!NOTE]
> Embora muitos dos recursos de gerenciamento das salas de chat estejam disponíveis em computadores que executam o chat persistente do usuário, os administradores de chat persistente (na função **cspersistentchatadministrator** ) devem usar os cmdlets do painel de controle ou do Shell de gerenciamento para criar ou gerenciar categorias.
  
Administradores de chat persistentes usam o painel de controle do Skype for Business Server ou cmdlets do Windows PowerShell para criar e gerenciar categorias e para criar acesso a salas de chat para os usuários de sua organização.
  
Os gerentes de sala de chat persistentes, que têm a capacidade de gerenciar uma ou mais salas de chat, podem usar o cliente para iniciar um aplicativo Web de gerenciamento de salas para criar e gerenciar salas (ou clientes podem criar soluções e fluxos de trabalho personalizados a serem invocados). Chat Persistente
  
Os administradores de chat persistente também podem usar o painel de controle ou cmdlets do Windows PowerShell para criar e gerenciar salas.
  
Os gerentes de salas de chat podem fazer alterações em todas as propriedades dessas salas, exceto alterar a sua categoria. Eles devem ter permissão para executar as seguintes ações:
  
- Desabilitar uma sala de chat
    
- Alterar o nome de uma sala de chat
    
- Alterar a descrição de uma sala de chat
    
- Alterar um tipo de sala de chat (Auditório versus Normal)
    
- Alterar a privacidade de uma sala (aberta verso fechada verso secreta)
    
- Adicionar ou remover membros
    
- Adicionar ou remover gerentes de salas de chat
    
- Adicionar ou remover um suplemento
    
- Alterar as configurações, como convites (de acordo com o que for permitido pela categoria)
    
## <a name="tasks-that-you-can-perform"></a>Tarefas que você pode executar

Você pode executar as seguintes tarefas na página **configuração de chat persistente** : configurar opções do servidor de chat persistente globalmente ou para um pool específico.
  
## <a name="to-configure-persistent-chat-options-globally"></a>Para configurar as opções de chat persistente globalmente

1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Configuração do Chat Persistente**.
    
4. Na página **configuração de chat persistente** , clique em **novo** e, em seguida, clique em **configuração do site**.
    
    > [!IMPORTANT]
    > Escolha esta opção se quiser que a configuração seja aplicada a todos os pools de servidores de chat persistentes implantados no site. Clique em **configuração de pool** se desejar que a configuração seja aplicada a um pool específico do servidor de chat persistente.
  
5. Em **selecionar um site**, selecione o site a ser configurado para a configuração de site do servidor de chat persistente.
    
6. Em **Nova Configuração de Chat Persistente**, siga este procedimento:
    
   - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do site já existe.
    
   - Em **Histórico de chat padrão**, defina o número de mensagens de chat que serão processadas para cada sala após a primeira solicitação. Por padrão, esse número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
    
     > [!IMPORTANT]
     > O servidor de chat persistente armazenará essas mensagens em cache na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache. Você sempre pode acessar o conteúdo histórico por meio da pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao conectar-se a uma sala de chat. 
  
   - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo de arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo de arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual os carregamentos de arquivo estão habilitados pela configuração de **Categoria** correspondente).
    
   - Em **Limite de atualizações do participante**, selecione o limite para atualizações de participantes. O servidor de chat persistente envia informações da lista (quem está conectado a uma sala de chat) a todos os participantes até que o número de usuários conectados atinja esse número. Por padrão, o número é 75. Esse limite indica o número máximo de participantes em uma determinada sala além da qual o servidor de chat persistente interrompe o envio de atualizações da lista para clientes conectados sobre quem está presente na sala.
    
   - (Opcional.) Na **URL de gerenciamento de salas**, selecione a URL de gerenciamento de salas. Essa é a URL para o gerenciamento personalizado de salas baseado na Web. Se você não precisar personalizar o gerenciamento de salas e simplesmente usar a configuração padrão, deixe esta opção em branco. Uma vez definida a URL, ela será aplicada como a URL interna e externa de gerenciamento de salas.
    
     Se você quiser personalizar a experiência de criação da sala e incluir seu fluxo de trabalho de negócios específico, poderá criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de desenvolvimento de software) do servidor de chat persistente, hospedá-lo em algum lugar e colocar a URL aqui. Essa URL será enviada para o cliente de modo que, quando um usuário tentar exibir ou criar uma sala, ele será direcionado para sua solução personalizada de gerenciamento de salas.
    
7. Clique em **Confirmar**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar opções de chat persistente para um pool de servidor de chat persistente específico

1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Configuração do Chat Persistente**.
    
4. Na página **Configuração do Chat Persistente**, clique em **Novo** e, em seguida, clique em **Configuração do pool**.
    
5. Em **selecionar um serviço**, selecione o serviço associado ao pool de servidores de chat persistente a ser configurado.
    
6. Em **Nova Configuração de Chat Persistente**, siga este procedimento:
    
   - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do pool do site já existe.
    
   - Em **Histórico de chat padrão**, defina o número de mensagens de chat que serão processadas para cada sala após a primeira solicitação. Por padrão, esse número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
    
     > [!IMPORTANT]
     > O servidor de chat persistente armazenará essas mensagens em cache na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache. Você sempre pode acessar o conteúdo histórico por meio da pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao conectar-se a uma sala de chat. 
  
   - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo de arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo de arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual os carregamentos de arquivo estão habilitados pela configuração de **Categoria** correspondente).
    
   - Em **Limite de atualizações do participante**, selecione o limite para atualizações de participantes. O servidor de chat persistente envia informações da lista (quem está conectado a uma sala de chat) a todos os participantes até que o número de usuários conectados atinja esse número. Por padrão, o número é 75. Esse limite indica o número máximo de participantes em uma determinada sala além da qual o servidor de chat persistente interrompe o envio de atualizações da lista para clientes conectados sobre quem está presente na sala.
    
   - (Opcional) Em **URL de gerenciamento de salas**, selecione a URL de gerenciamento de salas. Essa é a URL para uma implantação de gerenciamento de salas baseado na Web. Se você não precisar personalizar o gerenciamento de salas e simplesmente usar a configuração padrão, deixe esta opção em branco.
    
     Se você quiser personalizar a experiência de criação da sala e incluir seu fluxo de trabalho de negócios específico, poderá criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de desenvolvimento de software) do servidor de chat persistente, hospedá-lo em algum lugar e colocar a URL aqui. Essa URL será enviada para o cliente de modo que, quando um usuário tentar exibir ou criar uma sala, ele será direcionado para sua solução personalizada de gerenciamento de salas.
    
7. Clique em **Confirmar**.
    
## <a name="see-also"></a>Confira também

Para obter detalhes sobre recursos e recursos do servidor de chat persistente, consulte [planejar o servidor de chat persistente no Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [implantar o servidor de chat persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [gerenciar o servidor de chat persistente no Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

