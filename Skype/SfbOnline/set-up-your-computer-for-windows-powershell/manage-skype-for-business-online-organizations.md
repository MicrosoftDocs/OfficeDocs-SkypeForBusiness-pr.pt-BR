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
ms.openlocfilehash: 2fa95bf8997dd0aff7271b1383c69d9b27c4f4a9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238781"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="056d0-103">Gerenciar Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="056d0-103">Manage Skype for Business Online organizations</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> <span data-ttu-id="056d0-104">A versão Teams versão de visualização pública do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) mais recente é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="056d0-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="056d0-105">Você pode encontrar informações sobre seu locatário Skype for Business Online usando os cmdlets **Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="056d0-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="056d0-106">Gerenciar Skype for Business locatários online</span><span class="sxs-lookup"><span data-stu-id="056d0-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="056d0-107">Para retornar informações sobre seu locatário Skype for Business Online, chame o cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) sem nenhum parâmetro adicional.</span><span class="sxs-lookup"><span data-stu-id="056d0-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="056d0-108">Para retornar apenas o nome do locatário e a ID, use este comando.</span><span class="sxs-lookup"><span data-stu-id="056d0-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="056d0-109">O valor do parâmetro  _TenantID_ é necessário ao executar cmdlets como [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) e [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="056d0-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="056d0-110">Para encontrar informações sobre se as informações de licenciamento do locatário especificado estão disponíveis no centro de administração do Skype for Business Online, use o cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)</span><span class="sxs-lookup"><span data-stu-id="056d0-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="056d0-111">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="056d0-111">Related topics</span></span>
[<span data-ttu-id="056d0-112">Configurar seu computador para gerenciamento do skype for business online usando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="056d0-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
