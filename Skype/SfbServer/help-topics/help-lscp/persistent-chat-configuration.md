---
title: Configuração de Chat Persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: Sua implantação de Servidor de Chat Persistente pode hospedar muitas salas de Chat Persistente simultâneas. As salas de chat podem ser organizadas em um conjunto de categorias no servidor. Cada sala de chat pertence a uma categoria, e herda algumas configurações dessa categoria. Essa organização cria uma estrutura útil para identificar conversas, com base em suas finalidades de negócio e facilita a administração delegada e o gerenciamento simplificado.
ms.openlocfilehash: ca059cd739093840028a6e9b952e12566ccfa5c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829391"
---
# <a name="persistent-chat-configuration"></a>Configuração de Chat Persistente
 
Sua implantação de Servidor de Chat Persistente pode hospedar muitas salas de Chat Persistente simultâneas. As salas de chat podem ser organizadas em um conjunto de categorias no servidor. Cada sala de chat pertence a uma categoria, e herda algumas configurações dessa categoria. Essa organização cria uma estrutura útil para identificar conversas, com base em suas finalidades de negócio e facilita a administração delegada e o gerenciamento simplificado.
  
> [!NOTE]
> Embora muitos dos recursos de gerenciamento de salas de chat estão disponíveis em computadores que executam o Chat Persistente para o usuário, os Administradores de Chat Persistente (na função **cspersistentchatadministrator)** devem usar o painel de controle ou os cmdlets do shell de gerenciamento para criar ou gerenciar categorias.
  
Os Administradores de Chat Persistente usam o Painel de Controle do Skype for Business Server ou cmdlets do Windows PowerShell para criar e gerenciar categorias e para projetar o acesso a salas de chat para os usuários em sua organização.
  
Os gerentes de sala de Chat Persistente, que têm a capacidade de gerenciar uma ou mais salas de chat, podem usar o cliente para iniciar um aplicativo Web de gerenciamento de salas para criar e gerenciar salas (ou os clientes podem criar soluções personalizadas e fluxos de trabalho a serem invocados). Chat persistente
  
Os administradores de Chat Persistente também podem usar o painel de controle ou cmdlets do Windows PowerShell para criar e gerenciar salas.
  
Os gerentes de sala de chat podem fazer alterações em todas as propriedades de sala de chat, exceto alterar a categoria da sala. Não é possível impedi-los de executar as seguintes ações:
  
- Desabilitar uma sala de chat
    
- Alterar o nome de uma sala de chat
    
- Alterar a descrição de uma sala de chat
    
- Alterar um tipo de sala de chat (Auditório versus Normal)
    
- Alterar a privacidade de uma sala (aberta versus fechada versus segredo)
    
- Adicionar ou remover membros
    
- Adicionar ou remover gerentes de sala de chat
    
- Adicionar ou remover um suplemento
    
- Alterar configurações como convites (de acordo com o que é permitido pela categoria)
    
## <a name="tasks-that-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página Configuração de **Chat** Persistente: configurar opções de Servidor de Chat Persistente globalmente ou para um pool específico.
  
## <a name="to-configure-persistent-chat-options-globally"></a>Para configurar as opções de Chat Persistente globalmente

1. A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.
    
2. No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Configuração de Chat Persistente**.
    
4. Na página **Configuração de Chat Persistente,** clique em **Novo e em** **Configuração de Site.**
    
    > [!IMPORTANT]
    > Escolha essa opção se quiser que a configuração seja aplicada a todos os pools de Servidor de Chat Persistente implantados no site. Clique **em Configuração** de Pool se quiser que a configuração seja aplicada a um pool de Servidor de Chat Persistente específico.
  
5. Em **Selecionar um Site,** selecione o site a ser configurado para a configuração do site do Servidor de Chat Persistente.
    
