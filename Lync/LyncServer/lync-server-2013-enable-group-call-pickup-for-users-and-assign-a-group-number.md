---
title: 'Lync Server 2013: habilitar o recebimento de chamadas em grupo para usuários e atribuir um número de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e83972d95956a0ed2bd44f08ba8787c46118730
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>Habilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013 e atribuir um número de grupo

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-30_

Após adicionar os números de grupo de recebimento de chamada à tabela de órbita de estacionamento de chamada, você atribui os números de grupo aos usuários e habilita o recebimento de chamadas em grupo para eles. Use a ferramenta de ativação de recursos de extensão secundária (SEFAUtil) para atribuir números de grupo e habilitar o recebimento de chamadas em grupo.

<div>


> [!NOTE]  
> Em uma implantação híbrida, não atribua um grupo de recebimento de chamadas de grupo aos usuários hospedados online. Os usuários hospedados online não podem participar do recebimento de chamadas em grupo. Ou seja, suas chamadas não podem ser atendidas por outros usuários e não podem responder chamadas para outros usuários.



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para atribuir um número de grupo e habilitar o recebimento de chamadas em grupo para um usuário

1.  Faça logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.

2.  Na linha de comando, execute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por exemplo, para atribuir o número de grupo 199 a um usuário:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>Confira também


[Desabilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

