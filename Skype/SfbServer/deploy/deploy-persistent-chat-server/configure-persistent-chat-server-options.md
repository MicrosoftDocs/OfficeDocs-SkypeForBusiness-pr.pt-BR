---
title: Configurar opções do Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Resumo: Saiba como configurar opções de servidor de Chat persistente em escopo global, site ou nível de pool no Skype para Business Server 2015.'
ms.openlocfilehash: fd4d9ed10c2629f714d336190e5c85b2dfe1621e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883753"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurar opções do Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como configurar opções de servidor de Chat persistente em escopo global, site ou nível de pool no Skype para Business Server 2015.
  
Você pode especificar várias opções para o servidor de Chat persistente que podem ser aplicadas globalmente, para todos os pools dentro de um site ou um pool específico dentro de um site. As opções do Servidor de Chat Persistente incluem o seguinte: 
  
- Histórico de chat padrão. O número de mensagens de chat disponível para cada sala de chat após a primeira solicitação. O padrão global é de 30 mensagens de chat. 
    
- Tamanho máximo do arquivo. O tamanho máximo do arquivo que pode ser enviado para ou baixado a partir de uma sala. O padrão global é de 20 MB.
    
- Limite de atualização do participante. O número máximo de participantes de uma determinada sala de chat para a qual um Chat persistente enviará atualizações. O padrão global é de 75.
    
- URL de gerenciamento de sala. A URL usada para gerenciar a sala de chat personalizada. A configuração permite o uso de uma solução de gerenciamento de sala personalizado. 
   
> [!NOTE] 
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurar opções globais do servidor de Chat persistente

Para configurar as opções globais do servidor de Chat persistente:
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurar opções para um pool específico do servidor de Chat persistente

Para configurar opções de um pool do servidor de Chat persistente específico.
  
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
    

