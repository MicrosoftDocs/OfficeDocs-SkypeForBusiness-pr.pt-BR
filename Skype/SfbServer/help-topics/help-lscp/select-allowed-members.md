---
title: Selecionar Membros Permitidos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Criar e gerenciar salas de chat persistente é muito mais fácil com o uso correto de categorias. Um administrador de chat persistente pode definir AllowedMembers e criadores para cada categoria e também pode definir as configurações e os comportamentos padrão da sala de chat que serão aplicados a todas as salas de chat criadas na categoria. Administradores de chat persistentes criam e gerenciam categorias usando o painel de controle ou cmdlets do Windows PowerShell.
ms.openlocfilehash: ad371fada6bbb7e8c9a2620eb5ec533cc60a0673
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822294"
---
# <a name="select-allowed-members"></a>Selecionar Membros Permitidos

Criar e gerenciar salas de chat persistente é muito mais fácil com o uso correto de categorias. Um administrador de chat persistente pode definir **AllowedMembers** e **criadores** para cada categoria e também pode definir as configurações e os comportamentos padrão da sala de chat que serão aplicados a todas as salas de chat criadas na categoria. Administradores de chat persistentes criam e gerenciam categorias usando o painel de controle ou cmdlets do Windows PowerShell.

Usuários, Unidades Organizacionais (OUs) e grupos de usuários identificados como Criadores da categoria são os únicos indivíduos e grupos que porem criar salas na categoria. Após a criação da categoria, elas podem escolher usuários, UOs e grupos de usuários na lista **AllowedMembers** da categoria como gerentes e membros da sala de chat para gerenciar e participar da sala.

## <a name="tasks-that-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Selecionar Membros Permitidos**:

- [Configure Categories](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [New Persistent Chat Server Features](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o painel de controle do Skype for Business Server, consulte [gerenciar o Skype for Business server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorias salas de chat

Em **Associação**, na seção **Membros permitidos** , adicione ou remova usuários e outras entidades de segurança dos serviços de domínio Active Directory (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que podem ser adicionados como membros de salas de chat pertencentes à categoria. As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).


Para obter detalhes sobre recursos e recursos do servidor de chat persistente, consulte [visão geral do servidor de chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) na documentação de planejamento. Para obter detalhes sobre como trabalhar com configurações de servidor de chat persistente, consulte [Configurando o servidor de chat persistente](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) na documentação de implantação e [Gerenciando o Lync Server 2013, servidor de chat persistente](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) na documentação de operações.

## <a name="see-also"></a>Confira também

[Understanding Persistent Chat Membership](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
