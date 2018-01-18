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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="6783e-103">Gerenciar Skype para organizações Business Online</span><span class="sxs-lookup"><span data-stu-id="6783e-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="6783e-104">Você pode encontrar informações sobre sua Skype para locatário Business Online usando os cmdlets **Get-CsTenant** e **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="6783e-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="6783e-105">Gerenciar Skype para os locatários Business Online</span><span class="sxs-lookup"><span data-stu-id="6783e-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="6783e-106">Para retornar informações sobre sua Skype para locatário Business Online, chame o cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sem quaisquer parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="6783e-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="6783e-107">Para retornar apenas o locatário nome e ID, use este comando.</span><span class="sxs-lookup"><span data-stu-id="6783e-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="6783e-108">O valor do parâmetro _TenantID_ é necessário ao se executar cmdlets como [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="6783e-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="6783e-109">Para encontrar informações sobre se as informações de licenciamento para o inquilino especificado estão disponíveis no Skype para o admin center Business Online, use o cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="6783e-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6783e-110">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6783e-110">Related topics</span></span>
[<span data-ttu-id="6783e-111">Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6783e-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
