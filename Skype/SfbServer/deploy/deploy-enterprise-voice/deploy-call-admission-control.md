---
title: Implantar o serviço de controle de admissão de chamadas no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas. Para obter mais informações, consulte Plan para controle de admissão de chamada no Skype for Business Server 2015.
ms.openlocfilehash: 471bc7abe8a79f2ef4b4cc322450dbc7c639129f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="00321-104">Implantar o serviço de controle de admissão de chamadas no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="00321-104">Deploy call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="00321-105">O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.</span><span class="sxs-lookup"><span data-stu-id="00321-105">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="00321-106">Para obter mais informações, consulte [Planejar o controle de admissão de chamada no Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="00321-106">For more information, see [Plan for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="00321-107">Para implantar o Serviço de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="00321-107">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="00321-108">Reunir todas as informações necessárias para a sua topologia de rede empresarial, conforme descrito em [exemplo: coletando os requisitos para o controle de admissão de chamada no Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00321-108">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="00321-109">Se você não tiver feito isso, você deve definir as regiões e os sites da rede e associar sub-redes aos sites da rede.</span><span class="sxs-lookup"><span data-stu-id="00321-109">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="00321-110">Para obter detalhes, consulte [Deploy regiões de rede, sites e sub-redes em Skype para negócios 2015](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="00321-110">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
3. <span data-ttu-id="00321-111">Criar perfis de política, conforme detalhado no [criar perfis de política de largura de banda em Skype para Business Server 2015](create-bandwidth-policy-profiles.md) de largura de banda</span><span class="sxs-lookup"><span data-stu-id="00321-111">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server 2015](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="00321-112">Crie links de região de rede, conforme detalhado no [criar links de região de rede no Skype para Business Server 2015](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="00321-112">Create network region links, as detailed in [Create network region links in Skype for Business Server 2015](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="00321-113">Crie rotas de inter-região de rede, conforme detalhado no [criar rotas interregional da rede no Skype para Business Server 2015](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="00321-113">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server 2015](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="00321-114">Crie políticas entre sites de rede, conforme detalhado no [políticas entre sites de rede de criar no Skype para Business Server 2015](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="00321-114">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server 2015](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="00321-115">Habilite o controle de admissão de chamada, conforme detalhado no [Habilitar o controle de admissão de chamada no Skype para Business Server 2015](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="00321-115">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="00321-116">Verifique algumas configurações finais para certificar-se de que tudo está definido corretamente.</span><span class="sxs-lookup"><span data-stu-id="00321-116">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="00321-117">Para obter detalhes, consulte [implantação do controle de admissão de chamada: lista de verificação final do Skype para Business Server 2015](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="00321-117">For details, see [Call admission control deployment: final checklist for Skype for Business Server 2015](final-checklist.md).</span></span>
    

