---
title: 'Lync Server 2013: atribuir números de recebimento de chamadas de grupo aos usuários'
description: 'Lync Server 2013: atribuir números de recebimento de chamadas de grupo aos usuários.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d550b4556af427e11e99ffb26fb2a6c34d019490
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566127"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Atribuir números de recebimento de chamadas de grupo aos usuários no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-30_

Após adicionar os números de grupo de recebimento de chamada de grupo à tabela de órbita de estacionamento de chamada, você pode atribuir os grupos aos usuários. Use a ferramenta de ativação de recursos de extensão secundária (SEFAUtil) para atribuir grupos de recebimento de chamadas aos usuários.

<div>


> [!NOTE]  
> Em uma implantação híbrida, não atribua um grupo de recebimento de chamadas de grupo aos usuários hospedados online. Os usuários hospedados online não podem participar do recebimento de chamadas em grupo. Ou seja, suas chamadas não podem ser atendidas por outros usuários e não podem responder chamadas para outros usuários.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>Para atribuir um grupo de recebimento de chamadas de grupo a um usuário

1.  Faça logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.

2.  Na linha de comando, execute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por exemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Consulte também


[Habilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Desabilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

