---
title: Implantar o controle de admissão de chamadas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.
ms.openlocfilehash: 0b2df103c432cd6b304f93b3a36af6e87c4bc2e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233187"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="bce35-103">Implantar o controle de admissão de chamadas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bce35-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="bce35-104">O serviço de controle de admissão de chamadas (CAC) é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.</span><span class="sxs-lookup"><span data-stu-id="bce35-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="bce35-105">Para obter mais informações, consulte [planejar o controle de admissão de chamadas no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="bce35-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="bce35-106">Para implantar o Serviço de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="bce35-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="bce35-107">Reúna todas as informações necessárias para a topologia de rede da sua empresa, conforme descrito no [exemplo: coletando requisitos para controle de admissão de chamadas no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bce35-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="bce35-108">Se você não tiver feito isso, você deve definir as regiões e os sites da rede e associar sub-redes aos sites da rede.</span><span class="sxs-lookup"><span data-stu-id="bce35-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="bce35-109">Para obter detalhes, consulte [implantar regiões de rede, sites e sub-redes no Skype for Business](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="bce35-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="bce35-110">Criar perfis de política de largura de banda, conforme detalhado em [criar perfis de política de largura de banda no Skype for Business Server](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="bce35-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="bce35-111">Crie links de região de rede, conforme detalhado em [criar links de região de rede no Skype for Business Server](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="bce35-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="bce35-112">Crie rotas entre regiões, como detalhado em [criar rotas interregionis de rede no Skype for Business Server](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="bce35-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="bce35-113">Crie políticas entre sites de rede, conforme detalhado em [criar políticas entre sites de rede no Skype for Business Server](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bce35-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="bce35-114">Habilite o controle de admissão de chamadas, conforme detalhado em [habilitar controle de admissão de chamadas no Skype for Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="bce35-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="bce35-115">Verifique algumas configurações finais para certificar-se de que tudo está definido corretamente.</span><span class="sxs-lookup"><span data-stu-id="bce35-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="bce35-116">Para obter detalhes, consulte [implantação de controle de admissão de chamadas: lista de verificação final do Skype for Business Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="bce35-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

