---
title: 'Lync Server 2013: concedendo permissões de configuração'
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
ms.openlocfilehash: 647590131702addb8363b42aaa7d49e299b63a47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>Concedendo permissões de configuração no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-08-27_

Você pode usar o cmdlet **Grant-CsSetupPermission** para adicionar permissões de leitura, gravação, ReadSPN e WriteSPN ao grupo RTCUniversalServerAdmins para uma unidade organizacional (ou) especificada do Active Directory. Em seguida, os membros do grupo RTCUniversalServerAdmins no OU podem instalar servidores que executam o Lync Server 2013 no domínio especificado sem ser membros do grupo de administradores de domínio.

Use o cmdlet do **Test-CsSetupPermission** para verificar as permissões que você configurou usando o cmdlet **Grant-CsSetupPermission**.

Você pode usar o cmdlet **Revoke-CsSetupPermission** para remover as permissões que você concedeu usando o cmdlet **Grant-CsSetupPermission**.

<div>

## <a name="to-grant-setup-permissions"></a>Para conceder permissões de configuração

1.  Faça logon em um computador que executa o Lync Server 2013 no domínio onde você deseja conceder permissões de configuração. Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio específico (por exemplo, CN=computers). De outro modo, você pode especificar esse parâmetro como o nome diferenciado (DN) de UO completo (por exemplo, "CN=computers,DC=Contoso,DC=com"). No último caso, você de especificar um DN de OU que seja consistente com o domínio especificado.
    
    Se você não especificar o parâmetro de Domínio, o valor padrão é o domínio local.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>Para verificar as permissões de configuração

1.  Faça logon em um computador que executa o Lync Server 2013 no domínio em que você deseja verificar as permissões de configuração concedidas usando o cmdlet **Grant-CsSetupPermission** . Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio específico (por exemplo, CN=computers). De outro modo, você pode especificar esse parâmetro como o nome diferenciado (DN) de UO completo (por exemplo, "CN=computers,DC=Contoso,DC=com"). No último caso, você de especificar um DN de OU que seja consistente com o domínio especificado.
    
    Se você não especificar o parâmetro de Domínio, o valor padrão é o domínio local.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>Para revogar as permissões de configuração

1.  Faça logon em um computador que executa o Lync Server 2013 no domínio onde você deseja revogar as permissões de instalação concedidas pelo cmdlet **Grant-CsSetupPermission** . Use uma conta que seja membro do grupo Administradores de Domínio ou do grupo Administradores de Empresa se a UO estiver em um domínio filho diferente.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Você pode especificar o parâmetro ComputerOu como relativo ao contexto de nomenclatura padrão do domínio específico (por exemplo, CN=computers). De outro modo, você pode especificar esse parâmetro como o nome diferenciado (DN) de UO completo (por exemplo, "CN=computers,DC=Contoso,DC=com"). No último caso, você de especificar um DN de OU que seja consistente com o domínio especificado.
    
    Se você não especificar o parâmetro de Domínio, o valor padrão é o domínio local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

