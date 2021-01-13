---
title: Novidades no Skype for Business Server 2019 | Recursos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: Esses recursos são novos no Skype for Business Server 2019.'
ms.openlocfilehash: f20abfa7d48717052c8ee0144e143a21b168286d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812581"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="11b5c-103">O que há no Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="11b5c-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="11b5c-104">**Resumo:** Leia este tópico para saber mais sobre os novos recursos do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="11b5c-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="11b5c-105">Os novos recursos do Skype for Business Server 2019 incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="11b5c-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="11b5c-106">Caixa Postal em Nuvem</span><span class="sxs-lookup"><span data-stu-id="11b5c-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="11b5c-107">Conector de Chamada de Dados </span><span class="sxs-lookup"><span data-stu-id="11b5c-107">Call Data Connector</span></span>
- <span data-ttu-id="11b5c-108">Migração lado a lado</span><span class="sxs-lookup"><span data-stu-id="11b5c-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="11b5c-109">Serviços de unificação de mensagens: Caixa Postal na Nuvem</span><span class="sxs-lookup"><span data-stu-id="11b5c-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="11b5c-110">A UM do Exchange permanece disponível no Skype for Business Server 2019 quando você integra o Skype for Business 2019 com o Exchange 2013 ou o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="11b5c-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="11b5c-111">Devido às alterações no suporte no Exchange 2019, a integração de UM do Exchange está sendo enfatizada em favor dos recursos de Caixa Postal na Nuvem e Atendedor Automático na Nuvem.</span><span class="sxs-lookup"><span data-stu-id="11b5c-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="11b5c-112">A Caixa Postal na Nuvem permite que todos os usuários do Skype for Business 2019&#x2014;se eles estão no local ou online&#x2014;tenham acesso ao mesmo serviço de caixa postal no Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="11b5c-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="11b5c-113">A Caixa Postal na Nuvem oferece os seguintes benefícios para os usuários locais e online:</span><span class="sxs-lookup"><span data-stu-id="11b5c-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="11b5c-114">Acesso à caixa postal na caixa de correio do Exchange usando os clientes do Skype for Business Online, do Teams ou do Outlook</span><span class="sxs-lookup"><span data-stu-id="11b5c-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="11b5c-115">Capacidade de usar o portal baseado na Web para gerenciar suas opções de caixa postal</span><span class="sxs-lookup"><span data-stu-id="11b5c-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="11b5c-116">Consulte [Planejar o serviço de Caixa Postal na](../sfbhybrid/hybrid/plan-cloud-voicemail.md) [Nuvem e planejar a migração do Skype for Business Server](../sfbhybrid/hybrid/plan-um-migration.md) e do Exchange Server para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="11b5c-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="11b5c-117">Monitoramento de chamada: Conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="11b5c-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="11b5c-118">O Conector de Dados de Chamada simplifica bastante o monitoramento de chamada em um ambiente híbrido porque você não precisa mais usar conjuntos diferentes de ferramentas locais e online para monitorar a qualidade de chamada de todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="11b5c-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="11b5c-119">Se seus usuários estão locais ou online, você pode optar por exibir a qualidade da chamada para toda a sua organização online.</span><span class="sxs-lookup"><span data-stu-id="11b5c-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="11b5c-120">Com o Conector de Dados de Chamada, você pode executar as seguintes tarefas usando um único toolset:</span><span class="sxs-lookup"><span data-stu-id="11b5c-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="11b5c-121">Monitore sua experiência do usuário no Microsoft Teams, Skype for Business Online e Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="11b5c-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="11b5c-122">Exibir e solucionar problemas em sua rede</span><span class="sxs-lookup"><span data-stu-id="11b5c-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="11b5c-123">Atribua funções de administrador e de helpdesk para a Análise de Chamada, para que você possa capacitar os funcionários de helpdesk a exibir e solucionar problemas em suas áreas de responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="11b5c-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="11b5c-124">Consulte [Planejar o Conector de Dados de Chamada](../sfbhybrid/hybrid/plan-call-data-connector.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="11b5c-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="11b5c-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="11b5c-125">See also</span></span>

[<span data-ttu-id="11b5c-126">O que foi preterido do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="11b5c-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
