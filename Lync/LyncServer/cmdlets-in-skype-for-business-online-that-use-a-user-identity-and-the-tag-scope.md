---
title: Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5319d527c859d239cd58eb5561d82a0b47a322e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001436"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="3326c-102">Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca</span><span class="sxs-lookup"><span data-stu-id="3326c-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="3326c-103">Os cmdlets **Grant-cs** (usados para atribuir políticas aos usuários) exigem dois identificadores: uma identidade de usuário (o parâmetro Identity) e a identidade de uma política por usuário (o parâmetro PolicyName).</span><span class="sxs-lookup"><span data-stu-id="3326c-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="3326c-104">Por exemplo, para atribuir a política de voz, RedmondVoicePolicy, ao usuário Ken Myer, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3326c-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="3326c-105">Há duas coisas que você deve ter em mente ao atribuir políticas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="3326c-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="3326c-106">Primeiro, somente as políticas por usuário podem ser atribuídas.</span><span class="sxs-lookup"><span data-stu-id="3326c-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="3326c-107">Você não pode atribuir a política global a um usuário.</span><span class="sxs-lookup"><span data-stu-id="3326c-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="3326c-108">Por exemplo, este comando falhará:</span><span class="sxs-lookup"><span data-stu-id="3326c-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="3326c-109">Esse comando falha porque não há necessidade de atribuir a política global.</span><span class="sxs-lookup"><span data-stu-id="3326c-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="3326c-110">Se você quiser gerenciar um usuário usando a política global, certifique-se de que você não atribui esse usuário a uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="3326c-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="3326c-111">Se nenhuma política por usuário tiver sido atribuída a um usuário, o usuário será automaticamente gerenciado usando a política global.</span><span class="sxs-lookup"><span data-stu-id="3326c-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="3326c-112">E se o usuário tiver sido atribuído anteriormente a uma política por usuário e se você quiser cancelar a atribuição dessa política e fazer com que o usuário seja gerenciado pela política global?</span><span class="sxs-lookup"><span data-stu-id="3326c-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="3326c-113">Nesse caso, você primeiro usará a seguinte sintaxe, que cancelará a atribuição de uma política por usuário concedendo a esse usuário uma política nula:</span><span class="sxs-lookup"><span data-stu-id="3326c-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="3326c-114">Grant-CsVoicePolicy – Identity "Ken Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="3326c-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="3326c-115">Em segundo lugar, tenha em mente que as políticas por usuário são criadas no escopo da marca.</span><span class="sxs-lookup"><span data-stu-id="3326c-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="3326c-116">No entanto, você pode omitir o **prefixo** da marca ao especificar um nome de política.</span><span class="sxs-lookup"><span data-stu-id="3326c-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="3326c-117">Esses dois comandos são idênticos:</span><span class="sxs-lookup"><span data-stu-id="3326c-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="3326c-118">Se você quiser retornar as identidades para todas as suas políticas por usuário (ou, pelo menos, todas as políticas por usuário do tipo especificado, como políticas de voz), use um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="3326c-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="3326c-119">Os cmdlets a seguir usam uma identidade de usuário e o escopo de marca:</span><span class="sxs-lookup"><span data-stu-id="3326c-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="3326c-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3326c-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3326c-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3326c-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3326c-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3326c-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3326c-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3326c-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3326c-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3326c-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3326c-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3326c-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="3326c-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="3326c-126">See Also</span></span>


[<span data-ttu-id="3326c-127">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3326c-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="3326c-128">[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3326c-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

