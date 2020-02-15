---
title: 'Lync Server 2013: habilitar ou desabilitar um dispositivo de conferência'
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
ms.openlocfilehash: 3eb79f77bd6e99d36b1a6c9c9feb67f697e40f1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="8194c-102">Habilitar ou desabilitar um dispositivo de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8194c-102">Enable or disable a conferencing device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8194c-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8194c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8194c-104">Habilite e desabilite um dispositivo de conferência usando o cmdlet **Enable-CsMeetingRoom** e o cmdlet **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="8194c-104">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="8194c-105">Esses cmdlets podem ser executados a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8194c-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8194c-106">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="8194c-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="8194c-107">Habilitando um dispositivo de conferência</span><span class="sxs-lookup"><span data-stu-id="8194c-107">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="8194c-108">Para habilitar um dispositivo de conferência, use o cmdlet **Enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="8194c-108">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="8194c-109">Ao habilitar um dispositivo de conferência, você deve incluir uma, a identidade do dispositivo de conferência, b) o pool de registradores onde a conta da sala será hospedada e c) o endereço SIP a ser atribuído a essa conta.</span><span class="sxs-lookup"><span data-stu-id="8194c-109">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="8194c-110">Desabilitando um dispositivo de conferência</span><span class="sxs-lookup"><span data-stu-id="8194c-110">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="8194c-111">Para desabilitar um dispositivo de conferência, use o cmdlet **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="8194c-111">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="8194c-112">Verifique se você especificou a identidade do dispositivo de conferência a ser desabilitado:</span><span class="sxs-lookup"><span data-stu-id="8194c-112">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="8194c-113">Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e o cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="8194c-113">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

