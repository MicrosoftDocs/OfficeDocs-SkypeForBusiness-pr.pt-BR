---
title: 'Lync Server 2013: Concedendo permissões de configuração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>Concedendo permissões de configuração no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-08-27_

Você pode usar o cmdlet **Grant-CsSetupPermission** para adicionar permissões de leitura, gravação, ReadSPN e WriteSPN ao grupo RTCUniversalServerAdmins para uma unidade organizacional (ou) especificada do Active Directory. Em seguida, os membros do grupo RTCUniversalServerAdmins nessa UO podem instalar servidores que executam o Lync Server 2013 no domínio especificado sem serem membros do grupo Domain admins.

Use o cmdlet **Test-CsSetupPermission** para verificar as permissões configuradas usando o cmdlet **Grant-CsSetupPermission** .

Você pode usar o cmdlet **REVOKE-CsSetupPermission** para remover permissões concedidas usando o cmdlet **Grant-CsSetupPermission** .

<div>

## <a name="to-grant-setup-permissions"></a>Para conceder permissões de configuração

1.  Faça logon em um computador que esteja executando o Lync Server 2013 no domínio onde você deseja conceder permissões de configuração. Use uma conta que seja membro do grupo Domain admins ou do grupo Administradores de empresa se a UO estiver em um domínio filho diferente.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute:
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio especificado (por exemplo, CN = computadores). Você também pode especificar esse parâmetro como o nome diferenciado (DN) completo da OU (por exemplo, "CN = computadores, DC = contoso, DC = com"). Nesse caso, você deve especificar um DN de OU consistente com o domínio especificado.
    
    Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>Para verificar as permissões de configuração

1.  Faça logon em um computador que esteja executando o Lync Server 2013 no domínio em que você deseja verificar as permissões de configuração concedidas usando o cmdlet **Grant-CsSetupPermission** . Use uma conta que seja membro do grupo Domain admins ou do grupo Administradores de empresa se a UO estiver em um domínio filho diferente.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute:
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio especificado (por exemplo, CN = computadores). Você também pode especificar esse parâmetro como o nome diferenciado (DN) completo da OU (por exemplo, "CN = computadores, DC = contoso, DC = com"). Nesse caso, você deve especificar um DN de OU consistente com o domínio especificado.
    
    Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>Para revogar permissões de configuração

1.  Faça logon em um computador que esteja executando o Lync Server 2013 no domínio onde você deseja revogar as permissões de configuração que foram concedidas pelo cmdlet **Grant-CsSetupPermission** . Use uma conta que seja membro do grupo Domain admins ou do grupo Administradores de empresa se a UO estiver em um domínio filho diferente.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute:
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio especificado (por exemplo, CN = computadores). Você também pode especificar esse parâmetro como o nome diferenciado (DN) completo da OU (por exemplo, "CN = computadores, DC = contoso, DC = com"). Nesse caso, você deve especificar um DN de OU consistente com o domínio especificado.
    
    Se você não especificar o parâmetro Domain, o valor padrão será o domínio local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

