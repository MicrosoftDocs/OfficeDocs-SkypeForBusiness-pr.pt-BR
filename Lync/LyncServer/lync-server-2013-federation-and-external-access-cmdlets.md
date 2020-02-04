---
title: 'Lync Server 2013: cmdlets de Federação e acesso externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b206d8de27f2cdeebab5db0c125012c2a29c65b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>Cmdlets de Federação e acesso externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-26_

A Federação e o acesso externo fornecem duas funcionalidades importantes: a Federação permite que os usuários se comuniquem com pessoas de fora da sua organização, enquanto o acesso externo permite que os usuários se conectem ao Microsoft Lync Server 2013 de fora da rede interna. Os cmdlets disponíveis para gerenciamento de Federação e acesso externo no Lync Server 2013 permitem determinar quem seus usuários podem (e não pode) se comunicar e determinar se esses usuários podem ou não conectar ao Lync Server sem precisar fazer logon no Internal Network.

<div>

## <a name="federation-and-external-access-cmdlets"></a>Cmdlets de Federação e acesso externo

A maioria das tarefas de gerenciamento que se aplicam à Federação e ao acesso externo podem ser realizadas a partir do painel de controle do Lync Server. Essas mesmas tarefas podem ser executadas usando cmdlets do Shell de gerenciamento do Lync Server ou de dentro de um script; usar um script permite automatizar determinadas tarefas. Veja a seguir uma lista de cmdlets relacionados diretamente ao gerenciamento de Federação e acesso externo:

  - <span></span>  
    [Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))

  - <span></span>  
    [New-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))

  - <span></span>  
    [Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))

  - <span></span>  
    [Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))

  - <span></span>  
    [New-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))

  - <span></span>  
    [Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))

  - <span></span>  
    [Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))

  - <span></span>  
    [Grant CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))

  - <span></span>  
    [New-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))

  - <span></span>  
    [Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))

  - [New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))

  - [Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))

  - [Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))

  - <span></span>  
    [Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))

  - <span></span>  
    [Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))

  - <span></span>  
    [New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))

  - <span></span>  
    [Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))

  - <span></span>  
    [Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))

  - <span></span>  
    [Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))

  - <span></span>  
    [Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))

  - <span></span>  
    [New-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))

  - <span></span>  
    [Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))

  - <span></span>  
    [Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))

  - [New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))

  - [Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))

  - [Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Confira também


[Blog do PowerShell do Lync Server](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

