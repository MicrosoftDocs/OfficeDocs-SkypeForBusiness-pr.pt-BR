---
title: O que há de novo no Skype for Business Server 2019 | Recursos
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: esses recursos são novos no Skype for Business Server 2019.'
ms.openlocfilehash: 86a8ce580a8aafcfb487a4b0cf839cd001dace8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129394"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="d96c9-103">O que há no Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d96c9-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="d96c9-104">**Resumo:** Leia este tópico para saber mais sobre os novos recursos no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d96c9-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="d96c9-105">Os novos recursos do Skype for Business Server 2019 incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d96c9-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="d96c9-106">Caixa postal em nuvem</span><span class="sxs-lookup"><span data-stu-id="d96c9-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="d96c9-107">Call data Connector</span><span class="sxs-lookup"><span data-stu-id="d96c9-107">Call Data Connector</span></span>
- <span data-ttu-id="d96c9-108">Migração lado a lado</span><span class="sxs-lookup"><span data-stu-id="d96c9-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="d96c9-109">Serviços de Unificação de mensagens: caixa postal em nuvem</span><span class="sxs-lookup"><span data-stu-id="d96c9-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="d96c9-110">A UM do Exchange permanece disponível no Skype for Business Server 2019 quando você integra o Skype for Business 2019 com o Exchange 2013 ou o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="d96c9-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="d96c9-111">Devido às alterações no suporte no Exchange 2019, a integração de UM do Exchange está sendo realçada em favor dos recursos de caixa postal da nuvem e atendedor automático na nuvem.</span><span class="sxs-lookup"><span data-stu-id="d96c9-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="d96c9-112">A caixa postal em nuvem permite que todos os seus usuários do Skype for Business 2019&#x2014;se estão hospedados em&#x2014;locais ou online para ter acesso ao mesmo serviço de caixa postal na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d96c9-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="d96c9-113">A caixa postal em nuvem oferece os seguintes benefícios para os usuários locais e online:</span><span class="sxs-lookup"><span data-stu-id="d96c9-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="d96c9-114">Acesso à caixa postal em sua caixa de correio do Exchange usando o Skype for Business Online, o Teams ou clientes do Outlook</span><span class="sxs-lookup"><span data-stu-id="d96c9-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="d96c9-115">Capacidade de usar o Portal baseado na Web para gerenciar suas opções de caixa postal</span><span class="sxs-lookup"><span data-stu-id="d96c9-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="d96c9-116">Consulte [planejar o serviço de caixa postal Cloud](../sfbhybrid/hybrid/plan-cloud-voicemail.md) e [planejar o Skype for Business Server e a migração do Exchange Server](../sfbhybrid/hybrid/plan-um-migration.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d96c9-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="d96c9-117">Monitoramento de chamadas: Call data Connector</span><span class="sxs-lookup"><span data-stu-id="d96c9-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="d96c9-118">O Call data Connector simplifica bastante o monitoramento de chamadas em um ambiente híbrido, porque você não precisa mais usar conjuntos diferentes de ferramentas locais e online para monitorar toda a qualidade de chamada de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="d96c9-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="d96c9-119">Se seus usuários estão hospedados no local ou online, você pode optar por exibir a qualidade da chamada para toda a organização online.</span><span class="sxs-lookup"><span data-stu-id="d96c9-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="d96c9-120">Com o Call data Connector, você pode executar as seguintes tarefas usando um único conjunto de ferramentas:</span><span class="sxs-lookup"><span data-stu-id="d96c9-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="d96c9-121">Monitore a experiência do usuário no Microsoft Teams, no Skype for Business Online e no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d96c9-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="d96c9-122">Exibir e solucionar problemas em toda a sua rede</span><span class="sxs-lookup"><span data-stu-id="d96c9-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="d96c9-123">Atribuir funções de assistência técnica e de administrador para a análise de chamadas, para que você possa permitir que os profissionais de assistência técnica vejam e solucionem problemas de suas áreas de responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="d96c9-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="d96c9-124">Consulte [Plan Call data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d96c9-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="d96c9-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="d96c9-125">See also</span></span>

[<span data-ttu-id="d96c9-126">O que foi preterido do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d96c9-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
