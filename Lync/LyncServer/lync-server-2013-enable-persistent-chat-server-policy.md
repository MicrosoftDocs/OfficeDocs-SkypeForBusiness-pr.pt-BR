---
title: 'Lync Server 2013: habilitar política de servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794fe378f9e7d8024f4bc06000d6d7d1cd89481e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528568"
---
# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Habilitar política de servidor de chat persistente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

No painel de controle do Lync Server 2013, você pode usar a página **política de chat persistente** do grupo de **chat persistente** para gerenciar políticas em nível global, de pool, de site ou de usuário, incluindo a configuração da política global padrão e a criação de uma ou mais políticas de usuário e de site adicionais para sua implantação. Se um usuário estiver habilitado para o servidor de chat persistente por política, o ambiente do servidor de chat persistente aparecerá no cliente do Lync 2013.

<div>


> [!NOTE]  
> Na topologia, as políticas de site do servidor de chat persistente são aplicadas globalmente, por pool do usuário ou por site do usuário ou por usuário.



</div>

A política global é criada automaticamente quando você implanta o servidor de chat persistente, e pode ser configurada, mas não excluída. Como a política global se aplica a todos os usuários, não é necessário defini-la para cada usuário.

Você pode criar e configurar várias políticas de site e de usuário, juntamente com a política global, habilitar usuários para o servidor de chat persistente. As políticas de servidor de chat persistente de pool e de site substituem a política global de servidor de chat persistente, mas apenas para os usuários desse site. As políticas de usuário substituem as políticas global, de pool e de site para os usuários aos quais a política de usuário é atribuída.

<div>


> [!NOTE]  
> Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à topologia e, em seguida, publicar a topologia. Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurar a política global para chat persistente no Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Criar uma política de site para chat persistente no Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Criar uma política de usuário para chat persistente no Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Aplicar uma política de chat persistente a um usuário ou grupo de usuários no Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

