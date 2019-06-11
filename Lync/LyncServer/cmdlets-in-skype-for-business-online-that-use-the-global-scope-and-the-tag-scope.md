---
title: Cmdlets no Skype for Business online que usam o escopo global e o escopo de marca
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51327b98be69f92736c1c8523c97b4de6463273b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836094"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Cmdlets no Skype for Business online que usam o escopo global e o escopo de marca

 


No Skype for Business Online, as políticas podem ser configuradas no *escopo global* ou no *escopo da marca* (ou no *escopo por usuário*). Ao usar os cmdlets **Get-cs** , você não precisa especificar um escopo ou uma identidade. Se você chamar um desses cmdlets sem parâmetros, todos os itens relevantes serão retornados. Por exemplo, esse comando retorna informações sobre todas as suas políticas de acesso externo:

    Get-CsExternalAccessPolicy

Você precisa incluir somente o parâmetro Identity ou o parâmetro Filter se desejar limitar os dados retornados. Por exemplo, para retornar apenas a política global, use este comando:

    Get-CsExternalAccessPolicy -Identity "global"

Para retornar uma política por usuário com a identidade "RedmondAccessPolicy", use este comando:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> Ao fazer referência a uma política por usuário, o <STRONG>prefixo</STRONG> da marca é opcional. Essa sintaxe, que inclui o prefixo, também é válida:<BR>Get-CsExternalAccessPolicy – marca de identidade: RedmondAccessPolicy "



Para retornar todas as políticas, exceto as políticas globais (ou seja, todas as políticas por usuário), use este comando:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Os cmdlets a seguir operam em relação ao escopo global e ao escopo por usuário (marca):

  - [Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> Apesar do nome, planos de discagem, funcionamento em termos de funcionamento, políticas. O <EM>plano</EM> de discagem do termo é usado em vez de, por exemplo, política de discagem, para preservar a terminologia usada com as versões anteriores do Lync Server.



## <a name="see-also"></a>Confira também


[Identidades, escopos e locatários no Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Os cmdlets do Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

