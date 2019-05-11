---
title: Criar rede políticas entre sites no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Crie políticas entre sites, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server de rede.
ms.openlocfilehash: 455caaf624c463bdb1c32ca8fbce70c88626c774
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892962"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="73080-103">Criar rede políticas entre sites no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="73080-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="73080-104">Crie políticas entre sites, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server de rede.</span><span class="sxs-lookup"><span data-stu-id="73080-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="73080-105">Uma política entre sites de rede define limitações de largura de banda entre sites com links de WAN diretos entre eles.</span><span class="sxs-lookup"><span data-stu-id="73080-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="73080-106">Uma política entre sites de rede é necessária *somente* se houver um link cruzado direto entre dois sites de rede.</span><span class="sxs-lookup"><span data-stu-id="73080-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="73080-p101">Na região América do Norte da topologia de exemplo, existe um link direto entre os sites Reno e Albuquerque. Esses dois sites exigem uma política entre sites que aplique um perfil de política de largura de banda adequado. O exemplo a seguir aplica o perfil 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="73080-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="73080-110">Para criar uma política entre sites da rede</span><span class="sxs-lookup"><span data-stu-id="73080-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="73080-111">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="73080-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="73080-p102">Execute o cmdlet New-CsNetworkInterSitePolicy para criar política entre sites de rede e aplicar um perfil de política de largura de banda apropriado para dois sites que possuem um link cruzado direto. Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="73080-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="73080-114">Repita a etapa 2 conforme o necessário para criar políticas entre sites de rede para todos os pares de sites da rede que possuírem um link cruzado direto.</span><span class="sxs-lookup"><span data-stu-id="73080-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="73080-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="73080-115">See also</span></span>

[<span data-ttu-id="73080-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="73080-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="73080-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="73080-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="73080-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="73080-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="73080-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="73080-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
