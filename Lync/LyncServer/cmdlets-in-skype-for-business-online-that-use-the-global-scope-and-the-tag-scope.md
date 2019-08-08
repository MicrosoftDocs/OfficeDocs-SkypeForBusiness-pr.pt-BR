---
title: Cmdlets no Skype for Business online que usam o escopo global e o escopo de marca
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b274469f16ebb10338504afb2855e1c92774e545
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233096"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="8558d-102">Cmdlets no Skype for Business online que usam o escopo global e o escopo de marca</span><span class="sxs-lookup"><span data-stu-id="8558d-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="8558d-103">No Skype for Business Online, as políticas podem ser configuradas no *escopo global* ou no *escopo da marca* (ou no *escopo por usuário*).</span><span class="sxs-lookup"><span data-stu-id="8558d-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="8558d-104">Ao usar os cmdlets **Get-cs** , você não precisa especificar um escopo ou uma identidade.</span><span class="sxs-lookup"><span data-stu-id="8558d-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="8558d-105">Se você chamar um desses cmdlets sem parâmetros, todos os itens relevantes serão retornados.</span><span class="sxs-lookup"><span data-stu-id="8558d-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="8558d-106">Por exemplo, esse comando retorna informações sobre todas as suas políticas de acesso externo:</span><span class="sxs-lookup"><span data-stu-id="8558d-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="8558d-107">Você precisa incluir somente o parâmetro Identity ou o parâmetro Filter se desejar limitar os dados retornados.</span><span class="sxs-lookup"><span data-stu-id="8558d-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="8558d-108">Por exemplo, para retornar apenas a política global, use este comando:</span><span class="sxs-lookup"><span data-stu-id="8558d-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="8558d-109">Para retornar uma política por usuário com a identidade "RedmondAccessPolicy", use este comando:</span><span class="sxs-lookup"><span data-stu-id="8558d-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="8558d-110">Ao fazer referência a uma política por usuário, o <STRONG>prefixo</STRONG> da marca é opcional.</span><span class="sxs-lookup"><span data-stu-id="8558d-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="8558d-111">Essa sintaxe, que inclui o prefixo, também é válida:</span><span class="sxs-lookup"><span data-stu-id="8558d-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="8558d-112">Get-CsExternalAccessPolicy – marca de identidade: RedmondAccessPolicy "</span><span class="sxs-lookup"><span data-stu-id="8558d-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="8558d-113">Para retornar todas as políticas, exceto as políticas globais (ou seja, todas as políticas por usuário), use este comando:</span><span class="sxs-lookup"><span data-stu-id="8558d-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="8558d-114">Os cmdlets a seguir operam em relação ao escopo global e ao escopo por usuário (marca):</span><span class="sxs-lookup"><span data-stu-id="8558d-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="8558d-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8558d-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8558d-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8558d-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8558d-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8558d-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8558d-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8558d-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8558d-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8558d-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8558d-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8558d-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8558d-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8558d-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="8558d-122">Apesar do nome, planos de discagem, funcionamento em termos de funcionamento, políticas.</span><span class="sxs-lookup"><span data-stu-id="8558d-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="8558d-123">O <EM>plano</EM> de discagem do termo é usado em vez de, por exemplo, política de discagem, para preservar a terminologia usada com as versões anteriores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8558d-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="8558d-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="8558d-124">See Also</span></span>


[<span data-ttu-id="8558d-125">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8558d-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="8558d-126">[Os cmdlets do Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8558d-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

