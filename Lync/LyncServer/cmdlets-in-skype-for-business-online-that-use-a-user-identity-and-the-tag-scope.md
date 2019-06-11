---
title: Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab087388feb37ca8299cae8e4246484e4c23a88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836091"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca

 


Os cmdlets **Grant-cs** (usados para atribuir políticas aos usuários) exigem dois identificadores: uma identidade de usuário (o parâmetro Identity) e a identidade de uma política por usuário (o parâmetro PolicyName). Por exemplo, para atribuir a política de voz, RedmondVoicePolicy, ao usuário Ken Myer, use o seguinte comando:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Há duas coisas a ter em mente ao atribuir políticas a usuários. Primeiro, somente políticas por usuário podem ser atribuídas. Você não pode atribuir a política global a um usuário. Por exemplo, esse comando irá falhar:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Esse comando falha porque não há necessidade de atribuir a política global. Se você quiser gerenciar um usuário usando a política global, certifique-se de que você não atribua a ele uma política por usuário. Se nenhuma política por usuário tiver sido atribuída a um usuário, o usuário será automaticamente gerenciado com o uso da política global.


> [!NOTE]  
> E se o usuário tiver atribuído anteriormente uma política por usuário e você quiser cancelar a atribuição dessa política e ter o usuário gerenciado pela política global em vez disso? Nesse caso, você primeiro usará a seguinte sintaxe, que cancelará a atribuição de uma política por usuário concedendo a esse usuário uma política nula:<BR>Grant-CsVoicePolicy – identidade "Ken Myer" – PolicyName $Null



Em segundo lugar, lembre-se de que as políticas por usuário são criadas no escopo da marca. No entanto, você pode omitir o **prefixo** da marca ao especificar um nome de política. Esses dois comandos são idênticos:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Se você quiser retornar as identidades para todas as suas políticas por usuário (ou, pelo menos, todas as políticas por usuário do tipo especificado, como políticas de voz), use um comando semelhante a este:

    Get-CsVoicePolicy -Filter "tag:*"

Os cmdlets a seguir usam a identidade do usuário e o escopo da marca:

  - [Grant CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))

  - [Grant CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))

  - [Grant CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))

  - [Grant CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>Confira também


[Identidades, escopos e locatários no Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Os cmdlets do Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

