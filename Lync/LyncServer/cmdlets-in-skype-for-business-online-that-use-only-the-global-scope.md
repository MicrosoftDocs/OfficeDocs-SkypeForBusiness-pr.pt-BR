---
title: Cmdlets no Skype for Business online que usam apenas o escopo global
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
ms.openlocfilehash: b97f3c8d9ca7dda0b96db211192350184cbf27b1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755093"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Cmdlets no Skype for Business online que usam apenas o escopo global

 


Várias configurações do Skype for Business online estão disponíveis apenas no *escopo global*. Isso significa que há uma única coleção de configurações que se aplica a todos os usuários atribuídos a esse locatário. (Cada locatário tem seu próprio conjunto exclusivo de configurações globais.) Quando você está usando cmdlets limitados ao escopo global, o parâmetro Identity é opcional. Por exemplo, para recuperar as definições de configuração de reunião, você pode usar este comando:

    Get-CsMeetingConfiguration -Identity "global"

Como alternativa, você pode omitir o parâmetro Identity e usar esse comando mais simples em vez disso:

    Get-CsMeetingConfiguration

Como há apenas uma coleção global de definições de configuração de reunião, os dois comandos retornam as mesmas informações exatas. O parâmetro Identity também pode ser omitido ao usar um dos cmdlets **set-cs** . Esses dois comandos são idênticos:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Os dois comandos são idênticos porque, por padrão, o Windows PowerShell modificará a coleção global, se você não incluir o parâmetro Identity.

Os cmdlets a seguir operam apenas no escopo global:

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

Observe que o cmdlet **Remove-CsVoicePolicy** é algo de anomalia. Primeiro, este cmdlet exige que você inclua o parâmetro Identity:

    Remove-CsVoicePolicy -Identity "global"

Em segundo lugar, o cmdlet **Remove-CsVoicePolicy** não exclui realmente a política de voz global; O Skype for Business online não permite que você exclua políticas globais ou definições de configuração. O que o cmdlet faz é permitir que você redefina todas as propriedades na política de voz global para seus valores padrão. Por exemplo, por padrão, a propriedade AllowCallForwarding é definida como false. No entanto, AllowCallForwarding pode ter sido modificada, com o valor agora definido como true. Quando você executar o cmdlet **Remove-CsVoicePolicy** , a propriedade AllowCallForwarding será revertida para o valor padrão: false. A tabela a seguir resume esse cenário:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor AllowCallForwarding</th>
<th>Cenário</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Falso</p></td>
<td><p>Valor padrão</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>Após a política global ter sido modificada</p></td>
</tr>
<tr class="odd">
<td><p>Falso</p></td>
<td><p>Após a execução do cmdlet <strong>Remove-CsVoicePolicy</strong></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>Confira também


[Identidades, escopos e locatários no Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

