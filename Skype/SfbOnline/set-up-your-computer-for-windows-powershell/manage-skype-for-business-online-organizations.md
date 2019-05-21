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
f1keywords: None
ms.custom:
- PowerShell
description: Use o Windows PowerShell e os cmdlets Get-CsTenant e Get-CsTenantLicensingConfiguration para obter informações sobre seu locatário do Skype for Business online.
ms.openlocfilehash: 768ee4e0724bd04d38e9ce77b94372bdad498ecd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284686"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="9efef-103">Gerenciar organizações do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9efef-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="9efef-104">Você pode encontrar informações sobre o locatário do Skype for Business online usando os cmdlets **Get-CsTenant** e **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9efef-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="9efef-105">Gerenciar locatários do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9efef-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="9efef-106">Para retornar informações sobre o seu locatário do Skype for Business Online, chame o cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sem parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="9efef-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="9efef-107">Para retornar apenas o nome e a ID do locatário, use este comando.</span><span class="sxs-lookup"><span data-stu-id="9efef-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="9efef-108">O valor do parâmetro _tenantid_ é necessário ao executar cmdlets como [set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="9efef-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="9efef-109">Para localizar informações sobre se as informações de licenciamento do locatário especificado estão disponíveis no centro de administração do Skype for Business Online, use o cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="9efef-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9efef-110">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9efef-110">Related topics</span></span>
[<span data-ttu-id="9efef-111">Configurar seu computador para o gerenciamento do Skype for Business online usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9efef-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
