---
title: Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca
description: Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 3e2ddbcc9c90096cea5fad4cb680f4ea1797ce48
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545607"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="cfc29-103">Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca</span><span class="sxs-lookup"><span data-stu-id="cfc29-103">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="cfc29-104">Os cmdlets **Grant-cs** (usados para atribuir políticas aos usuários) exigem dois identificadores: uma identidade de usuário (o parâmetro Identity) e a identidade de uma política por usuário (o parâmetro PolicyName).</span><span class="sxs-lookup"><span data-stu-id="cfc29-104">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="cfc29-105">Por exemplo, para atribuir a política de voz, RedmondVoicePolicy, ao usuário Ken Myer, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cfc29-105">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="cfc29-106">Há duas coisas que você deve ter em mente ao atribuir políticas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="cfc29-106">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="cfc29-107">Primeiro, somente as políticas por usuário podem ser atribuídas.</span><span class="sxs-lookup"><span data-stu-id="cfc29-107">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="cfc29-108">Você não pode atribuir a política global a um usuário.</span><span class="sxs-lookup"><span data-stu-id="cfc29-108">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="cfc29-109">Por exemplo, este comando falhará:</span><span class="sxs-lookup"><span data-stu-id="cfc29-109">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="cfc29-110">Esse comando falha porque não há necessidade de atribuir a política global.</span><span class="sxs-lookup"><span data-stu-id="cfc29-110">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="cfc29-111">Se você quiser gerenciar um usuário usando a política global, certifique-se de que você não atribui esse usuário a uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="cfc29-111">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="cfc29-112">Se nenhuma política por usuário tiver sido atribuída a um usuário, o usuário será automaticamente gerenciado usando a política global.</span><span class="sxs-lookup"><span data-stu-id="cfc29-112">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="cfc29-113">E se o usuário tiver sido atribuído anteriormente a uma política por usuário e se você quiser cancelar a atribuição dessa política e fazer com que o usuário seja gerenciado pela política global?</span><span class="sxs-lookup"><span data-stu-id="cfc29-113">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="cfc29-114">Nesse caso, você primeiro usará a seguinte sintaxe, que cancelará a atribuição de uma política por usuário concedendo a esse usuário uma política nula:</span><span class="sxs-lookup"><span data-stu-id="cfc29-114">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="cfc29-115">Grant-CsVoicePolicy – Identity "Ken Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="cfc29-115">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="cfc29-116">Em segundo lugar, tenha em mente que as políticas por usuário são criadas no escopo da marca.</span><span class="sxs-lookup"><span data-stu-id="cfc29-116">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="cfc29-117">No entanto, você pode omitir o **prefixo** da marca ao especificar um nome de política.</span><span class="sxs-lookup"><span data-stu-id="cfc29-117">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="cfc29-118">Esses dois comandos são idênticos:</span><span class="sxs-lookup"><span data-stu-id="cfc29-118">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="cfc29-119">Se você quiser retornar as identidades para todas as suas políticas por usuário (ou, pelo menos, todas as políticas por usuário do tipo especificado, como políticas de voz), use um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="cfc29-119">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="cfc29-120">Os cmdlets a seguir usam uma identidade de usuário e o escopo de marca:</span><span class="sxs-lookup"><span data-stu-id="cfc29-120">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="cfc29-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cfc29-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="cfc29-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cfc29-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="cfc29-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cfc29-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="cfc29-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cfc29-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="cfc29-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cfc29-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="cfc29-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cfc29-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="cfc29-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="cfc29-127">See Also</span></span>


[<span data-ttu-id="cfc29-128">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cfc29-128">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="cfc29-129">[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="cfc29-129">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

