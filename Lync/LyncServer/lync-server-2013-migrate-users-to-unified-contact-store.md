---
title: 'Lync Server 2013: migrar usuários para o repositório unificado de contatos'
description: 'Lync Server 2013: migrar usuários para o repositório unificado de contatos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e9ee9850cc723ae132f15d7c0c6b3769e1240ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568587"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Migrar usuários para o repositório unificado de contatos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-15_

Os contatos de um usuário são migrados automaticamente para o servidor Exchange 2013 quando o usuário:

  - For atribuído com uma política de serviços do usuário com UcsAllowed definido para True.

  - Foi provisionado com uma caixa de correio do Exchange 2013 e entrou na caixa de correio pelo menos uma vez.

  - Faz login usando um cliente avançado do Lync 2013.

Se o usuário fizer logon com um cliente do Lync 2010 ou anterior ou se o usuário não estiver conectado a um servidor do Exchange 2013, a política de serviços do usuário será ignorada e os contatos do usuário permanecerão no Lync Server.

É possível determinar se os contatos do usuário foram migrados usando um dos seguintes métodos:

  - Verifique a chave do registro no computador cliente:
    
    HKey \_ Current \_ user \\ software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ \<SIP URL\> \\ UCS
    
    Se os contatos do usuário estiverem armazenados no Exchange 2013, esta chave contém um valor de InUCSMode com um valor de 2165.

  - Execute o cmdlet **Test-CsUnifiedContactStore**. Na linha de comando do Shell de gerenciamento do Lync Server, digite:
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Se o **Test-CsUnifiedContactStore** tiver êxito, os contatos do usuário foram migrados para o repositório de contatos unificados.

</div>

<span> </span>

</div>

</div>

</div>

