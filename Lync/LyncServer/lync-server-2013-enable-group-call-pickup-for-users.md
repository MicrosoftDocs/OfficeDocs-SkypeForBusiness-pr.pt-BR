---
title: 'Lync Server 2013: habilitar o recebimento de chamadas em grupo para usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b54abf04c7c0d892e5cc58938866592f96cc1776
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Habilitar a retirada de chamadas em grupo para usuários no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-30_

Use a ferramenta kit de recursos do SEFAUtil para habilitar o recurso de recebimento de chamadas em grupo para usuários. Os usuários devem receber um número de grupo com o tipo GroupPickup na tabela órbita do estacionamento de chamada para que a retirada de chamadas em grupo seja habilitada. Você atribui um número de grupo de recebimento de chamada e habilita o recebimento de chamadas em grupo ao mesmo tempo usando o parâmetro/enablegrouppickup quando você executa o SEFAUtil. exe.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>Para habilitar a retirada de chamadas em grupo para um usuário

1.  Realize logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.

2.  Na linha de comando, execute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por exemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Confira também


[Atribuir números de recebimento de chamadas em grupo aos usuários no Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Desabilitar a retirada de chamadas em grupo para usuários no Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

