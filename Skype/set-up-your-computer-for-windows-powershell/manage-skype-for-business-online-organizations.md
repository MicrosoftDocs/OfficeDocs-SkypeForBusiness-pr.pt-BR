---
title: "Gerenciar Skype para organizações Business Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "Use o Windows PowerShell e os cmdlets Get-CsTenant e Get-CsTenantLicensingConfiguration para obter mais informações sobre sua Skype para locatário Business Online."
ms.openlocfilehash: cab693fa153eae99ac605981112a30ec09f49920
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="manage-skype-for-business-online-organizations"></a>Gerenciar Skype para organizações Business Online

Você pode encontrar informações sobre sua Skype para locatário Business Online usando os cmdlets **Get-CsTenant** e **Get-CsTenantLicensingConfiguration** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Gerenciar Skype para os locatários Business Online

Para retornar informações sobre sua Skype para locatário Business Online, chame o cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sem quaisquer parâmetros adicionais.
  
```
Get-CsTenant
```

Para retornar apenas o locatário nome e ID, use este comando.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

O valor do parâmetro _TenantID_ é necessário ao se executar cmdlets como [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).
  
Para encontrar informações sobre se as informações de licenciamento para o inquilino especificado estão disponíveis no Skype para o admin center Business Online, use o cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
