---
title: 'Lync Server 2013: habilitar ou desabilitar um dispositivo de conferência'
description: 'Lync Server 2013: habilitar ou desabilitar um dispositivo de conferência.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 761bc19536c889cced68ff586753f6800df0da59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558077"
---
# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="b7ded-103">Habilitar ou desabilitar um dispositivo de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7ded-103">Enable or disable a conferencing device in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7ded-104">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b7ded-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b7ded-105">Habilite e desabilite um dispositivo de conferência usando o cmdlet **Enable-CsMeetingRoom** e o cmdlet **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="b7ded-105">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="b7ded-106">Esses cmdlets podem ser executados a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7ded-106">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7ded-107">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="b7ded-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="b7ded-108">Habilitando um dispositivo de conferência</span><span class="sxs-lookup"><span data-stu-id="b7ded-108">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="b7ded-109">Para habilitar um dispositivo de conferência, use o cmdlet **Enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="b7ded-109">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="b7ded-110">Ao habilitar um dispositivo de conferência, você deve incluir uma, a identidade do dispositivo de conferência, b) o pool de registradores onde a conta da sala será hospedada e c) o endereço SIP a ser atribuído a essa conta.</span><span class="sxs-lookup"><span data-stu-id="b7ded-110">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="b7ded-111">Desabilitando um dispositivo de conferência</span><span class="sxs-lookup"><span data-stu-id="b7ded-111">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="b7ded-112">Para desabilitar um dispositivo de conferência, use o cmdlet **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="b7ded-112">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="b7ded-113">Verifique se você especificou a identidade do dispositivo de conferência a ser desabilitado:</span><span class="sxs-lookup"><span data-stu-id="b7ded-113">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="b7ded-114">Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e o cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="b7ded-114">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

