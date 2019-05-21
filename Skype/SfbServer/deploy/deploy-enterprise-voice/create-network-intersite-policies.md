---
title: Criar políticas entre sites de rede no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Criar políticas entre sites de rede, que são usadas pelo controle de admissão de chamadas do Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: dceb48d0e87706d71de8c69b5622fbab468273b4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286310"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="60079-103">Criar políticas entre sites de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="60079-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="60079-104">Criar políticas entre sites de rede, que são usadas pelo controle de admissão de chamadas do Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="60079-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="60079-105">Uma política entre sites de rede define limitações de largura de banda entre sites com links de WAN diretos entre eles.</span><span class="sxs-lookup"><span data-stu-id="60079-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="60079-106">Uma política entre sites é necessária *somente* se houver um link cruzado direto entre dois sites de rede.</span><span class="sxs-lookup"><span data-stu-id="60079-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="60079-p101">Na região América do Norte da topologia de exemplo, existe um link direto entre os sites Reno e Albuquerque. Esses dois sites exigem uma política entre sites que aplique um perfil de política de largura de banda adequado. O exemplo a seguir aplica o perfil 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="60079-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="60079-110">Para criar uma política entre sites da rede</span><span class="sxs-lookup"><span data-stu-id="60079-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="60079-111">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="60079-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="60079-p102">Execute o cmdlet New-CsNetworkInterSitePolicy para criar política entre sites de rede e aplicar um perfil de política de largura de banda apropriado para dois sites que possuem um link cruzado direto. Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="60079-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="60079-114">Repita a etapa 2 conforme o necessário para criar políticas entre sites de rede para todos os pares de sites da rede que possuírem um link cruzado direto.</span><span class="sxs-lookup"><span data-stu-id="60079-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="60079-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="60079-115">See also</span></span>

[<span data-ttu-id="60079-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="60079-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="60079-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="60079-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="60079-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="60079-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="60079-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="60079-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
