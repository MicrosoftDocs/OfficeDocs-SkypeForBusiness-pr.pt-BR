---
title: Cmdlets no Skype for Business online que usam a identidade do usuário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 94c29eb2aadefcb6a9f3ca9b5c11a49f7e41167a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728121"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="172cf-102">Cmdlets no Skype for Business online que usam a identidade do usuário</span><span class="sxs-lookup"><span data-stu-id="172cf-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="172cf-103">No Skype for Business Online, há várias maneiras diferentes de fazer referência a uma identidade de usuário individual:</span><span class="sxs-lookup"><span data-stu-id="172cf-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="172cf-104">Use o nome de exibição dos serviços de domínio Active Directory do usuário.</span><span class="sxs-lookup"><span data-stu-id="172cf-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="172cf-105">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="172cf-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="172cf-106">Use o endereço SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="172cf-106">Use the user’s SIP address.</span></span> <span data-ttu-id="172cf-107">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="172cf-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="172cf-108">Use o UPN do usuário.</span><span class="sxs-lookup"><span data-stu-id="172cf-108">Use the user’s UPN.</span></span> <span data-ttu-id="172cf-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="172cf-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="172cf-110">Use o nome diferenciado dos serviços de domínio Active Directory do usuário.</span><span class="sxs-lookup"><span data-stu-id="172cf-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="172cf-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="172cf-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="172cf-112">Os cmdlets a seguir aceitam uma identidade de usuário:</span><span class="sxs-lookup"><span data-stu-id="172cf-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="172cf-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="172cf-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="172cf-125">Observe que você não precisa especificar uma identidade de usuário ao chamar um dos cmdlets **Get-cs** .</span><span class="sxs-lookup"><span data-stu-id="172cf-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="172cf-126">Nesse caso, os cmdlets retornam todas as instâncias do item especificado.</span><span class="sxs-lookup"><span data-stu-id="172cf-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="172cf-127">Por exemplo, esse comando retorna informações sobre todos os usuários que foram habilitados para o Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="172cf-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="172cf-128">O parâmetro Identity é necessário apenas se você quiser retornar informações para um usuário específico:</span><span class="sxs-lookup"><span data-stu-id="172cf-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="172cf-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="172cf-129">See Also</span></span>


[<span data-ttu-id="172cf-130">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="172cf-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="172cf-131">[Os cmdlets do Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="172cf-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

