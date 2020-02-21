---
title: 'Lync Server 2013: configurar salas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e78401d0f72f3b29f50453f49f7d7eb66811715
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Configurar salas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

A configuração de salas de chat persistente é normalmente tratada por usuários ou outras equipes centrais usando a interface de linha de comando do Windows PowerShell; Normalmente, um administrador não gerencia as salas de chat. No entanto, se você tiver que criar e gerenciar salas de chat, poderá usar a interface de linha de comando do Windows PowerShell ou adicionar a si mesmo como um membro para uma sala de chat e usar o cliente Lync 2013.

Para obter detalhes sobre como configurar salas de chat usando a interface de linha de comando do Windows PowerShell, consulte "gerenciamento de sala" em [Configurando servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

<div>

## <a name="managing-data-in-chat-rooms"></a>Gerenciando dados em salas de chat

O servidor de chat persistente permite que os usuários colaborem postando mensagens em salas de chat persistente. Os dados persistem no servidor e os membros da sala podem ter acesso a eles, inclusive ao histório de dados. No entanto, os usuários que têm funções diferentes têm acesso diferente aos dados persistentes conforme descrito na lista a seguir.

  - Os administradores podem excluir qualquer conteúdo (por exemplo, conteúdo postado antes de determinada data) de qualquer sala de char para impedir que o banco de dados assuma proporções muito grandesm. Eles também podem remover ou substituir mensagens consideradas impróprias para uma sala de chat específica.

  - Os usuários finais, incluisive os autores das mensagens, não podem excluir conteúdo de nenhuma sala de chat.

  - Os gerentes das salas de chat podem desabilitar salas, mas não excluí-las. Somente os administradores podem excluir salas de chat após a criação.

Quando a mensagem é excluída, não é possível desfazer a ação. No entanto, as mensagens excluídas podem ser restauradas caso exista um backup. Se um servidor de conformidade de chat persistente estiver habilitado, as mensagens antigas serão mantidas no banco de dados de conformidade.

<div>


> [!NOTE]  
> Este uso de dados da sala de chat se aplica ao aplicativo de API do servidor de chat persistente do Lync Server 2013, exceto no caso em que a função de administrador está envolvida. A API do servidor de chat persistente não pode ser usada para fazer qualquer uma das operações do administrador. Você deve executar essas operações no Shell de gerenciamento do Lync Server.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

