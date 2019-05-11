---
title: Suplemento de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Você pode usar a seção Add-in da página Chat persistente para associar URLs salas de Chat persistente. Essas URLs aparecem no cliente na sala de chat no painel de extensão da conversa. Um administrador precisa adicionar Suplementos à lista de suplementos registrados, e os gerentes/Criadores de sala de chat precisam associar salas a um dos suplementos registrados antes de os usuários poderem ver essa atualização em seu cliente.
ms.openlocfilehash: b1a601ab1ecfa1b188f291534af914daef1037c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910529"
---
# <a name="persistent-chat-add-in"></a>Suplemento de Chat Persistente

Você pode usar a seção **Add-in** da página **Chat persistente** para associar URLs salas de Chat persistente. Essas URLs aparecem no cliente na sala de chat no painel de extensão da conversa. Um administrador precisa adicionar Suplementos à lista de suplementos registrados, e os gerentes/Criadores de sala de chat precisam associar salas a um dos suplementos registrados antes de os usuários poderem ver essa atualização em seu cliente.

Os suplementos são usados para estender a experiência na sala. Um suplemento típico pode incluir uma URL que aponta para um aplicativo Silverlight que intercepta quando um registrador de cotações é postado em uma sala de bate-papo e mostra o histórico de estoque no painel de extensibilidade. Outros exemplos incluem a URL do OneNote 2013 na sala de chat como um suplemento para incluir algum contexto compartilhado, como o "Mais lembrado" ou "Assunto do dia".

Para criar suplementos para salas de Chat persistente, consulte [Configurar suplementos para salas de Chat persistente no Skype para Business Server 2015](../../manage/persistent-chat/configure-add-ins.md). Se você for um administrador de Chat persistente, você pode criar suplementos usando o painel de controle ou os cmdlets do Windows PowerShell.

## <a name="tasks-that-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Suplemento**:

- [Configurar suplementos para salas de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Para configurar Suplementos para as salas de chat

As listas a seguir descrevem os menus, comando, campos e propriedades na página.

1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.

2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle, consulte [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).

3. Na barra de navegação esquerda, clique em **Chat Persistente** e depois em **Suplemento**.

    Para várias implantações de pool de servidor de Chat persistente, selecione o pool apropriado na lista suspensa.

4. Na página  **Suplementos**, clique em **Novo**.

5. Em **Selecionar um serviço**, selecione o serviço correspondente para o pool do servidor de Chat persistente onde você precisa criar o suplemento. Suplementos não podem ser movidos de um pool a outro nem compartilhado entre pools diferentes.

6. Em **Suplementos novos**, faça o seguinte:

   - Em **Nome**, especifique um nome para o novo suplemento.

   - Em **URL**, especifique a URL que deve ser associada ao suplemento. As URLs são limitadas aos protocolos http e https.

7. Clique em **Confirmar**.

## <a name="see-also"></a>Confira também

Para obter detalhes sobre os recursos de servidor de Chat persistente e recursos, consulte [Plan for Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server na Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Gerenciar o servidor de Chat persistente no Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md).


