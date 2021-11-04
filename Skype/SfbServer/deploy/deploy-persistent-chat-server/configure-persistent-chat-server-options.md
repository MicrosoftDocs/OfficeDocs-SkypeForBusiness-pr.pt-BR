---
title: Configurar opções do Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Resumo: saiba como configurar as opções do Servidor de Chat Persistente no nível global, do site ou do pool no Skype for Business Server 2015.'
ms.openlocfilehash: 76ad47a45f8883064b712107ec54b20939437dcb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751310"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurar opções do Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como configurar as opções do Servidor de Chat Persistente no nível global, do site ou do pool no Skype for Business Server 2015.
  
Você pode especificar várias opções para o Servidor de Chat Persistente que podem ser aplicadas globalmente, a todos os pools em um site ou a um pool específico dentro de um site. As opções do servidor de Chat Persistente incluem o seguinte: 
  
- Histórico de chat padrão. O número de mensagens de chat disponíveis para cada sala de chat após a primeira solicitação. O padrão global é 30 mensagens de chat. 
    
- Tamanho máximo do arquivo. O tamanho máximo de um arquivo que pode ser carregado ou baixado de uma sala. O padrão global é 20 MB.
    
- Limite de atualização do participante. O número máximo de participantes em uma determinada sala de chat para a qual o Chat Persistente enviará atualizações de lista. O padrão global é 75.
    
- URL de Gerenciamento de Sala. A URL usada para gerenciamento de sala de chat personalizada. A configuração permite o uso de uma solução de gerenciamento de sala personalizada. 
   
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurar opções globais do Servidor de Chat Persistente

Para configurar opções globais do Servidor de Chat Persistente:
  
1. A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.
    
2. No menu **Iniciar,** selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Configuração de Chat Persistente**.
    
4. Na página **Configuração de Chat Persistente,** clique em **Novo e** em **Configuração do Site.**
    
    > [!IMPORTANT]
    > Escolha essa opção se quiser que a configuração seja aplicada a todos os pools do Servidor de Chat Persistente implantados no site. Clique **em Configuração do** Pool se quiser que a configuração seja aplicada a um pool específico do Servidor de Chat Persistente.
  
5. Em **Selecionar um Site,** selecione o site a ser configurado para a configuração do site do Servidor de Chat Persistente.
    
6. Em **Nova Configuração de Chat Persistente**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do site já existe.
    
   - Em **Histórico de chat padrão**, defina o número de mensagens do chat que serão processadas para cada sala na primeira solicitação. Por padrão, o número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
    
     > [!IMPORTANT]
     > O Servidor de Chat Persistente armazenará essas mensagens em cache na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache. Sempre é possível acessar conteúdo histórico por meio da pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao se conectar a uma sala de chat. 
  
   - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo do arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo para um arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual o carregamento de arquivos é habilitado por sua configuração correspondente de **Categoria**).
    
   - Em **Limite de atualização de participantes**, selecione o limite de atualizações de participantes. O Servidor de Chat Persistente envia informações de lista (que está conectado a uma sala de chat) para todos os participantes até que o número de usuários conectados atinja esse número. Por padrão, o número é 75. Esse limite indica o número máximo de participantes em uma determinada sala além da qual o Servidor de Chat Persistente para de enviar atualizações de lista para clientes conectados sobre quem está presente na sala.
    
   - (Opcional.) Em **URL de gerenciamento de sala,** selecione a URL de gerenciamento de sala. Essa é a URL para um gerenciamento de sala personalizada baseada na Web. Se você não precisar personalizar o gerenciamento de sala e simplesmente usar a configuração padrão, deixe essa opção em branco. Após a URL ser definida, ela é aplicada como URL de gerenciamento de sala interna e externa.
    
     Se você quiser personalizar sua experiência de criação de sala e incluir seu fluxo de trabalho comercial específico, você pode criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de Desenvolvimento de Software do Servidor de Chat Persistente), hospedá-lo em algum lugar e colocar a URL aqui. Essa URL é enviada para o cliente de modo que quando um usuário tenta exibir ou criar uma sala, ele ou ela é direcionado à sua solução de gerenciamento de sala personalizada.
    
7. Clique em **Confirmar**.
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurar opções para um pool específico do Servidor de Chat Persistente

Para configurar opções para um pool específico de Servidor de Chat Persistente.
  
1. A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.
    
2. No menu **Iniciar,** selecione o painel Skype for Business Server controle ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Configuração de Chat Persistente**.
    
4. Na página **Configuração de Chat Persistente**, clique em **Novo** e clique em **Configuração de pool**.
    
5. Em **Selecionar um Serviço,** selecione o serviço associado ao pool do Servidor de Chat Persistente a ser configurado.
    
6. Em **Nova Configuração de Chat Persistente**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do pool de sites já existe.
    
   - Em **Histórico de chat padrão**, defina o número de mensagens do chat que serão processadas para cada sala na primeira solicitação. Por padrão, o número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
    
     > [!IMPORTANT]
     > O Servidor de Chat Persistente armazenará essas mensagens em cache na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache. Sempre é possível acessar conteúdo histórico por meio da pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao se conectar a uma sala de chat. 
  
   - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo do arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo para um arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual o carregamento de arquivos é habilitado por sua configuração correspondente de **Categoria**).
    
   - Em **Limite de atualização de participantes**, selecione o limite de atualizações de participantes. O Servidor de Chat Persistente envia informações de lista (que está conectado a uma sala de chat) para todos os participantes até que o número de usuários conectados atinja esse número. Por padrão, o número é 75. Esse limite indica o número máximo de participantes em uma determinada sala além da qual o Servidor de Chat Persistente para de enviar atualizações de lista para clientes conectados sobre quem está presente na sala.
    
   - Em **URL de Gerenciamento da Sala**, selecione a URL de gerenciamento de sala. Essa é a URL para uma implantação de gerenciamento de sala baseada na Web. Se você não precisar personalizar o gerenciamento de sala e simplesmente usar a configuração padrão, deixe essa opção em branco.
    
     Se você quiser personalizar sua experiência de criação de sala e incluir seu fluxo de trabalho comercial específico, você pode criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de Desenvolvimento de Software do Servidor de Chat Persistente), hospedá-lo em algum lugar e colocar a URL aqui. Esta URL é enviada para o cliente para que quando um usuário tentar exibir/criar uma sala, ele ou ela seja direcionado para sua solução de gerenciamento de sala personalizada.
    
7. Clique em **Confirmar**.
    