6. Em **Nova Configuração de Chat Persistente**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do site já existe.
    
   - Em **Histórico de chat padrão**, defina o número de mensagens do chat que serão processadas para cada sala na primeira solicitação. Por padrão, o número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
    
     > [!IMPORTANT]
     > O Servidor de Chat Persistente armazenará essas mensagens em cache na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache. Sempre é possível acessar conteúdo histórico por meio da pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao se conectar a uma sala de chat. 
  
   - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo do arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo para um arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual o carregamento de arquivos é habilitado por sua configuração correspondente de **Categoria**).
    
   - Em **Limite de atualização de participantes**, selecione o limite de atualizações de participantes. O Servidor de Chat Persistente envia informações da lista de participação (que está conectado a uma sala de chat) para todos os participantes até que o número de usuários conectados atinja esse número. Por padrão, o número é 75. Esse limite indica o número máximo de participantes em uma determinada sala além da qual o Servidor de Chat Persistente para de enviar atualizações de lista para clientes conectados sobre quem está presente na sala.
    
   - (Opcional.) Na **URL de gerenciamento de sala,** selecione a URL de gerenciamento de sala. Essa é a URL para um gerenciamento de sala personalizada baseada na Web. Se você não precisar personalizar o gerenciamento de sala e simplesmente usar a configuração padrão, deixe essa opção em branco. Após a URL ser definida, ela é aplicada como URL de gerenciamento de sala interna e externa.
    
     Se quiser personalizar sua experiência de criação de sala e incluir seu fluxo de trabalho comercial específico, você pode criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de Desenvolvimento de Software de Servidor de Chat Persistente), hospedá-lo em algum lugar e colocar a URL aqui. Essa URL é enviada para o cliente de modo que quando um usuário tenta exibir ou criar uma sala, ele ou ela é direcionado à sua solução de gerenciamento de sala personalizada.
    
7. Clique em **Confirmar**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar opções de Chat Persistente para um pool de Servidor de Chat Persistente específico

1. A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.
    
2. No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Configuração de Chat Persistente**.
    
4. Na página **Configuração de Chat Persistente**, clique em **Novo** e clique em **Configuração de pool**.
    
5. Em **Selecionar um Serviço,** selecione o serviço associado ao pool de Servidor de Chat Persistente a ser configurado.
    
6. Em **Nova Configuração de Chat Persistente**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do pool de sites já existe.
    
   - Em **Histórico de chat padrão**, defina o número de mensagens do chat que serão processadas para cada sala na primeira solicitação. Por padrão, o número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
    
     > [!IMPORTANT]
     > O Servidor de Chat Persistente armazenará essas mensagens em cache na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache. Sempre é possível acessar conteúdo histórico por meio da pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao se conectar a uma sala de chat. 
  
   - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo do arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo para um arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual o carregamento de arquivos é habilitado por sua configuração correspondente de **Categoria**).
    
   - Em **Limite de atualização de participantes**, selecione o limite de atualizações de participantes. O Servidor de Chat Persistente envia informações da lista de participação (que está conectado a uma sala de chat) para todos os participantes até que o número de usuários conectados atinja esse número. Por padrão, o número é 75. Esse limite indica o número máximo de participantes em uma determinada sala além da qual o Servidor de Chat Persistente para de enviar atualizações de lista para clientes conectados sobre quem está presente na sala.
    
   - (Opcional) Em **URL de Gerenciamento da Sala**, selecione a URL de gerenciamento de sala. Essa é a URL para uma implantação de gerenciamento de sala baseada na Web. Se você não precisar personalizar o gerenciamento de sala e simplesmente usar a configuração padrão, deixe essa opção em branco.
    
     Se quiser personalizar sua experiência de criação de sala e incluir seu fluxo de trabalho comercial específico, você pode criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de Desenvolvimento de Software de Servidor de Chat Persistente), hospedá-lo em algum lugar e colocar a URL aqui. Essa URL é enviada para o cliente de modo que quando um usuário tenta exibir/criar uma sala, ele ou ela é direcionado à sua solução de gerenciamento de sala personalizada.
    
7. Clique em **Confirmar**.
    
## <a name="see-also"></a>Confira também

Para obter detalhes sobre recursos e capacidades do Servidor de Chat Persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

