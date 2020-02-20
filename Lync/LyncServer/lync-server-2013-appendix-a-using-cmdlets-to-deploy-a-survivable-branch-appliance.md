---
title: 'Lync Server 2013: Apêndice A: usando cmdlets para implantar um aparelho de filial persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 107bc5f9b39b1d62db0cba6960b60307c82831fb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>Apêndice A: usando cmdlets para implantar um aparelho de filial persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-07_

Este tópico descreve como implantar um aparelho de filial persistente usando o Shell de gerenciamento do Lync Server. Execute este procedimento no local central.

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>Para implantar um aparelho de filial persistente remotamente

1.  Siga o procedimento em [adicionar sites de filial à sua topologia no Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) para adicionar um novo site de filial.

2.  Ingresse o site da filial no domínio.

3.  Adicione o grupo RTCUniversalSBATechnicians ao grupo de Administradores local.

4.  Reinicie o servidor e faça o logon nele como um membro do grupo RTCUniversalSBATechnicians.

5.  No Shell de gerenciamento do Lync Server, digite os seguintes comandos, substituindo os espaços reservados pelas informações corretas da sua organização:
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

