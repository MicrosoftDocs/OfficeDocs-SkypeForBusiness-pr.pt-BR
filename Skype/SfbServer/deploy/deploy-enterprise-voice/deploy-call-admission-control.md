---
title: Implantar o serviço de controle de admissão de chamadas no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas. Planejamento do controle de admissão de chamadas no Skype for Business Server 2015
ms.openlocfilehash: 0302663546a099e682b5dc405625d4519fe998d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="a90d2-104">Implantar o serviço de controle de admissão de chamadas no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a90d2-104">Deploy call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a90d2-105">O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.</span><span class="sxs-lookup"><span data-stu-id="a90d2-105">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="a90d2-106">Planejamento do controle de admissão de chamadas no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a90d2-106">Plan for call admission control in Skype for Business Server 2015</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="a90d2-107">Para implantar o Serviço de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="a90d2-107">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="a90d2-108">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a90d2-108">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="a90d2-109">Se você não tiver feito isso, você deve definir as regiões e os sites da rede e associar sub-redes aos sites da rede.</span><span class="sxs-lookup"><span data-stu-id="a90d2-109">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="a90d2-110">Implantar regiões da rede, sites e sub-redes no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="a90d2-110">Deploy network regions, sites and subnets in Skype for Business 2015</span></span>
    
3. <span data-ttu-id="a90d2-111">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server 2015](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a90d2-111">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server 2015](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="a90d2-112">Create network region links, as detailed in [Create network region links in Skype for Business Server 2015](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="a90d2-112">Create network region links, as detailed in [Create network region links in Skype for Business Server 2015](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="a90d2-113">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server 2015](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="a90d2-113">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server 2015](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="a90d2-114">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server 2015](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a90d2-114">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server 2015](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="a90d2-115">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="a90d2-115">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="a90d2-116">Verifique algumas configurações finais para certificar-se de que tudo está definido corretamente.</span><span class="sxs-lookup"><span data-stu-id="a90d2-116">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="a90d2-117">Lista de verificação final da implantação do serviço de controle de admissão de chamadas do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a90d2-117">Call admission control deployment: final checklist for Skype for Business Server 2015</span></span>
    

