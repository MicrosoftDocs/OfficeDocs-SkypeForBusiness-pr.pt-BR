---
title: 'Lync Server 2013: cmdlets de gerenciamento de usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a841daae6a811b6668c61ac1befca045fb73b03f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="b19c6-102">Cmdlets de gerenciamento de usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b19c6-102">User management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b19c6-103">_**Tópico da última modificação:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="b19c6-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="b19c6-104">Os cmdlets de gerenciamento de usuários incluídos no Microsoft Lync Server 2013 permitem que você habilite, desabilite e modifique contas de usuário do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b19c6-104">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="b19c6-105">Cmdlets de gerenciamento de usuários</span><span class="sxs-lookup"><span data-stu-id="b19c6-105">User Management Cmdlets</span></span>

<span data-ttu-id="b19c6-106">A maioria das tarefas de gerenciamento que se aplicam a usuários e contas de usuário podem ser executadas no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b19c6-106">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="b19c6-107">As exceções primárias são os cmdlets que lidam com provedores de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="b19c6-107">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="b19c6-108">As tarefas de gerenciamento de usuários podem ser realizadas usando cmdlets do Shell de gerenciamento do Lync Server ou de dentro de um script.</span><span class="sxs-lookup"><span data-stu-id="b19c6-108">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="b19c6-109">Usando um script, você pode automatizar determinadas tarefas.</span><span class="sxs-lookup"><span data-stu-id="b19c6-109">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="b19c6-110">Veja a seguir uma lista de cmdlets relacionados diretamente ao gerenciamento de usuários e contas de usuário:</span><span class="sxs-lookup"><span data-stu-id="b19c6-110">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="b19c6-111">Get-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="b19c6-111">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="b19c6-112">Get-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="b19c6-112">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="b19c6-113">Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="b19c6-113">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="b19c6-114">Get-CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="b19c6-114">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="b19c6-115">Invoke-CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="b19c6-115">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="b19c6-116">Debug-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="b19c6-116">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="b19c6-117">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="b19c6-117">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="b19c6-118">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="b19c6-118">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="b19c6-119">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="b19c6-119">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="b19c6-120">Get-CsUser</span><span class="sxs-lookup"><span data-stu-id="b19c6-120">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="b19c6-121">Mover-CsUser</span><span class="sxs-lookup"><span data-stu-id="b19c6-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="b19c6-122">Set-CsUser</span><span class="sxs-lookup"><span data-stu-id="b19c6-122">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="b19c6-123">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="b19c6-123">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="b19c6-124">Remove-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="b19c6-124">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="b19c6-125">Set-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="b19c6-125">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="b19c6-126">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="b19c6-126">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="b19c6-127">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="b19c6-127">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="b19c6-128">Get-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="b19c6-128">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="b19c6-129">Grant-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="b19c6-129">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="b19c6-130">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="b19c6-130">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="b19c6-131">Remove-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="b19c6-131">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="b19c6-132">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="b19c6-132">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b19c6-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="b19c6-133">See Also</span></span>


[<span data-ttu-id="b19c6-134">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="b19c6-134">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

