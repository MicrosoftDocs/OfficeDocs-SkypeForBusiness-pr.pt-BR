---
title: Cmdlets no Skype for Business online que usam o escopo global e o escopo da marca
description: Cmdlets no Skype for Business online que usam o escopo global e o escopo da marca.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba89ebe7322159027c5de765117afd366cb3dc23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545617"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="6ffc0-103">Cmdlets no Skype for Business online que usam o escopo global e o escopo da marca</span><span class="sxs-lookup"><span data-stu-id="6ffc0-103">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="6ffc0-104">No Skype for Business Online, as políticas podem ser configuradas no *escopo global* ou no *escopo de marca* (ou *escopo por usuário*).</span><span class="sxs-lookup"><span data-stu-id="6ffc0-104">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="6ffc0-105">Ao usar os cmdlets **Get-cs** , não é necessário especificar um escopo ou uma identidade.</span><span class="sxs-lookup"><span data-stu-id="6ffc0-105">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="6ffc0-106">Se você chamar um desses cmdlets sem qualquer parâmetro, todos os itens relevantes serão retornados.</span><span class="sxs-lookup"><span data-stu-id="6ffc0-106">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="6ffc0-107">Por exemplo, este comando retorna informações sobre todas as suas políticas de acesso externo:</span><span class="sxs-lookup"><span data-stu-id="6ffc0-107">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="6ffc0-108">Você precisa incluir apenas o parâmetro Identity ou o parâmetro Filter se quiser limitar os dados retornados.</span><span class="sxs-lookup"><span data-stu-id="6ffc0-108">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="6ffc0-109">Por exemplo, para retornar somente a política global, use este comando:</span><span class="sxs-lookup"><span data-stu-id="6ffc0-109">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="6ffc0-110">Para retornar uma política por usuário com a identidade "RedmondAccessPolicy", use este comando:</span><span class="sxs-lookup"><span data-stu-id="6ffc0-110">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="6ffc0-111">Ao fazer referência a uma política por usuário, o <STRONG>prefixo</STRONG> da marca é opcional.</span><span class="sxs-lookup"><span data-stu-id="6ffc0-111">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="6ffc0-112">Essa sintaxe, que inclui o prefixo, também é válida:</span><span class="sxs-lookup"><span data-stu-id="6ffc0-112">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="6ffc0-113">Marca Get-CsExternalAccessPolicy – Identity ": RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="6ffc0-113">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="6ffc0-114">Para retornar todas as políticas, exceto as políticas globais (ou seja, todas as políticas por usuário), use este comando:</span><span class="sxs-lookup"><span data-stu-id="6ffc0-114">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="6ffc0-115">Os cmdlets a seguir operam contra o escopo global e o escopo por usuário (marca):</span><span class="sxs-lookup"><span data-stu-id="6ffc0-115">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="6ffc0-116">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6ffc0-116">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6ffc0-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6ffc0-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6ffc0-118">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6ffc0-118">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6ffc0-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6ffc0-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6ffc0-120">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6ffc0-120">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6ffc0-121">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6ffc0-121">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="6ffc0-122">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6ffc0-122">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="6ffc0-123">Apesar do nome, os planos de discagem são funcionalmente falando, políticas.</span><span class="sxs-lookup"><span data-stu-id="6ffc0-123">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="6ffc0-124">O <EM>plano de discagem</EM> do termo é usado em vez de, por exemplo, a política de discagem, para preservar a terminologia usada com as versões anteriores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ffc0-124">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="6ffc0-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="6ffc0-125">See Also</span></span>


[<span data-ttu-id="6ffc0-126">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6ffc0-126">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="6ffc0-127">[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="6ffc0-127">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

