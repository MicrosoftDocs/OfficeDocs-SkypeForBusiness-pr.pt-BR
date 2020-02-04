---
title: 'Lync Server 2013: Delegar permissões de configuração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 245fa0cb3bb5393f1d0f09a3f3b9c10176c015ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Delegar permissões de configuração no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-05_

Se você não quiser conceder associação ao grupo Administradores de domínio para usuários ou grupos que estão implantando o Lync Server 2013, você pode habilitar os membros do grupo RTCUniversalServerAdmins para executar o cmdlet **Enable-CsTopology** do Windows PowerShell em servidores que executam o Lync Server 2013. Por padrão, os membros do grupo RTCUniversalServerAdmins não têm a capacidade de executar esse cmdlet. Conceda direitos e permissões de administrador para executar **Enable-CsTopology** em servidores que executam o Lync Server usando o cmdlet **Grant-CsSetupPermission** e especificando uma unidade organizacional na qual os objetos de computador do servidor que executa o Lync Server 2013 estão localizados.

A preparação do domínio que ocorre quando você instala o Lync Server não adiciona automaticamente as permissões que permitem que os membros do grupo RTCUniversalServerAdmins executem o cmdlet Enable-CsTopology. Isso significa que, por padrão, você deve ser um administrador de domínio para habilitar uma topologia. Para dar aos membros do grupo RTCUniversalServerAdmins o direito de habilitar uma topologia, você deve executar o cmdlet Grant-CsSetupPermissions. Além disso, você precisará executar esse cmdlet em cada contêiner do Active Directory que abriga computadores que executam o Lync Server.

Lembre-se de que esse cmdlet concede somente permissões ao grupo RTCUniversalServerAdmins; o cmdlet não pode ser usado para conceder permissões a outros grupos de segurança ou a usuários individuais.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> é o cmdlet principal para permitir que os membros do grupo do RTCUniversalServerAdmins configurem e implantem o Lync Server 2013.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Para adicionar a capacidade de executar Enable-CsTopology ao grupo RTCUniversalServerAdmins

1.  Faça logon em um servidor como membro do grupo Domain admins do domínio no qual o usuário delegado irá executar **Enable-CsTopology**.

2.  Abra o Shell de gerenciamento do Lync Server 2013. O Shell de gerenciamento do Lync Server 2013 é instalado automaticamente em cada servidor front-end ou em qualquer computador onde as ferramentas administrativas do Lync Server 2013 tenham sido instaladas. Para obter detalhes sobre o Shell de gerenciamento do Lync Server 2013, consulte [Shell de gerenciamento do Lync server 2013](lync-server-2013-lync-server-management-shell.md) na documentação de operações.

3.  Execute o seguinte cmdlet do Shell de gerenciamento do Lync Server 2013:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Se a UO não estiver no nível superior, você deve fornecer o nome de domínio completo.

    
    </div>
    
    No exemplo a seguir, a UO é "Lync Servers", que está no domínio contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

