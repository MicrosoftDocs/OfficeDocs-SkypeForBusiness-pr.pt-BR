---
title: Página Principal do Suplemento de Chat Persistente
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
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: Você pode usar a seção Add-in da página chat persistente para associar URLs com salas de Chat Persistente. Essas URLs aparecem no cliente na sala de chat no painel de extensibilidade da conversa. Um administrador deve adicionar os Complementos à lista de complementos registrados, e os gerentes/Criadores de sala de chat devem associar salas a um dos complementos registrados para que os usuários possam ver essa atualização em seus clientes.
ms.openlocfilehash: ee747e12b4a6209d831588e68533531b0a7d95ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803791"
---
# <a name="persistent-chat-add-in-main-page"></a>Página Principal do Suplemento de Chat Persistente

Você pode usar a **seção Desassociação** da página **Chat Persistente** para associar URLs a salas de Chat Persistente. Essas URLs aparecem no cliente na sala de chat no painel de extensibilidade da conversa. Um administrador deve adicionar os Complementos à lista de complementos registrados, e os gerentes/Criadores de sala de chat devem associar salas a um dos complementos registrados para que os usuários possam ver essa atualização em seus clientes.

Os suplementos são usados para estender a experiência na sala. Um complemento típico pode incluir uma URL apontando para um aplicativo Silverlight que intercepta quando uma cotação das ações é postada em uma sala de chat e mostra o histórico de ações no painel de extensibilidade. Outros exemplos incluem o URL do OneNote 2013 na sala de chat como um suplemento para incluir algum contexto compartilhado, como o "Mais lembrado" ou "Assunto do dia."

Para criar Add-ins para salas de Chat Persistente, consulte Configurar os complementos para salas de Chat Persistente no [Skype for Business Server 2015.](../../manage/persistent-chat/configure-add-ins.md) Se você for um Administrador de Chat Persistente, poderá criar complementos usando o painel de controle ou cmdlets do Windows PowerShell.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Suplemento**:

- [Configurar os complementos para salas de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Para configurar Suplementos para salas de chat

As listas a seguir descrevem os menus, comando, campos e propriedades na página.

1. A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2. No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle, consulte [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).

3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Suplemento**.

    Para várias implantações de pool de Servidor de Chat Persistente, selecione o pool apropriado na lista lista.

4. Na página **Suplementos**, clique em **Novo**.

5. Em **Selecionar um Serviço,** selecione o serviço correspondente ao pool de Servidor de Chat Persistente onde você precisa criar o Add-in. Os suplementos não podem ser movidos de um pool para outro ou compartilhado entre pools diferentes.

6. Em **Suplementos novos**, faça o seguinte:

   - Em **Nome**, especifique um nome para o novo suplemento.

   - Em **URL**, especifique o  URL que deve ser associada ao suplemento. Os URLs são limitados aos protocolos http e https.

7. Clique em **Confirmar**.

## <a name="see-also"></a>Confira também

Para obter detalhes sobre recursos e capacidades do Servidor de Chat Persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).


