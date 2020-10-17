---
title: 'Lync Server 2013: Criando ou editando uma nova sala'
description: 'Lync Server 2013: Criando ou editando uma nova sala.'
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
ms.openlocfilehash: d822eb05993f77c57200e29364f0a6a68509450b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562977"
---
# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Criando ou editando uma nova sala no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-03-19_

A configuração de salas de chat persistente é normalmente tratada pelos usuários; um administrador de chat persistente normalmente não configura ou gerencia salas de chat. Os cmdlets do Windows PowerShell para gerenciar salas estão disponíveis somente para administradores do **CsPersistentChatAdministrator** .

Os usuários que são **criadores** em qualquer categoria determinada podem usar o cliente Lync para criar e gerenciar salas. Os usuários que foram designados como gerentes de uma sala de chat específica também podem realizar gerenciamento contínuo da sala, como edição das propriedades ou associação das salas.

<div>


> [!TIP]  
> Os administradores de chat persistente também podem ser criadores e não estão sujeitos às restrições colocadas nos criadores.



</div>

Opcionalmente, se você for um administrador de chat persistente, poderá empregar uma interface de usuário para criar e gerenciar salas de chat em vez de usar cmdlets do Windows PowerShell. Para fazer isso, habilite um administrador para servidor de chat persistente e use o cliente Lync para criar e gerenciar salas de chat.

Se você deseja criar um fluxo de trabalho de gerenciamento de sala personalizado para seus usuários, você pode definir a propriedade **RoomManagementUrl** na sua configuração de servidor de chat persistente para redirecionar os usuários para sua solução personalizada do cliente Lync.

Para obter detalhes sobre como configurar salas de chat usando a interface de linha de comando do Windows PowerShell, consulte "gerenciamento de sala" em [Configurando servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para obter detalhes sobre como configurar salas de chat, consulte [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) na documentação de implantação.

<div>


> [!NOTE]  
> Servidor de chat persistente permite que os usuários criem e gerenciem a sala de chat de um site específico. No entanto, os usuários não podem criar ou gerenciar salas de chat em outros sites dentro da mesma topologia. Certifique-se de especificar os criadores e gerentes de sala de chat para todos os sites em sua organização.



</div>

<div>


> [!NOTE]  
> Os usuários hospedados em um aparelho de filial persistente do Lync Server não podem criar novas salas de chat ou exibir o cartão de sala para salas existentes.



</div>

</div>

<span> </span>

</div>

</div>

</div>

