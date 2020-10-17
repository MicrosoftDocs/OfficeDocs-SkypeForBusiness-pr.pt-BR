---
title: 'Lync Server 2013: cmdlets de conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing cmdlets
ms:assetid: 0718f82a-91c4-466f-8443-a85002deaa48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415630(v=OCS.15)
ms:contentKeyID: 48183320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63b24ad9b6203f3b73033e1c4f80dc8252d0f67
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514538"
---
# <a name="dial-in-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="b8f3d-102">Cmdlets de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8f3d-102">Dial-in conferencing cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8f3d-103">_**Última modificação do tópico:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="b8f3d-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="b8f3d-104">A conferência discada permite aos usuários utilizar um telefone "comum" (ou seja, um dispositivo da rede telefônica pública comutada) para participar da parte de áudio de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="b8f3d-104">Dial-in conferencing provides a way for users to use a "regular" telephone (that is, a device on the public switched telephone network) to join the audio portion of a conference.</span></span>

<div>

## <a name="dial-in-conferencing-cmdlets"></a><span data-ttu-id="b8f3d-105">Cmdlets de conferência discada</span><span class="sxs-lookup"><span data-stu-id="b8f3d-105">Dial-In Conferencing Cmdlets</span></span>

<span data-ttu-id="b8f3d-p101">Se a intenção for não permitir a conferência discada, é possível desabilitar esse recurso usando o cmdlet Set-CsConferencingPolicy e definindo a propriedade EnableDialInConferencing como Falso. Por padrão, todos os usuários podem coordenar reuniões que incluam a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="b8f3d-p101">If you do not want to allow dial-in conferencing you can disable this capability by using the Set-CsConferencingPolicy cmdlet and setting the EnableDialInConferencing property to False. By default, all users are allowed to host meetings that include dial-in conferencing.</span></span>

<span data-ttu-id="b8f3d-108">**Conferência discada**</span><span class="sxs-lookup"><span data-stu-id="b8f3d-108">**Dial-In Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-109">[Get-CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-109">[Get-CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-110">[Move-CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-110">[Move-CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-111">[New-CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-111">[New-CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-112">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-112">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b8f3d-113">[Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-113">[Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b8f3d-114">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-114">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-115">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-115">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-116">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-116">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-117">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-117">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b8f3d-118">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-118">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-119">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-119">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-120">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-120">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-121">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-121">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b8f3d-122">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-122">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-123">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-123">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-124">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-124">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b8f3d-125">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-125">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b8f3d-126">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b8f3d-126">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b8f3d-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="b8f3d-127">See Also</span></span>


[<span data-ttu-id="b8f3d-128">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="b8f3d-128">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

