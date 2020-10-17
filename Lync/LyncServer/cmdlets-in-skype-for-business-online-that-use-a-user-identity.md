---
title: Cmdlets no Skype for Business online que usam uma identidade de usuário
description: Cmdlets no Skype for Business online que usam uma identidade de usuário.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f838317f8b2779de862eb2df82ae1b348871e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545647"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="46afb-103">Cmdlets no Skype for Business online que usam uma identidade de usuário</span><span class="sxs-lookup"><span data-stu-id="46afb-103">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="46afb-104">No Skype for Business Online, há várias maneiras diferentes de fazer referência a uma identidade de usuário individual:</span><span class="sxs-lookup"><span data-stu-id="46afb-104">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="46afb-105">Use o nome de exibição dos serviços de domínio do Active Directory do usuário.</span><span class="sxs-lookup"><span data-stu-id="46afb-105">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="46afb-106">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="46afb-106">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="46afb-107">Use o endereço SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="46afb-107">Use the user’s SIP address.</span></span> <span data-ttu-id="46afb-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="46afb-108">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="46afb-109">Use o UPN do usuário.</span><span class="sxs-lookup"><span data-stu-id="46afb-109">Use the user’s UPN.</span></span> <span data-ttu-id="46afb-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="46afb-110">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="46afb-111">Use o nome diferenciado dos serviços de domínio do Active Directory do usuário.</span><span class="sxs-lookup"><span data-stu-id="46afb-111">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="46afb-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="46afb-112">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="46afb-113">Os cmdlets a seguir aceitam uma identidade do usuário:</span><span class="sxs-lookup"><span data-stu-id="46afb-113">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="46afb-114">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-114">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-115">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-115">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-116">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-116">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-117">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-117">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-118">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-118">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-119">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-119">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-120">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-120">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-121">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-121">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-122">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-122">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-123">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-123">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-124">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-124">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46afb-125">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-125">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="46afb-126">Observe que você não precisa especificar uma identidade de usuário ao chamar um dos cmdlets **Get-cs** .</span><span class="sxs-lookup"><span data-stu-id="46afb-126">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="46afb-127">Nesse caso, os cmdlets retornam todas as instâncias do item especificado.</span><span class="sxs-lookup"><span data-stu-id="46afb-127">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="46afb-128">Por exemplo, este comando retorna informações sobre todos os usuários que foram habilitados para o Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="46afb-128">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="46afb-129">O parâmetro Identity só será necessário se você quiser retornar informações de um usuário específico:</span><span class="sxs-lookup"><span data-stu-id="46afb-129">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="46afb-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="46afb-130">See Also</span></span>


[<span data-ttu-id="46afb-131">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="46afb-131">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="46afb-132">[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46afb-132">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

