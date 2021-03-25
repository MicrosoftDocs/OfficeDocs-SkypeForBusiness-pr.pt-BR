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
description: Use Windows PowerShell e os cmdlets Get-CsTenant e Get-CsTenantLicensingConfiguration para obter informações sobre seu locatário do Skype for Business Online.
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113177"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gerenciar organizações do Skype for Business Online
> [!NOTE]
> A versão [de visualização pública mais](https://www.powershellgallery.com/packages/MicrosoftTeams/) recente do Teams PowerShell é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento do Teams PowerShell.

Você pode encontrar informações sobre seu locatário do Skype for Business Online usando os cmdlets **Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Gerenciar locatários do Skype for Business Online

Para retornar informações sobre seu locatário do Skype for Business Online, chame o cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) sem nenhum parâmetro adicional.
  
```PowerShell
Get-CsTenant
```

Para retornar apenas o nome do locatário e a ID, use este comando.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

O valor do parâmetro  _TenantID_ é necessário ao executar cmdlets como [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) e [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).
  
Para encontrar informações sobre se as informações de licenciamento para o locatário especificado estão disponíveis no centro de administração do Skype for Business Online, use o cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do skype for business online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
