---
title: Cmdlets no Skype for Business online que usam apenas o escopo global
description: Cmdlets no Skype for Business online que usam somente o escopo global.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f59806128ceea825a4cdd966e85852b98079b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545597"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="3b096-103">Cmdlets no Skype for Business online que usam apenas o escopo global</span><span class="sxs-lookup"><span data-stu-id="3b096-103">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="3b096-104">Várias configurações do Skype for Business online estão disponíveis apenas no *escopo global*.</span><span class="sxs-lookup"><span data-stu-id="3b096-104">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="3b096-105">Isso significa que há uma única coleção de configurações que se aplica a todos os usuários atribuídos a esse locatário.</span><span class="sxs-lookup"><span data-stu-id="3b096-105">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="3b096-106">(Cada locatário tem seu próprio conjunto exclusivo de configurações globais.) Quando você está usando cmdlets limitados ao escopo global, o parâmetro Identity é opcional.</span><span class="sxs-lookup"><span data-stu-id="3b096-106">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="3b096-107">Por exemplo, para recuperar as definições de configuração de reunião, você pode usar este comando:</span><span class="sxs-lookup"><span data-stu-id="3b096-107">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="3b096-108">Como alternativa, você pode omitir o parâmetro Identity e usar esse comando mais simples em vez disso:</span><span class="sxs-lookup"><span data-stu-id="3b096-108">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="3b096-109">Como há apenas uma coleção global de definições de configuração de reunião, os dois comandos retornam as mesmas informações exatas.</span><span class="sxs-lookup"><span data-stu-id="3b096-109">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="3b096-110">O parâmetro Identity também pode ser omitido ao usar um dos cmdlets **set-cs** .</span><span class="sxs-lookup"><span data-stu-id="3b096-110">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="3b096-111">Esses dois comandos são idênticos:</span><span class="sxs-lookup"><span data-stu-id="3b096-111">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="3b096-112">Os dois comandos são idênticos porque, por padrão, o Windows PowerShell modificará a coleção global, se você não incluir o parâmetro Identity.</span><span class="sxs-lookup"><span data-stu-id="3b096-112">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="3b096-113">Os cmdlets a seguir operam apenas no escopo global:</span><span class="sxs-lookup"><span data-stu-id="3b096-113">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="3b096-114">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-114">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b096-115">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-115">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b096-116">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-116">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b096-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b096-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b096-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b096-120">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-120">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b096-121">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-121">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b096-122">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-122">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3b096-123">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-123">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="3b096-124">Observe que o cmdlet **Remove-CsVoicePolicy** é algo de anomalia.</span><span class="sxs-lookup"><span data-stu-id="3b096-124">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="3b096-125">Primeiro, este cmdlet exige que você inclua o parâmetro Identity:</span><span class="sxs-lookup"><span data-stu-id="3b096-125">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="3b096-126">Em segundo lugar, o cmdlet **Remove-CsVoicePolicy** não exclui realmente a política de voz global; O Skype for Business online não permite que você exclua políticas globais ou definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="3b096-126">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="3b096-127">O que o cmdlet faz é permitir que você redefina todas as propriedades na política de voz global para seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="3b096-127">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="3b096-128">Por exemplo, por padrão, a propriedade AllowCallForwarding é definida como false.</span><span class="sxs-lookup"><span data-stu-id="3b096-128">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="3b096-129">No entanto, AllowCallForwarding pode ter sido modificada, com o valor agora definido como true.</span><span class="sxs-lookup"><span data-stu-id="3b096-129">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="3b096-130">Quando você executar o cmdlet **Remove-CsVoicePolicy** , a propriedade AllowCallForwarding será revertida para o valor padrão: false.</span><span class="sxs-lookup"><span data-stu-id="3b096-130">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="3b096-131">A tabela a seguir resume esse cenário:</span><span class="sxs-lookup"><span data-stu-id="3b096-131">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b096-132">Valor AllowCallForwarding</span><span class="sxs-lookup"><span data-stu-id="3b096-132">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="3b096-133">Cenário</span><span class="sxs-lookup"><span data-stu-id="3b096-133">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b096-134">Falso</span><span class="sxs-lookup"><span data-stu-id="3b096-134">False</span></span></p></td>
<td><p><span data-ttu-id="3b096-135">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="3b096-135">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b096-136">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="3b096-136">True</span></span></p></td>
<td><p><span data-ttu-id="3b096-137">Após a política global ter sido modificada</span><span class="sxs-lookup"><span data-stu-id="3b096-137">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b096-138">Falso</span><span class="sxs-lookup"><span data-stu-id="3b096-138">False</span></span></p></td>
<td><p><span data-ttu-id="3b096-139">Após a execução do cmdlet <strong>Remove-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="3b096-139">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="3b096-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="3b096-140">See Also</span></span>


[<span data-ttu-id="3b096-141">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3b096-141">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="3b096-142">[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3b096-142">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

