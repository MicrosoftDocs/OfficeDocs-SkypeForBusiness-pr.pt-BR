---
title: 'Lync Server 2013: Movendo uma sala de chat de uma categoria a outra'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f9774e53321ff6fe667b3b8c8dcfe0e78bcdaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Movendo uma sala de chat de uma categoria a outra no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Recomendamos que você não altere a categoria de uma sala de chat persistente após a criação da sala de chat. No entanto, se o gerente da sala de chat tem privilégios de **criador** em outra categoria, ele pode mover a sala de uma categoria para outra. A sala não é excluída nem recriada. É uma alteração de associação dentro do banco de dados.

Alterar uma categoria de sala de chat raramente deve ser feito. Uma categoria determina a associação permitida para a sala de chat, por isso, quando uma sala de chat muda de categoria, todas as listas de controle de acesso do sistema (SACLs) não mais suportadas pela nova categoria são purgadas. Por exemplo, se um usuário era membro da sala e não é mais um **AllowedMember** na nova categoria, a participação da sala será modificada e o usuário será removido da sala.

Para obter detalhes sobre como mover uma sala de chat usando a interface de linha de comando do Windows PowerShell, consulte o "gerenciamento de sala" em [Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para obter detalhes sobre como configurar salas de chat, consulte [Configurar salas no Lync Server 2013](lync-server-2013-configure-rooms.md) na documentação de implantação.

</div>

<span> </span>

</div>

</div>

</div>

