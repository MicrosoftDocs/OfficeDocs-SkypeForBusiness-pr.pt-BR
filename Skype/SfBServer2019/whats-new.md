---
title: Novidades no Skype for Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: Esses recursos são novos no Skype para Business Server 2019.'
ms.openlocfilehash: 411ca0705fa06d0b5720656cec2fcb3cbda50eeb
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696153"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="a135c-103">O que há no Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a135c-103">What's in Skype for Business Server 2019</span></span> 

<span data-ttu-id="a135c-104">**Resumo:** Leia este tópico para conhecer os novos recursos do Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a135c-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="a135c-105">Novos recursos do Skype para Business Server 2019 incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a135c-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="a135c-106">Caixa postal de nuvem</span><span class="sxs-lookup"><span data-stu-id="a135c-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="a135c-107">Conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="a135c-107">Call Data Connector</span></span>
- <span data-ttu-id="a135c-108">Migração lado a lado</span><span class="sxs-lookup"><span data-stu-id="a135c-108">Side-by-side migration</span></span>
- <span data-ttu-id="a135c-109">Migração para equipes</span><span class="sxs-lookup"><span data-stu-id="a135c-109">Migration to Teams</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="a135c-110">Unificação de serviços de mensagens: caixa postal de nuvem</span><span class="sxs-lookup"><span data-stu-id="a135c-110">Unified messaging services: Cloud Voicemail</span></span> 

<span data-ttu-id="a135c-111">UM do Exchange permanece disponível na Skype para Business Server 2019 ao integrar Skype para negócios 2019 com Exchange 2013 ou 2016 do Exchange.</span><span class="sxs-lookup"><span data-stu-id="a135c-111">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="a135c-112">Devido às alterações no suporte no Exchange 2019, a integração de UM do Exchange está sendo desprovisionamento emphasised em favor de recursos de caixa postal de nuvem e atendedor automático de nuvem.</span><span class="sxs-lookup"><span data-stu-id="a135c-112">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="a135c-113">Caixa postal de nuvem permite que todos os seu Skype para usuários corporativos 2019 & #x 2014; eles estão hospedados no local ou online & #x 2014; tenham acesso ao mesmo serviço caixa postal no Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="a135c-113">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="a135c-114">Caixa postal de nuvem fornece os seguintes benefícios para seu local e a usuários online:</span><span class="sxs-lookup"><span data-stu-id="a135c-114">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="a135c-115">Acesso à caixa postal na sua caixa de correio do Exchange usando o Skype para clientes corporativos Online, equipes ou Outlook</span><span class="sxs-lookup"><span data-stu-id="a135c-115">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span> 
- <span data-ttu-id="a135c-116">Capacidade de usar o portal baseado na web para gerenciar suas opções de caixa postal</span><span class="sxs-lookup"><span data-stu-id="a135c-116">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="a135c-117">Para obter mais informações, consulte [serviço de caixa postal de nuvem planejar](hybrid/plan-cloud-voicemail.md) e [Planejar Skype para Business Server e migração do Exchange Server](hybrid/plan-um-migration.md) .</span><span class="sxs-lookup"><span data-stu-id="a135c-117">See [Plan Cloud Voicemail service](hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="a135c-118">Monitoramento de chamada: conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="a135c-118">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="a135c-119">Conector de dados chamada simplifica bastante chamada monitoramento em um ambiente híbrido porque não precisar mais usar diferentes conjuntos de locais e ferramentas online para monitorar a qualidade da chamada seus usuários.</span><span class="sxs-lookup"><span data-stu-id="a135c-119">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="a135c-120">Se os usuários estão hospedados no local ou online, você pode optar por exibir a qualidade da chamada de toda sua organização online.</span><span class="sxs-lookup"><span data-stu-id="a135c-120">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="a135c-121">Com o conector de dados de chamada, você pode executar as seguintes tarefas usando um único conjunto de ferramentas:</span><span class="sxs-lookup"><span data-stu-id="a135c-121">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="a135c-122">Monitore sua experiência do usuário em produtos Microsoft Teams, Skype para Business Online e Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a135c-122">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="a135c-123">Visualizar e solucionar problemas em sua rede</span><span class="sxs-lookup"><span data-stu-id="a135c-123">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="a135c-124">Atribua funções de administrador e assistência técnica para a análise de chamada, para que você pode capacitar os trabalhadores de assistência técnica para visualizar e solucionar problemas de suas áreas de responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="a135c-124">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span> 

<span data-ttu-id="a135c-125">Consulte o [Plano de chamar o conector de dados](hybrid/plan-call-data-connector.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a135c-125">See [Plan Call Data Connector](hybrid/plan-call-data-connector.md) for more information.</span></span>
  


## <a name="installation-and-upgrade-side-by-side-migration"></a><span data-ttu-id="a135c-126">Instalação e atualização: migração lado a lado</span><span class="sxs-lookup"><span data-stu-id="a135c-126">Installation and Upgrade: Side-by-side migration</span></span>

<span data-ttu-id="a135c-127">Em uma migração lado a lado, você implantar um novo servidor que executa o Skype para Business Server 2019 junto com um servidor correspondente que está executando uma versão anterior (Skype para Business Server 2015 ou o Lync Server 2013) e depois transferir operações para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="a135c-127">In a side-by-side migration, you deploy a new server running Skype for Business Server 2019 alongside a corresponding server that is running a previous version (Skype for Business Server 2015 or Lync Server 2013), and then transfer operations to the new server.</span></span> <span data-ttu-id="a135c-128">Se for necessário reverter para a versão anterior, você precisará apenas deslocar as operações de volta para os servidores originais.</span><span class="sxs-lookup"><span data-stu-id="a135c-128">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> 

<span data-ttu-id="a135c-129">Para obter detalhes completos, consulte [Migration to Skype para Business Server 2019](migration/migration-to-skype-for-business-server-2019.md).</span><span class="sxs-lookup"><span data-stu-id="a135c-129">For complete details, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md).</span></span>

### <a name="see-also"></a><span data-ttu-id="a135c-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a135c-130">See also</span></span>

[<span data-ttu-id="a135c-131">O que é reduzido do Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a135c-131">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)