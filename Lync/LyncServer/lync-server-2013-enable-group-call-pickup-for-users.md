---
title: 'Lync Server 2013: habilitar o recebimento de chamadas em grupo para usuários'
description: 'Lync Server 2013: habilitar o recebimento de chamadas em grupo para usuários.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27951e9000fd17aac90339cf2a507757ae96a397
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559617"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Habilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-30_

Use a ferramenta SEFAUtil Resource Kit para habilitar o recebimento de chamadas em grupo para usuários. Os usuários devem ser atribuídos a um número de grupo com o tipo GroupPickup na tabela de órbita de estacionamento de chamada para que o recebimento de chamadas de grupo seja habilitado. Você atribui um número de grupo de recebimento de chamadas e habilita o recebimento de chamadas em grupo ao mesmo tempo usando o parâmetro/enablegrouppickup quando você executa o SEFAUtil.exe.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>Para habilitar o recebimento de chamadas em grupo para um usuário

1.  Faça logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.

2.  Na linha de comando, execute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por exemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Consulte também


[Atribuir números de recebimento de chamadas de grupo aos usuários no Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Desabilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

