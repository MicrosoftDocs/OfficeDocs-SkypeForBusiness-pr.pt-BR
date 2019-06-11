---
title: 'Lync Server 2013: cmdlets do aplicativo de estacionamento de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park application cmdlets
ms:assetid: 30cc001f-b29e-4d44-bad7-65e1133e67b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415639(v=OCS.15)
ms:contentKeyID: 48183764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0530cdd5f9c9fdb7997b6c3576ca0f1280436458
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-application-cmdlets-in-lync-server-2013"></a><span data-ttu-id="1bcad-102">Cmdlets do aplicativo Call Park no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bcad-102">Call Park application cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bcad-103">_**Tópico da última modificação:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="1bcad-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="1bcad-104">O aplicativo de estacionamento de chamadas permite que o usuário faça uma chamada em espera e, em seguida, recupere essa chamada de outro telefone.</span><span class="sxs-lookup"><span data-stu-id="1bcad-104">Call Park application allows a user to place a call on hold, then retrieve that call from a different phone.</span></span> <span data-ttu-id="1bcad-105">Use estes cmdlets para definir configurações para órbitas do parque de chamadas e do aplicativo de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1bcad-105">Use these cmdlets to configure settings for call park orbits and the Call Park application.</span></span>

<div>

## <a name="call-park-application-cmdlets"></a><span data-ttu-id="1bcad-106">Cmdlets do aplicativo Call Park</span><span class="sxs-lookup"><span data-stu-id="1bcad-106">Call Park Application Cmdlets</span></span>

<span data-ttu-id="1bcad-107">Os cmdlets a seguir podem ser usados para gerenciar o aplicativo parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1bcad-107">The following cmdlets can be used to manage Call Park application.</span></span>

<span data-ttu-id="1bcad-108">**Aplicativo de estacionamento de chamadas**</span><span class="sxs-lookup"><span data-stu-id="1bcad-108">**Call Park Application**</span></span>

  - <span></span>  
    <span data-ttu-id="1bcad-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bcad-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bcad-110">[New-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bcad-110">[New-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bcad-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bcad-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bcad-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bcad-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1bcad-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bcad-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1bcad-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bcad-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bcad-115">[New-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bcad-115">[New-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bcad-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bcad-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bcad-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bcad-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1bcad-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="1bcad-118">See Also</span></span>


[<span data-ttu-id="1bcad-119">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="1bcad-119">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

