---
title: Cmdlets no Skype for Business online que usam uma identidade de provedor de conferência
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e36c04b2f5728ff624a280696bacf4eacb032967
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836093"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="2db11-102">Cmdlets no Skype for Business online que usam uma identidade de provedor de conferência</span><span class="sxs-lookup"><span data-stu-id="2db11-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="2db11-103">Para retornar informações sobre todos os provedores de serviços de audioconferência com os quais a sua organização se contratadou, você pode simplesmente chamar o cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) sem parâmetros:</span><span class="sxs-lookup"><span data-stu-id="2db11-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="2db11-104">Se você quiser limitar os dados retornados a um único provedor (neste exemplo, os serviços de áudio da Contoso do provedor), use o parâmetro Identity:</span><span class="sxs-lookup"><span data-stu-id="2db11-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="2db11-105">Há apenas um cmdlet do Skype for Business online que aceita uma ID do provedor de serviços de audioconferência:</span><span class="sxs-lookup"><span data-stu-id="2db11-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="2db11-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="2db11-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="2db11-107">Confira também</span><span class="sxs-lookup"><span data-stu-id="2db11-107">See Also</span></span>


[<span data-ttu-id="2db11-108">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2db11-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="2db11-109">[Os cmdlets do Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="2db11-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

