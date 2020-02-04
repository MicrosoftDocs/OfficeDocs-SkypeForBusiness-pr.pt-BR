---
title: 'Lync Server 2013: Habilitar política de Servidor de Chat Persistente'
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
ms.openlocfilehash: 27d87277c813c24ae36de14430bc711d991d7181
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Habilitar política de Servidor de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

No painel de controle do Lync Server 2013, você pode usar a página **política de chat persistente** do grupo de **chat persistente** para gerenciar políticas em um nível global, de pool, de site ou de usuário, incluindo a configuração da política global padrão e a criação de uma ou mais políticas de usuário e de site adicionais para a sua implantação. Se um usuário estiver habilitado para o servidor de chat persistente por política, o ambiente do servidor de chat persistente aparecerá no cliente do Lync 2013.

<div>


> [!NOTE]  
> Na topologia, as políticas de site do servidor de chat persistente se aplicam globalmente, o pool de cada usuário ou o site de cada usuário ou por usuário.



</div>

A política global é criada automaticamente quando você implanta um servidor de chat persistente, e pode ser configurada, mas não excluída. Como ela se aplica a todos os usuários, não é necessário defini-la por usuário.

Você pode criar e configurar várias políticas de site e de usuário, juntamente com a política global, habilitar usuários para o servidor de chat persistente. As políticas de servidor de chat persistente do pool e do site substituem a política global de servidor de chat persistente, mas somente para os usuários desse site. As políticas de usuário substituem as políticas globais, de pool e de site para os usuários aos quais são atribuídas.

<div>


> [!NOTE]  
> Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte a servidor de chat persistente à topologia e, em seguida, publicar a topologia. Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurar a política global para Chat Persistente no Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Criar uma política de site para chat persistente no Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Criar uma política de usuário para Chat Persistente no Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Aplicar uma política de Chat Persistente a um usuário ou grupo de usuários no Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

