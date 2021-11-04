---
title: Página Principal do Suplemento de Chat Persistente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: Você pode usar a seção Adicionar da página Chat Persistente para associar URLs a salas de Chat Persistente. Essas URLs aparecem no cliente na sala de chat no painel de extensibilidade da conversa. Um administrador deve adicionar Add-ins à lista de complementos registrados, e os gerentes/Criadores de salas de chat devem associar salas a um dos complementos registrados para que os usuários possam ver essa atualização em seu cliente.
ms.openlocfilehash: 226810dd7fca7327085a4c715269423ef962a816
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60757313"
---
# <a name="persistent-chat-add-in-main-page"></a>Página Principal do Suplemento de Chat Persistente

Você pode usar a **seção Adicionar da** página Chat **Persistente** para associar URLs a salas de Chat Persistente. Essas URLs aparecem no cliente na sala de chat no painel de extensibilidade da conversa. Um administrador deve adicionar Add-ins à lista de complementos registrados, e os gerentes/Criadores de salas de chat devem associar salas a um dos complementos registrados para que os usuários possam ver essa atualização em seu cliente.

Os suplementos são usados para estender a experiência na sala. Um complemento típico pode incluir uma URL apontando para um aplicativo Silverlight que intercepta quando um ticker de ações é postado em uma sala de chat e mostra o histórico de ações no painel de extensibilidade. Outros exemplos incluem o URL do OneNote 2013 na sala de chat como um suplemento para incluir algum contexto compartilhado, como o "Mais lembrado" ou "Assunto do dia."

Para criar Complementos para salas de Chat Persistente, consulte [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md). Se você for um Administrador de Chat Persistente, poderá criar complementos usando o painel de controle ou Windows PowerShell cmdlets.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Suplemento**:

- [Configurar os complementos para salas de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Para configurar Suplementos para salas de chat

As listas a seguir descrevem os menus, comando, campos e propriedades na página.

1. A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2. No menu **Iniciar,** selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle, consulte [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).

3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Suplemento**.

    Para várias implantações de pool do Servidor de Chat Persistente, selecione o pool apropriado na listada.

4. Na página **Suplementos**, clique em **Novo**.

5. Em **Selecionar um Serviço,** selecione o serviço correspondente ao pool do Servidor de Chat Persistente onde você precisa criar o Add-in. Os suplementos não podem ser movidos de um pool para outro ou compartilhado entre pools diferentes.

6. Em **Suplementos novos**, faça o seguinte:

   - Em **Nome**, especifique um nome para o novo suplemento.

   - Em **URL**, especifique o  URL que deve ser associada ao suplemento. Os URLs são limitados aos protocolos http e https.

7. Clique em **Confirmar**.

## <a name="see-also"></a>Confira também

Para obter detalhes sobre recursos e recursos do Servidor de Chat Persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), Deploy Persistent Chat Server in Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).