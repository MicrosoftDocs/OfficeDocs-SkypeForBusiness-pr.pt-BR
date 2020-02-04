---
title: Cmdlets no Skype for Business online que usam apenas o escopo global
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 5610649295fdf4089372d9c59e4ccb51228c1fc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728101"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="b2a6c-102">Cmdlets no Skype for Business online que usam apenas o escopo global</span><span class="sxs-lookup"><span data-stu-id="b2a6c-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="b2a6c-103">Várias configurações do Skype for Business online estão disponíveis apenas no *escopo global*.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="b2a6c-104">Isso significa que há um único conjunto de configurações que se aplica a todos os usuários atribuídos a esse locatário.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="b2a6c-105">(Cada locatário tem seu próprio conjunto exclusivo de configurações globais.) Quando você está usando cmdlets limitados ao escopo global, o parâmetro Identity é opcional.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="b2a6c-106">Por exemplo, para recuperar as configurações de configuração de reunião, você pode usar este comando:</span><span class="sxs-lookup"><span data-stu-id="b2a6c-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="b2a6c-107">Como alternativa, você pode omitir o parâmetro Identity e usar esse comando mais simples em vez disso:</span><span class="sxs-lookup"><span data-stu-id="b2a6c-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="b2a6c-108">Como há apenas uma coleção global de definições de configuração de reunião, os dois comandos retornam as mesmas informações exatas.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="b2a6c-109">O parâmetro Identity também pode ser omitido ao usar um dos cmdlets **set-cs** .</span><span class="sxs-lookup"><span data-stu-id="b2a6c-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="b2a6c-110">Esses dois comandos são idênticos:</span><span class="sxs-lookup"><span data-stu-id="b2a6c-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="b2a6c-111">Os dois comandos são idênticos porque, por padrão, o Windows PowerShell modificará a coleção global, se você não incluir o parâmetro de identidade.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="b2a6c-112">Os cmdlets a seguir operam somente no escopo global:</span><span class="sxs-lookup"><span data-stu-id="b2a6c-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="b2a6c-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b2a6c-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b2a6c-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b2a6c-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b2a6c-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b2a6c-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b2a6c-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b2a6c-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b2a6c-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b2a6c-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="b2a6c-123">Observe que o cmdlet **Remove-CsVoicePolicy** é algo de anomalia.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="b2a6c-124">Primeiro, esse cmdlet exige que você inclua o parâmetro Identity:</span><span class="sxs-lookup"><span data-stu-id="b2a6c-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="b2a6c-125">Segundo, o cmdlet **Remove-CsVoicePolicy** não exclui realmente a política de voz global; O Skype for Business online não permite que você exclua políticas globais ou definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="b2a6c-126">O que o cmdlet faz é permitir que você redefina todas as propriedades na política de voz global para seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="b2a6c-127">Por exemplo, por padrão, a propriedade AllowCallForwarding é definida como false.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="b2a6c-128">No entanto, AllowCallForwarding pode ter sido modificado, com o valor agora definido como true.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="b2a6c-129">Quando você executar o cmdlet **Remove-CsVoicePolicy** , a propriedade AllowCallForwarding voltará para o valor padrão: false.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="b2a6c-130">A tabela a seguir resume esse cenário:</span><span class="sxs-lookup"><span data-stu-id="b2a6c-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2a6c-131">Valor de AllowCallForwarding</span><span class="sxs-lookup"><span data-stu-id="b2a6c-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="b2a6c-132">Cenário</span><span class="sxs-lookup"><span data-stu-id="b2a6c-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2a6c-133">Falso</span><span class="sxs-lookup"><span data-stu-id="b2a6c-133">False</span></span></p></td>
<td><p><span data-ttu-id="b2a6c-134">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="b2a6c-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2a6c-135">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b2a6c-135">True</span></span></p></td>
<td><p><span data-ttu-id="b2a6c-136">Após a modificação da política global</span><span class="sxs-lookup"><span data-stu-id="b2a6c-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2a6c-137">Falso</span><span class="sxs-lookup"><span data-stu-id="b2a6c-137">False</span></span></p></td>
<td><p><span data-ttu-id="b2a6c-138">O cmdlet <strong>Remove-CsVoicePolicy</strong> foi executado</span><span class="sxs-lookup"><span data-stu-id="b2a6c-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="b2a6c-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="b2a6c-139">See Also</span></span>


[<span data-ttu-id="b2a6c-140">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b2a6c-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="b2a6c-141">[Os cmdlets do Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b2a6c-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

