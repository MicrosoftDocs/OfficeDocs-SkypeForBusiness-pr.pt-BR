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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="814b2-103">Gerenciar organizações do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="814b2-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="814b2-104">A versão [de visualização pública mais recente](https://www.powershellgallery.com/packages/MicrosoftTeams/) do Teams PowerShell é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="814b2-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="814b2-105">Você pode encontrar informações sobre seu locatário do Skype for Business Online usando os **cmdlets Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="814b2-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="814b2-106">Gerenciar locatários do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="814b2-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="814b2-107">Para retornar informações sobre seu locatário do Skype for Business Online, ligue para o cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sem parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="814b2-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="814b2-108">Para retornar apenas o nome do locatário e a ID, use este comando.</span><span class="sxs-lookup"><span data-stu-id="814b2-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="814b2-109">O valor do parâmetro _TenantID_ é necessário ao executar cmdlets como [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [Set-CsTenantFederationConfiguration.](https://technet.microsoft.com/library/jj994080.aspx)</span><span class="sxs-lookup"><span data-stu-id="814b2-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="814b2-110">Para saber mais sobre se as informações de licenciamento do locatário especificado estão disponíveis no Centro de administração do Skype for Business Online, use o cmdlet [Get-CsTenantLicensingConfiguration.](https://go.microsoft.com/fwlink/p/?linkid=849606)</span><span class="sxs-lookup"><span data-stu-id="814b2-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="814b2-111">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="814b2-111">Related topics</span></span>
[<span data-ttu-id="814b2-112">Configurar seu computador para gerenciamento do Skype for Business Online usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="814b2-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
