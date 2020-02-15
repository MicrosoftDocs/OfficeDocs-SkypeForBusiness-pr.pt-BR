---
title: 'Lync Server 2013: adicionando texto personalizado a mensagens instantâneas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0681df9803615fee04c20e52258120bd6616e57d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>Adicionando texto personalizado a mensagens instantâneas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-20_

Adicione um aviso de isenção de responsabilidade ao início de cada conversa de IM (mensagens instantâneas) do Lync 2013 usando os cmdlets **New-CSClientPolicy** ou **set-CSClientPolicy** do Shell de gerenciamento do Lync Server com o parâmetro imwarning.

O comando no exemplo a seguir adiciona um lembrete de segurança na parte superior da janela Conversa sempre que uma nova conversa de IM começa:

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Use **Grant-CSClientPolicy** para atribuir essa nova política aos usuários. Para obter detalhes, consulte **New-CSClientPolicy** e **Grant-CSClientPolicy** na documentação do Shell de gerenciamento do Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

