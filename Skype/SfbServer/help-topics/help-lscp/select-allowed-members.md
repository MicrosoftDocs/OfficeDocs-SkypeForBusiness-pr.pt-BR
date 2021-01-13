---
title: Selecionar Membros Permitidos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Criar e gerenciar salas de Chat Persistente é muito mais fácil com o uso correto de categorias. Um Administrador de Chat Persistente pode definir AllowedMembers e Criadores para cada categoria e também pode definir as configurações e comportamentos padrão da sala de chat que serão aplicados a todas as salas de chat criadas na categoria. Os Administradores de Chat Persistente criam e gerenciam categorias usando o painel de controle ou cmdlets do Windows PowerShell.
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829131"
---
# <a name="select-allowed-members"></a>Selecionar Membros Permitidos

Criar e gerenciar salas de Chat Persistente é muito mais fácil com o uso correto de categorias. Um Administrador de Chat Persistente pode definir **AllowedMembers** e Criadores para cada categoria e também pode definir as configurações e comportamentos padrão da sala de chat que serão aplicados a todas as salas de chat **criadas** na categoria. Os Administradores de Chat Persistente criam e gerenciam categorias usando o painel de controle ou cmdlets do Windows PowerShell.

Usuários, Unidades Organizacionais (OUs) e grupos de usuário identificados como Creators da categoria são os únicos indivíduos e grupos que têm permissão para criar salas na categoria. Depois que a categoria é criada, eles podem escolher usuários, OUs e grupos de usuários na lista **AllowedMembers** da categoria como gerentes e membros da sala de chat para gerenciar e participar da sala.

## <a name="tasks-that-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Selecionar Membros Permitidos**:

- [Configurar Categorias](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [Novos recursos de servidor de chat persistente](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o Painel de Controle do Skype for Business Server, consulte [Gerenciar o Skype for Business Server 2015.](../../manage/manage.md)

## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar as categorias para salas de chat

In **Membership**, in the **Allowed members section,** add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are allowed to be added as members of chat rooms belonging to the category. As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).


Para obter detalhes sobre recursos do Servidor de Chat Persistente, consulte [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation. Para obter detalhes sobre como trabalhar com configurações de Servidor de Chat Persistente, consulte [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.

## <a name="see-also"></a>Confira também

[Noções básicas sobre associação ao chat persistente](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
