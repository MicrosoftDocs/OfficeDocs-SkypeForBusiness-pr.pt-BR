---
title: Gerenciar Skype for Business online
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
description: Use Windows PowerShell e os cmdlets Get-CsTenant e Get-CsTenantLicensingConfiguration para obter informações sobre seu locatário Skype for Business Online.
ms.openlocfilehash: 733d7e30bc25f15bcf05c2746ef1eb2cb8aa5cfd8e7e780356c4a972ef97a183
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298741"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gerenciar Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> A versão Teams versão de visualização pública do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) mais recente é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento Teams PowerShell.

Você pode encontrar informações sobre seu locatário Skype for Business Online usando os cmdlets **Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Gerenciar Skype for Business locatários online

Para retornar informações sobre seu locatário Skype for Business Online, chame o cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) sem nenhum parâmetro adicional.
  
```PowerShell
Get-CsTenant
```

Para retornar apenas o nome do locatário e a ID, use este comando.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

O valor do parâmetro  _TenantID_ é necessário ao executar cmdlets como [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) e [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).
  
Para encontrar informações sobre se as informações de licenciamento do locatário especificado estão disponíveis no centro de administração do Skype for Business Online, use o cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do skype for business online usando Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
