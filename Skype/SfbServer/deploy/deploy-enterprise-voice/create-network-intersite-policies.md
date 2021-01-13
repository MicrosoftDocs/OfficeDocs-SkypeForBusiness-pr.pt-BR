---
title: Criar políticas entre locais de rede no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Crie políticas entre sites de rede, que são usadas pelo controle de admissão de chamadas do Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 69609da75fdfa87309743920eace59892a440f2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822471"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="00ecc-103">Criar políticas entre locais de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00ecc-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="00ecc-104">Crie políticas entre sites de rede, que são usadas pelo controle de admissão de chamadas do Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00ecc-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="00ecc-105">Uma política entre sites de rede define limitações de largura de banda entre sites que possuem links wan diretos entre eles.</span><span class="sxs-lookup"><span data-stu-id="00ecc-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="00ecc-106">Uma política entre sites de rede só será  *necessária*  se houver um link cruzado direto entre dois sites de rede.</span><span class="sxs-lookup"><span data-stu-id="00ecc-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="00ecc-107">Na região América do Norte da topologia de exemplo, existe um link direto entre os sites Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="00ecc-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="00ecc-108">Esses dois sites exigem uma política entre sites que aplique um perfil de política de largura de banda apropriado.</span><span class="sxs-lookup"><span data-stu-id="00ecc-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="00ecc-109">O exemplo a seguir aplica o perfil 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="00ecc-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="00ecc-110">Para criar uma política entre sites de rede</span><span class="sxs-lookup"><span data-stu-id="00ecc-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="00ecc-111">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="00ecc-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="00ecc-112">Execute o cmdlet New-CsNetworkInterSitePolicy para criar políticas entre sites de rede e aplicar um perfil de política de largura de banda apropriado para dois sites que tenham um link cruzado direto.</span><span class="sxs-lookup"><span data-stu-id="00ecc-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="00ecc-113">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="00ecc-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="00ecc-114">Repita a etapa 2 conforme necessário para criar políticas entre sites de rede para todos os pares de sites de rede que tenham um link cruzado direto.</span><span class="sxs-lookup"><span data-stu-id="00ecc-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="00ecc-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="00ecc-115">See also</span></span>

[<span data-ttu-id="00ecc-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="00ecc-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="00ecc-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="00ecc-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="00ecc-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="00ecc-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="00ecc-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="00ecc-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
