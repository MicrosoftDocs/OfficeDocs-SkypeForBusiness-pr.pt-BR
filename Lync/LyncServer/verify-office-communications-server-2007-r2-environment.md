---
title: Verificar o ambiente do Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ce71bce6594c0604027df9f055859f023048518
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Verificar o ambiente do Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-16_

Antes de implantar o Lync Server 2013 em um estado de coexistência com o Office Communications Server 2007 R2, você precisa verificar se os serviços do Office Communications Server 2007 R2 estão configurados e iniciados.

**Verificar se o pool é iniciado usando a ferramenta administrativa do Office Communications Server 2007 R2**

1.  Abra a ferramenta administrativa do Office Communications Server 2007 R2.

2.  Expanda o nó **Floresta**, expanda o nó **ServidoresStandard Edition** ou **Pools Enterprise** e expanda o pool ou o nome do servidor.

3.  Certifique-se de que os serviços estejam sendo executado no servidor Standard Edition ou pool Enterprise.
    
    ![Console de administração do Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console de administração do Office Communications Server 2007 R2")

**Revisar usuários configurados para o Office Communications Server 2007 R2**

1.  Abra a ferramenta administrativa do Office Communications Server 2007 R2.

2.  Expanda o nó **Floresta**, expanda o nó **ServidoresStandard Edition** ou **Pools Enterprise** e expanda o pool ou o nome do servidor.

3.  Clique em **Usuários**.

4.  Verifique a lista de usuários do Office Communications Server 2007 R2.
    
    ![Listar usuários na ferramenta de administração do OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Listar usuários na ferramenta de administração do OCS")

**Verificar a configuração de parceiro federado XMPP herdado**

1.  No servidor XMPP herdado, navegue até o mini-aplicativo Serviços\\de ferramentas administrativas.

2.  Verifique se o serviço do Gateway XMPP do Office Communications Server foi inicializado.
    
    ![Serviço de Gateway XMPP do Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Serviço de Gateway XMPP do Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

