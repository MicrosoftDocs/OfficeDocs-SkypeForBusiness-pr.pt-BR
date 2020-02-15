---
title: Cmdlets no Skype for Business online que usam uma identidade de usuário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8310d5e25b5fc3dd3ada43fcf3c8f899f60e5a7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001256"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Cmdlets no Skype for Business online que usam uma identidade de usuário

 


No Skype for Business Online, há várias maneiras diferentes de fazer referência a uma identidade de usuário individual:

  - Use o nome de exibição dos serviços de domínio do Active Directory do usuário. Por exemplo:
    
        -Identity "Ken Myer"

  - Use o endereço SIP do usuário. Por exemplo:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Use o UPN do usuário. Por exemplo:
    
        -Identity " kenmyer@litwareinc.com"

  - Use o nome diferenciado dos serviços de domínio do Active Directory do usuário. Por exemplo:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

Os cmdlets a seguir aceitam uma identidade do usuário:

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))

  - [Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))

  - [Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))

  - [New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))

  - [Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))

  - [Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))

  - [Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))

  - [Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))

Observe que você não precisa especificar uma identidade de usuário ao chamar um dos cmdlets **Get-cs** . Nesse caso, os cmdlets retornam todas as instâncias do item especificado. Por exemplo, este comando retorna informações sobre todos os usuários que foram habilitados para o Skype for Business Online:

    Get-CsOnlineUser

O parâmetro Identity só será necessário se você quiser retornar informações de um usuário específico:

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>Confira também


[Identidades, escopos e locatários no Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

