---
title: Cmdlets no Skype for Business online que usam uma identidade do provedor de conferência
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0ae3167b1cb6c83b46e4f9d4846e8863b43515d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001716"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="ee7cf-102">Cmdlets no Skype for Business online que usam uma identidade do provedor de conferência</span><span class="sxs-lookup"><span data-stu-id="ee7cf-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="ee7cf-103">Para retornar informações sobre todos os provedores de audioconferência que sua organização tenha contratado, você pode simplesmente chamar o cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) sem nenhum parâmetro:</span><span class="sxs-lookup"><span data-stu-id="ee7cf-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="ee7cf-104">Se você quiser limitar os dados retornados a um único provedor (neste exemplo, os serviços de áudio da Contoso do provedor), use o parâmetro Identity:</span><span class="sxs-lookup"><span data-stu-id="ee7cf-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="ee7cf-105">Há apenas um cmdlet do Skype for Business online que aceita uma ID de provedor de audioconferência:</span><span class="sxs-lookup"><span data-stu-id="ee7cf-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="ee7cf-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ee7cf-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="ee7cf-107">Confira também</span><span class="sxs-lookup"><span data-stu-id="ee7cf-107">See Also</span></span>


[<span data-ttu-id="ee7cf-108">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ee7cf-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="ee7cf-109">[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ee7cf-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

