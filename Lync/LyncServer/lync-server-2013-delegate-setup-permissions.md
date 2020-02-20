---
title: 'Lync Server 2013: delegar permissões de configuração'
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
ms.openlocfilehash: d5660a78bcad4d125fbf32204331b433978a831d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Delegar permissões de configuração no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-05_

Se não quiser conceder a associação ao grupo Administradores de domínio para usuários ou grupos que estão implantando o Lync Server 2013, você pode habilitar os membros do grupo RTCUniversalServerAdmins para executar o cmdlet **Enable-CsTopology** do Windows PowerShell em servidores que executam o Lync Server 2013. Por padrão, os membros do grupo RTCUniversalServerAdmins não podem executar esse cmdlet. Conceda permissões e direitos de administrador para executar **Enable-CsTopology** em servidores que executam o Lync Server usando o cmdlet **Grant-CsSetupPermission** e especificando uma UO (unidade organizacional) onde os objetos de computador do servidor que executa o Lync Server 2013 estão localizados.

A preparação do domínio que ocorre quando você instala o Lync Server não adiciona automaticamente as permissões que permitem que os membros do grupo RTCUniversalServerAdmins executem o cmdlet Enable-CsTopology. Isso significa que, por padrão, é necessário que você seja um administrador do domínio para poder habilitar uma topologia. Para dar aos membros do grupo RTCUniversalServerAdmins o direito de habilitar uma topologia, você deve executar o cmdlet Grant-CsSetupPermissions. Além disso, você precisará executar esse cmdlet em cada contêiner do Active Directory que hospeda computadores que executam o Lync Server.

Tenha em mente que esse cmdlet apenas concede permissões ao grupo RTCUniversalServerAdmins; ele não pode ser utilizado para conceder permissões aos grupos de segurança ou a usuários individuais.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> é o cmdlet principal para permitir que os membros do grupo RTCUniversalServerAdmins configurem e implantem o Lync Server 2013.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Para adicionar a habilidade de executar o cmdlet Enable-CsTopology ao grupo RTCUniversalServerAdmins

1.  Faça logon em um servidor como membro do grupo Administradores de Domínio para o domínio em que o usuário delegado executará o cmdlet **Enable-CsTopology**.

2.  Abra o Shell de gerenciamento do Lync Server 2013. O Shell de gerenciamento do Lync Server 2013 é instalado automaticamente em cada servidor de front-end ou em qualquer computador onde as ferramentas administrativas do Lync Server 2013 tenham sido instaladas. Para obter detalhes sobre o Shell de gerenciamento do Lync Server 2013, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) na documentação operações.

3.  Execute o seguinte cmdlet no Shell de gerenciamento do Lync Server 2013:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Se OU não for o nível superior, você deve fornecer o nome de domínio completo.

    
    </div>
    
    No exemplo a seguir, a UO é o "Lync Server", que está no domínio contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

