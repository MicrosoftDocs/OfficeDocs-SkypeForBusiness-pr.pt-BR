---
title: 'Lync Server 2013: cmdlets de presença e mensagens instantâneas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d96b8971bb25898e9e8b02403b0f8cd5447681c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a>Cmdlets de presença e mensagens instantâneas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-26_

O recurso de mensagens instantâneas (IM) e os cmdlets de presença permitem que você gerencie esses recursos de cliente por meio do Windows PowerShell. Você pode definir políticas de presença que se aplicam a usuários em escopo global, de site ou por usuário. Você também pode configurar vários recursos de privacidade e mensagens instantâneas.

<div>

## <a name="im-and-presence-cmdlets"></a>Cmdlets de presença e mensagens instantâneas

A configuração IM e a presença, use os seguintes cmdlets:

  - <span></span>  
    [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))

  - <span></span>  
    [Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))

  - <span></span>  
    [New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))

  - <span></span>  
    [Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))

  - <span></span>  
    [Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))

<!-- end list -->

  - [Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))

  - [New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))

  - [Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))

  - [Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))

  - <span></span>  
    [New-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))

  - <span></span>  
    [Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))

  - <span></span>  
    [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))

  - <span></span>  
    [New-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))

  - <span></span>  
    [Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))

  - <span></span>  
    [Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))

  - <span></span>  
    [New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))

  - <span></span>  
    [Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))

  - <span></span>  
    [Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))

  - <span></span>  
    [New-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))

  - <span></span>  
    [Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))

  - <span></span>  
    [Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Confira também


[Cmdlets de gerenciamento de cliente no Lync Server 2013](lync-server-2013-client-management-cmdlets.md)  


[Blog do PowerShell do Lync Server](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

