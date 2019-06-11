---
title: 'Lync Server 2013: habilitar ou desabilitar um dispositivo de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 435c119e81923ec19e4f8a1e0d3fc35180b8508a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>Habilitar ou desabilitar um dispositivo de conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-20_

Habilite e desabilite um dispositivo de conferência usando o cmdlet **Enable-CsMeetingRoom** e o cmdlet **Disable-CsMeetingRoom** . Esses cmdlets podem ser executados no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Microsoft Lync Server 2010 usando o PowerShell remoto" em.



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>Habilitando um dispositivo de conferência

  - Para habilitar um dispositivo de conferência, use o cmdlet **Enable-CsMeetingRoom** . Ao habilitar um dispositivo de conferência, você deve incluir uma) a identidade do dispositivo de conferência, b) o pool de registrador onde a conta da sala será hospedada e c) o endereço SIP a ser atribuído a essa conta.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>Desativando um dispositivo de conferência

  - Para desabilitar um dispositivo de conferência, use o cmdlet **Disable-CsMeetingRoom** . Certifique-se de especificar a identidade do dispositivo de conferência a ser desativado:
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

Para obter detalhes, consulte os tópicos da ajuda para o cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e o cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

