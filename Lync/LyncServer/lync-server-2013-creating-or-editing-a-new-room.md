---
title: 'Lync Server 2013: Criando ou editando uma nova sala'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd0fdbce300f417764e093fec3acb8705b2d17b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Criando ou editando uma nova sala no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-03-19_

A configuração de salas de chat persistente é comumente manipulada pelos usuários; Geralmente, um administrador de chat persistente não configura ou gerencia salas de chat. Cmdlets do Windows PowerShell para gerenciar salas estão disponíveis somente para administradores do **CsPersistentChatAdministrator** .

Os usuários que são **criadores** em qualquer categoria determinada podem usar o cliente do Lync para criar e gerenciar salas. Os usuários que foram designados como gerentes de uma sala de chat específica também podem executar o gerenciamento contínuo da sala, como a edição de propriedades da sala ou associação.

<div>


> [!TIP]  
> Os administradores de chat persistente também podem ser criadores e não estão sujeitos às restrições colocadas em criadores.



</div>

Opcionalmente, se você for um administrador de chat persistente, poderá empregar uma interface de usuário para criar e gerenciar salas de chat em vez de usar cmdlets do Windows PowerShell. Para fazer isso, habilite um administrador para servidor de chat persistente e use o cliente do Lync para criar e gerenciar salas de chat.

Se quiser criar um fluxo de trabalho de gerenciamento de sala personalizado para seus usuários, você pode definir a propriedade **RoomManagementUrl** na configuração do seu servidor de chat persistente para redirecionar os usuários para sua solução personalizada do cliente do Lync.

Para obter detalhes sobre como configurar salas de chat usando a interface de linha de comando do Windows PowerShell, consulte o "gerenciamento de sala" em [Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para obter detalhes sobre como configurar salas de chat, consulte [Configurar salas no Lync Server 2013](lync-server-2013-configure-rooms.md) na documentação de implantação.

<div>


> [!NOTE]  
> O servidor de chat persistente permite que os usuários criem e gerenciem a sala de chat para um site específico. No entanto, os usuários não podem criar ou gerenciar salas de chat em outros sites na mesma topologia. Certifique-se de especificar os criadores e gerentes da sala de chat para todos os sites da sua organização.



</div>

<div>


> [!NOTE]  
> Os usuários que estiverem hospedados em um aparelho de ramificação de Lync do Lync Server não poderão criar novas salas de chat ou exibir o cartão de sala para salas existentes.



</div>

</div>

<span> </span>

</div>

</div>

</div>

