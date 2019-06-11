---
title: 'Lync Server 2013: Configurar salas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08b7cb0146f96b151af021a63ef97a485a0a9dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Configurar salas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

Configurar salas de chat persistentes geralmente é manipulado por usuários ou outras equipes centrais usando a interface de linha de comando do Windows PowerShell; Geralmente, um administrador não gerencia as salas de chat. No entanto, se você precisar criar e gerenciar salas de chat, poderá usar a interface de linha de comando do Windows PowerShell ou adicionar-se como membro a uma sala de chat e usar o cliente Lync 2013.

Para obter detalhes sobre como configurar salas de chat usando a interface de linha de comando do Windows PowerShell, consulte o "gerenciamento de sala" em Configurando o [servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

<div>

## <a name="managing-data-in-chat-rooms"></a>Gerenciando dados em salas de chat

O servidor de chat persistente permite aos usuários colaborar enviando mensagens para salas de chat persistente. Os dados persistem no servidor e os membros da sala podem ter acesso aos dados, incluindo dados históricos. No entanto, os usuários com funções diferentes têm acesso diferente aos dados persistentes, conforme descrito na lista a seguir.

  - Os administradores podem excluir qualquer conteúdo (por exemplo, conteúdo publicado antes de determinada data) de qualquer sala de chat para impedir que o banco de dados assuma proporções muito grandes. Ou podem remover ou substituir mensagens que são consideradas inapropriadamente para uma determinada sala de chat.

  - Os usuários finais, inclusive os autores das mensagens, não podem excluir conteúdo de nenhuma sala de chat.

  - Os gerentes de salas de chat podem desabilitar salas, mas não podem excluir salas. Somente os administradores podem excluir uma sala de chat depois que ela foi criada.

Quando uma mensagem é excluída, não é possível desfazer a ação. No entanto, as mensagens excluídas podem ser restauradas se houver um backup. Se um servidor de conformidade de chat persistente estiver habilitado, as mensagens antigas serão mantidas no banco de dados de conformidade.

<div>


> [!NOTE]  
> Este uso de dados da sala de chat aplica-se ao Lync Server 2013, aplicativo de API do servidor de chat persistente, exceto quando a função de administrador estiver envolvida. A API do servidor de chat persistente não pode ser usada para fazer qualquer uma das operações do administrador. Você deve executar essas operações no Shell de gerenciamento do Lync Server.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

