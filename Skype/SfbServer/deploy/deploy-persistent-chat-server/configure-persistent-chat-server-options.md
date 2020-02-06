---
title: Configurar opções do Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Resumo: saiba como configurar opções de servidor de chat persistente no nível global, de site ou de pool no Skype for Business Server 2015.'
ms.openlocfilehash: c842d0c0790f7aad18dda6f3f9cabe5382eb4f33
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793559"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurar opções do Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como configurar opções de servidor de chat persistente no nível global, de site ou de pool no Skype for Business Server 2015.
  
Você pode especificar várias opções para um servidor de chat persistente que podem ser aplicadas globalmente, a todos os pools dentro de um site ou a um pool específico dentro de um site. As opções do Servidor de Chat Persistente incluem o seguinte: 
  
- Histórico de chat padrão. O número de mensagens de chat disponível para cada sala de chat após a primeira solicitação. O padrão global é de 30 mensagens de chat. 
    
- Tamanho máximo do arquivo. O tamanho máximo do arquivo que pode ser enviado para ou baixado a partir de uma sala. O padrão global é de 20 MB.
    
- Limite de atualização do participante. O número máximo de participantes de uma determinada sala de chat para a qual um Chat persistente enviará atualizações. O padrão global é de 75.
    
- URL de gerenciamento de salas. A URL usada para gerenciar a sala de chat personalizada. A configuração permite o uso de uma solução de gerenciamento de sala personalizado. 
   
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurar opções globais do servidor de chat persistente

Para configurar opções globais do servidor de chat persistente:
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurar opções para um pool específico de servidores de chat persistentes

Para configurar as opções de um pool específico do servidor de chat persistente.
  
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
    
   - Em **URL de gerenciamento de salas**, selecione a URL de gerenciamento de salas. Essa é a URL para uma implantação de gerenciamento de salas baseado na Web. Se você não precisar personalizar o gerenciamento de salas e simplesmente usar a configuração padrão, deixe esta opção em branco.
    
     Se você quiser personalizar a experiência de criação da sala e incluir seu fluxo de trabalho de negócios específico, poderá criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de desenvolvimento de software) do servidor de chat persistente, hospedá-lo em algum lugar e colocar a URL aqui. Essa URL será enviada para o cliente de modo que, quando um usuário tentar exibir ou criar uma sala, ele será direcionado para sua solução personalizada de gerenciamento de salas.
    
7. Clique em **Confirmar**.
    

