---
title: 'Lync Server 2013: adicionando um link personalizado às mensagens de erro do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa65580cd9138b58792d4a0f0621bfe6f5f10c9c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Adicionando um link personalizado às mensagens de erro do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-20_

Personalize mensagens de erro do Lync 2013 adicionando um link para suas próprias informações de solução de problemas ou suporte técnico. Para fazer isso, use os cmdlets **New-CSClientPolicy** ou **set-CSClientPolicy** do Shell de gerenciamento do Lync Server com o parâmetro CustomLinkInErrorMessages. O texto do link personalizado é "clique aqui para obter tópicos de suporte do seu administrador" e não pode ser personalizado.

Por exemplo, o comando a seguir faz com que o link personalizado apareça na área de notas de rodapé de cada mensagem de erro do Lync 2013 e define o destino do link comohttp://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Use **Grant-CSClientPolicy** para atribuir essa nova política aos usuários. Para obter detalhes, consulte **New-CSClientPolicy** e **Grant-CSClientPolicy** na documentação do Shell de gerenciamento do Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

