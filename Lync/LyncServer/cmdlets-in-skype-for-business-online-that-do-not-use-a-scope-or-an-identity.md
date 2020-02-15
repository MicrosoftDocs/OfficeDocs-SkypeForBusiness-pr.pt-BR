---
title: Cmdlets no Skype for Business online que não usam um escopo ou uma identidade
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad366315bbc4acf5afb417262da92a5683a084df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001726"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="55a17-102">Cmdlets no Skype for Business online que não usam um escopo ou uma identidade</span><span class="sxs-lookup"><span data-stu-id="55a17-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="55a17-103">Os cmdlets usados ao modificar as listas permitidas e listas bloqueadas (listas que determinam a quais organizações externas seus usuários têm permissão para se comunicar) não usam um escopo ou uma identidade.</span><span class="sxs-lookup"><span data-stu-id="55a17-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="55a17-104">Na verdade, o cmdlet **New-CsEdgeAllowAllKnownDomains** não tem nenhum parâmetro de qualquer outra função.</span><span class="sxs-lookup"><span data-stu-id="55a17-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="55a17-105">Os cmdlets que não usam um escopo ou uma identidade são:</span><span class="sxs-lookup"><span data-stu-id="55a17-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="55a17-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="55a17-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="55a17-107">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="55a17-107">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="55a17-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="55a17-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="55a17-109">Observe que, com o cmdlet **New-CsEdgeAllowList** e o cmdlet **New-CsEdgeDomainPattern** , você deve incluir o parâmetro Domain.</span><span class="sxs-lookup"><span data-stu-id="55a17-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="55a17-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="55a17-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="55a17-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="55a17-111">See Also</span></span>


[<span data-ttu-id="55a17-112">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="55a17-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="55a17-113">[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="55a17-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

