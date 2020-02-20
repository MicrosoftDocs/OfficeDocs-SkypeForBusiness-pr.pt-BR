---
title: 'Lync Server 2013: habilitar usuários para repositório unificado de contatos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc769241059a2536ff644e6ea7b711aaa8cd342d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Habilitar usuários para repositório unificado de contatos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-07_

Quando você implanta o Lync Server 2013 e publica a topologia, o repositório unificado de contatos é habilitado para todos os usuários por padrão. Você não precisa realizar qualquer ação adicional para habilitar o repositório unificado de contatos após implantar o Lync Server 2013. Contudo, você pode usar o **Set-CsUserServicesPolicy** cmdlet para definir quais usuários têm o armazenamento unificado de contatos disponível. Você pode habilitar esse recurso globalmente, por local, por tenant ou por indivíduos ou grupos de indivíduos.

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>Para permitir o armazenamento unificado de contatos

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Faça um dos seguintes:
    
      - Para habilitar o repositório unificado de contatos globalmente para todos os usuários do Lync Server, na linha de comando, digite:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Para permitir o armazenamento unificado de contatos para os usuários em um local específico, digite na linha de comando:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Por exemplo:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Para permitir o armazenamento unificado de contatos por tenant, digite na linha de comando:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Por exemplo:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Para permitir o armazenamento unificado de contatos para usuários específicos, digite na linha de comando:
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > Você também pode alterar o URI do SIP ou o usuário remoto em vez do nome do usuário.

        
        </div>
        
        Por exemplo:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > No exemplo anterior, o primeiro comando criar uma nova política de acordo com o usuário chamada <EM>Usuários do UCS Permitidos</EM>, com o sinalizador AcsAllowed definido para True. O segundo comando define a política ao usuário com nome de Ken Myer, o que significa que Ken Myer está autorizado a ter armazenamento unificado de contatos.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

