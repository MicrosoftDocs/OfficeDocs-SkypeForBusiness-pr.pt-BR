---
title: 'Lync Server 2013: concedendo permissões de unidade organizacional'
description: 'Lync Server 2013: concedendo permissões de unidade organizacional.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ad862241e409190620afa7dbf4fa73adf339de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554507"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Concedendo permissões de unidade organizacional no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-05-14_

Você pode usar o cmdlet **Grant-CsOuPermission** para conceder permissões a objetos em unidades organizacionais especificadas para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessá-los sem serem membros do grupo Administradores de Domínio. As permissões adicionadas à unidade organizacional especificada são as mesmas permissões que o cmdlet **Enable-CsAdDomain** adiciona aos contêineres de computadores e usuários durante a preparação do domínio.

Use o cmdlet **Test-CsOuPermission** para verificar as permissões configuradas usando o cmdlet **Grant-CsOuPermission**.

Você pode usar o cmdlet **Revoke-CsOuPermission** para remover permissões concedidas usando o cmdlet **Grant-CsOuPermission**.

<div>

## <a name="to-grant-ou-permissions"></a>Para conceder permissões de UO

1.  Faça logon em um computador que executa o Lync Server 2013 no domínio em que você deseja conceder permissões de OU. Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Se o parâmetro Domain não for especificado, o valor padrão será o domínio local.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>Para verificar permissões de UO

1.  Faça logon em um computador que executa o Lync Server 2013 no domínio em que você deseja verificar as permissões de OU concedidas usando o cmdlet **Grant-CsOuPermission** . Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Se o parâmetro Domain não for especificado, o valor padrão será o domínio local.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>Para revogar permissões de OU

1.  Faça logon em um computador que executa o Lync Server 2013 no domínio onde você deseja revogar as permissões de OU que foram concedidas pelo cmdlet **Grant-CsOuPermission** . Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Se o parâmetro Domain não for especificado, o valor padrão será o domínio local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

