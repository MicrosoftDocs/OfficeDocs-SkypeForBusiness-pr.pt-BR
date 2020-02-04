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

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a><span data-ttu-id="a7ab2-102">Cmdlets de Federação e acesso externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7ab2-102">Federation and external access cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7ab2-103">_**Tópico da última modificação:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="a7ab2-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="a7ab2-104">A Federação e o acesso externo fornecem duas funcionalidades importantes: a Federação permite que os usuários se comuniquem com pessoas de fora da sua organização, enquanto o acesso externo permite que os usuários se conectem ao Microsoft Lync Server 2013 de fora da rede interna.</span><span class="sxs-lookup"><span data-stu-id="a7ab2-104">Federation and external access provide two important capabilities: federation enables users to communicate with people outside your organization, while external access enables users to connect to Microsoft Lync Server 2013 from outside the internal network.</span></span> <span data-ttu-id="a7ab2-105">Os cmdlets disponíveis para gerenciamento de Federação e acesso externo no Lync Server 2013 permitem determinar quem seus usuários podem (e não pode) se comunicar e determinar se esses usuários podem ou não conectar ao Lync Server sem precisar fazer logon no Internal Network.</span><span class="sxs-lookup"><span data-stu-id="a7ab2-105">The cmdlets available for managing federation and external access in Lync Server 2013 let you determine who your users can (and cannot) communicate with, and determine whether or not those users can connect to Lync Server without having to log on to the internal network.</span></span>

<div>

## <a name="federation-and-external-access-cmdlets"></a><span data-ttu-id="a7ab2-106">Cmdlets de Federação e acesso externo</span><span class="sxs-lookup"><span data-stu-id="a7ab2-106">Federation and External Access Cmdlets</span></span>

<span data-ttu-id="a7ab2-107">A maioria das tarefas de gerenciamento que se aplicam à Federação e ao acesso externo podem ser realizadas a partir do painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7ab2-107">Most management tasks that apply to federation and external access can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="a7ab2-108">Essas mesmas tarefas podem ser executadas usando cmdlets do Shell de gerenciamento do Lync Server ou de dentro de um script; usar um script permite automatizar determinadas tarefas.</span><span class="sxs-lookup"><span data-stu-id="a7ab2-108">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="a7ab2-109">Veja a seguir uma lista de cmdlets relacionados diretamente ao gerenciamento de Federação e acesso externo:</span><span class="sxs-lookup"><span data-stu-id="a7ab2-109">The following is a list of cmdlets that relate directly to managing federation and external access:</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-110">[Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-110">[Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-111">[New-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-111">[New-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-112">[Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-112">[Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-113">[Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-113">[Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7ab2-114">[Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-114">[Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-115">[New-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-115">[New-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-116">[Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-116">[Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-117">[Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-117">[Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7ab2-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-119">[Grant CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-119">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-120">[New-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-120">[New-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-121">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-121">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-122">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-122">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="a7ab2-123">[Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-123">[Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))</span></span>

  - <span data-ttu-id="a7ab2-124">[New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-124">[New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))</span></span>

  - <span data-ttu-id="a7ab2-125">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-125">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))</span></span>

  - <span data-ttu-id="a7ab2-126">[Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-126">[Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7ab2-127">[Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-127">[Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-128">[Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-128">[Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-129">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-129">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-130">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-130">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-131">[Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-131">[Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-132">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-132">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7ab2-133">[Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-133">[Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-134">[Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-134">[Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-135">[Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-135">[Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-136">[New-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-136">[New-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-137">[Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-137">[Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7ab2-138">[Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-138">[Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7ab2-139">[Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-139">[Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="a7ab2-140">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-140">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span></span>

  - <span data-ttu-id="a7ab2-141">[New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-141">[New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))</span></span>

  - <span data-ttu-id="a7ab2-142">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-142">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))</span></span>

  - <span data-ttu-id="a7ab2-143">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-143">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="a7ab2-144">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-144">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span></span>

  - <span data-ttu-id="a7ab2-145">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-145">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="a7ab2-146">[Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7ab2-146">[Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7ab2-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="a7ab2-147">See Also</span></span>


[<span data-ttu-id="a7ab2-148">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="a7ab2-148">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

