---
title: Implantar o controle de admissão de chamada no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.
ms.openlocfilehash: 52fcedaab781e9ed76222afb32b56840a3b07c1c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223138"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="6f009-103">Implantar o controle de admissão de chamada no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="6f009-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="6f009-104">O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.</span><span class="sxs-lookup"><span data-stu-id="6f009-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="6f009-105">Para obter mais informações, consulte [Planejar o controle de admissão de chamada no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="6f009-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="6f009-106">Para implantar o Serviço de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="6f009-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="6f009-107">Reunir todas as informações necessárias para a sua topologia de rede empresarial, conforme descrito em [exemplo: coletando os requisitos para o controle de admissão de chamada no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f009-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="6f009-108">Se você não tiver feito isso, você deve definir as regiões e os sites da rede e associar sub-redes aos sites da rede.</span><span class="sxs-lookup"><span data-stu-id="6f009-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="6f009-109">Para obter detalhes, consulte [Deploy regiões de rede, sites e sub-redes em Skype para negócios](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="6f009-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="6f009-110">Criar perfis de política, conforme detalhado no [criar perfis de política de largura de banda em Skype para Business Server](create-bandwidth-policy-profiles.md) de largura de banda</span><span class="sxs-lookup"><span data-stu-id="6f009-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="6f009-111">Crie links de região de rede, conforme detalhado no [criar links de região de rede no Skype para Business Server](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="6f009-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="6f009-112">Crie rotas de inter-região de rede, conforme detalhado no [criar rotas interregional da rede no Skype para Business Server](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="6f009-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="6f009-113">Crie políticas entre sites de rede, conforme detalhado no [políticas entre sites de rede de criar no Skype para Business Server](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6f009-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="6f009-114">Habilite o controle de admissão de chamada, conforme detalhado no [Habilitar o controle de admissão de chamada no Skype para Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="6f009-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="6f009-115">Verifique algumas configurações finais para certificar-se de que tudo está definido corretamente.</span><span class="sxs-lookup"><span data-stu-id="6f009-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="6f009-116">Para obter detalhes, consulte [implantação do controle de admissão de chamada: lista de verificação final do Skype para Business Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="6f009-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

