---
title: Gerenciar Skype para organizações Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use o Windows PowerShell e os cmdlets Get-CsTenant e Get-CsTenantLicensingConfiguration para obter mais informações sobre sua Skype para locatário Business Online.
ms.openlocfilehash: 1b58686b2330b43cc5978752ac4f6b4a91f9588e
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="d0ca4-103">Gerenciar Skype para organizações Business Online</span><span class="sxs-lookup"><span data-stu-id="d0ca4-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="d0ca4-104">Você pode encontrar informações sobre sua Skype para locatário Business Online usando os cmdlets **Get-CsTenant** e **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d0ca4-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="d0ca4-105">Gerenciar Skype para os locatários Business Online</span><span class="sxs-lookup"><span data-stu-id="d0ca4-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="d0ca4-106">Para retornar informações sobre sua Skype para locatário Business Online, chame o cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sem quaisquer parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="d0ca4-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="d0ca4-107">Para retornar apenas o locatário nome e ID, use este comando.</span><span class="sxs-lookup"><span data-stu-id="d0ca4-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="d0ca4-108">O valor do parâmetro _TenantID_ é necessário ao se executar cmdlets como [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="d0ca4-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="d0ca4-109">Para encontrar informações sobre se as informações de licenciamento para o inquilino especificado estão disponíveis no Skype para o admin center Business Online, use o cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="d0ca4-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d0ca4-110">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d0ca4-110">Related topics</span></span>
[<span data-ttu-id="d0ca4-111">Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0ca4-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 