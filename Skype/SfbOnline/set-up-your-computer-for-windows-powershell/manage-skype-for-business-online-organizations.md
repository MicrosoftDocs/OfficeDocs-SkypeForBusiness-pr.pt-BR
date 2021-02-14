---
title: Gerenciar organizações do Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use o Windows PowerShell e os cmdlets Get-CsTenant e Get-CsTenantLicensingConfiguration para obter informações sobre seu locatário do Skype for Business Online.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085687"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gerenciar organizações do Skype for Business Online
> [!NOTE]
> A versão [de visualização pública mais recente](https://www.powershellgallery.com/packages/MicrosoftTeams/) do Teams PowerShell é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento do PowerShell do Teams.

Você pode encontrar informações sobre seu locatário do Skype for Business Online usando os **cmdlets Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Gerenciar locatários do Skype for Business Online

Para retornar informações sobre seu locatário do Skype for Business Online, ligue para o cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sem parâmetros adicionais.
  
```PowerShell
Get-CsTenant
```

Para retornar apenas o nome do locatário e a ID, use este comando.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

O valor do parâmetro _TenantID_ é necessário ao executar cmdlets como [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [Set-CsTenantFederationConfiguration.](https://technet.microsoft.com/library/jj994080.aspx)
  
Para saber mais sobre se as informações de licenciamento do locatário especificado estão disponíveis no Centro de administração do Skype for Business Online, use o cmdlet [Get-CsTenantLicensingConfiguration.](https://go.microsoft.com/fwlink/p/?linkid=849606)
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do Skype for Business Online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
