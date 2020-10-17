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
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Cmdlets no Skype for Business online que usam o escopo global e o escopo da marca

 


No Skype for Business Online, as políticas podem ser configuradas no *escopo global* ou no *escopo de marca* (ou *escopo por usuário*). Ao usar os cmdlets **Get-cs** , não é necessário especificar um escopo ou uma identidade. Se você chamar um desses cmdlets sem qualquer parâmetro, todos os itens relevantes serão retornados. Por exemplo, este comando retorna informações sobre todas as suas políticas de acesso externo:

    Get-CsExternalAccessPolicy

Você precisa incluir apenas o parâmetro Identity ou o parâmetro Filter se quiser limitar os dados retornados. Por exemplo, para retornar somente a política global, use este comando:

    Get-CsExternalAccessPolicy -Identity "global"

Para retornar uma política por usuário com a identidade "RedmondAccessPolicy", use este comando:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> Ao fazer referência a uma política por usuário, o <STRONG>prefixo</STRONG> da marca é opcional. Essa sintaxe, que inclui o prefixo, também é válida:<BR>Marca Get-CsExternalAccessPolicy – Identity ": RedmondAccessPolicy"



Para retornar todas as políticas, exceto as políticas globais (ou seja, todas as políticas por usuário), use este comando:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Os cmdlets a seguir operam contra o escopo global e o escopo por usuário (marca):

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> Apesar do nome, os planos de discagem são funcionalmente falando, políticas. O <EM>plano de discagem</EM> do termo é usado em vez de, por exemplo, a política de discagem, para preservar a terminologia usada com as versões anteriores do Lync Server.



## <a name="see-also"></a>Confira também


[Identidades, escopos e locatários no Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

