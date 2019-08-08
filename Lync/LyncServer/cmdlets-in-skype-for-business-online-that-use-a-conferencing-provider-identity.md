---
title: Cmdlets no Skype for Business online que usam uma identidade de provedor de conferência
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2957fbc63a885a1c2e1f053cffbf7439d2b648d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233117"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Cmdlets no Skype for Business online que usam uma identidade de provedor de conferência

 


Para retornar informações sobre todos os provedores de serviços de audioconferência com os quais a sua organização se contratadou, você pode simplesmente chamar o cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) sem parâmetros:

    Get-CsAudioConferencingProvider

Se você quiser limitar os dados retornados a um único provedor (neste exemplo, os serviços de áudio da Contoso do provedor), use o parâmetro Identity:

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

Há apenas um cmdlet do Skype for Business online que aceita uma ID do provedor de serviços de audioconferência:

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>Confira também


[Identidades, escopos e locatários no Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Os cmdlets do Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

