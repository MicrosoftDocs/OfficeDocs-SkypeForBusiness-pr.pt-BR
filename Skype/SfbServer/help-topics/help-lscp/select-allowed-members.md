---
title: Selecionar Membros Permitidos
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Criar e gerenciar salas de Chat Persistente é muito mais fácil com o uso correto de categorias. Um Administrador de Chat Persistente pode definir AllowedMembers e Criadores para cada categoria e também pode definir as configurações e comportamentos padrão da sala de chat que serão aplicadas a todas as salas de chat criadas na categoria. Os administradores de Chat Persistente criam e gerenciam categorias usando o painel de controle ou Windows PowerShell cmdlets.
ms.openlocfilehash: 0a0b7730cc421cace1112413f4d08c7e65e8483e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737967"
---
# <a name="select-allowed-members"></a>Selecionar Membros Permitidos

Criar e gerenciar salas de Chat Persistente é muito mais fácil com o uso correto de categorias. Um Administrador de Chat Persistente pode definir **AllowedMembers** e Criadores para cada categoria e também pode definir as configurações e comportamentos padrão da sala de chat que serão aplicadas a todas as salas de chat **criadas** na categoria. Os administradores de Chat Persistente criam e gerenciam categorias usando o painel de controle ou Windows PowerShell cmdlets.

Usuários, Unidades Organizacionais (OUs) e grupos de usuário identificados como Creators da categoria são os únicos indivíduos e grupos que têm permissão para criar salas na categoria. Após a criação da categoria, eles podem escolher usuários, OUs e grupos de usuários na lista **AllowedMembers** da categoria como gerentes e membros da sala de chat para gerenciar e participar da sala.

## <a name="tasks-that-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Selecionar Membros Permitidos**:

- [Configurar categorias](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [Novos recursos de servidor de chat persistente](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o Painel de Controle Skype for Business Server, consulte [Manage Skype for Business Server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar as categorias para salas de chat

Em Associação , na seção **Membros** Permitidos, adicione ou remova usuários e outras entidades de Serviços de Domínio do Active Directory (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que têm permissão para serem adicionados como membros de salas de chat pertencentes à categoria. As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).


Para obter detalhes sobre recursos e recursos do Servidor de Chat Persistente, consulte [Visão geral do Servidor](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) de Chat Persistente na documentação planejamento. Para obter detalhes sobre como trabalhar com configurações do Servidor de Chat Persistente, consulte [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) na documentação de Implantação e [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) na documentação Operações.

## <a name="see-also"></a>Confira também

[Noções básicas sobre associação ao chat persistente](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)