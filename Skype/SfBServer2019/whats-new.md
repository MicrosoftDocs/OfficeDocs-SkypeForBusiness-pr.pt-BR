---
title: O que há de novo no Skype for Business Server 2019 | Funções
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: esses recursos são novos no Skype for Business Server 2019.'
ms.openlocfilehash: 6db5ea6589a56f696f233854372fc95d6064fed7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799411"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="a5dc3-103">O que há no Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5dc3-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="a5dc3-104">**Resumo:** Leia este tópico para saber mais sobre os novos recursos do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5dc3-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="a5dc3-105">Os novos recursos do Skype for Business Server 2019 incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5dc3-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="a5dc3-106">Caixa Postal na Nuvem</span><span class="sxs-lookup"><span data-stu-id="a5dc3-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="a5dc3-107">Conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="a5dc3-107">Call Data Connector</span></span>
- <span data-ttu-id="a5dc3-108">Migração lado a lado</span><span class="sxs-lookup"><span data-stu-id="a5dc3-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="a5dc3-109">Serviços de mensagens unificadas: correio de voz na nuvem</span><span class="sxs-lookup"><span data-stu-id="a5dc3-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="a5dc3-110">O Exchange UM permanecerá disponível no Skype for Business Server 2019 quando você integrar o Skype for Business 2019 com o Exchange 2013 ou o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="a5dc3-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="a5dc3-111">Devido a alterações no suporte ao Exchange 2019, a integração de UM Exchange está sendo realçada em favor do recurso de correio de voz e do atendedor automático na nuvem.</span><span class="sxs-lookup"><span data-stu-id="a5dc3-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="a5dc3-112">O correio de voz em nuvem permite que todos os seus usuários do Skype for Business 2019&#x2014;se estão hospedados em&#x2014;locais ou online para ter acesso ao mesmo serviço de correio de voz na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a5dc3-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="a5dc3-113">O correio de voz na nuvem oferece os seguintes benefícios para seus usuários locais e online:</span><span class="sxs-lookup"><span data-stu-id="a5dc3-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="a5dc3-114">Acesso à caixa postal na caixa de correio do Exchange usando o Skype for Business Online, o Teams ou clientes do Outlook</span><span class="sxs-lookup"><span data-stu-id="a5dc3-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="a5dc3-115">Capacidade de usar o Portal baseado na Web para gerenciar as opções de correio de voz</span><span class="sxs-lookup"><span data-stu-id="a5dc3-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="a5dc3-116">Consulte [planejar o serviço de correio de voz na nuvem](../sfbhybrid/hybrid/plan-cloud-voicemail.md) e [planejar a migração do Skype for Business Server e do Exchange Server](../sfbhybrid/hybrid/plan-um-migration.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a5dc3-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="a5dc3-117">Monitoramento de chamadas: ligar para conector de dados</span><span class="sxs-lookup"><span data-stu-id="a5dc3-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="a5dc3-118">O conector de dados de chamadas simplifica bastante o monitoramento de chamadas em um ambiente híbrido porque você não precisa mais usar conjuntos de ferramentas locais e online para monitorar todos os seus usuários a qualidade das chamadas.</span><span class="sxs-lookup"><span data-stu-id="a5dc3-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="a5dc3-119">Não importa se os usuários estão hospedados no local ou online, você pode optar por exibir a qualidade da chamada para toda a sua organização online.</span><span class="sxs-lookup"><span data-stu-id="a5dc3-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="a5dc3-120">Com o conector de dados de chamada, você pode executar as seguintes tarefas usando um único conjunto de ferramentas:</span><span class="sxs-lookup"><span data-stu-id="a5dc3-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="a5dc3-121">Monitore sua experiência de usuário no Microsoft Teams, no Skype for Business Online e no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5dc3-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="a5dc3-122">Exibir e solucionar problemas em toda a rede</span><span class="sxs-lookup"><span data-stu-id="a5dc3-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="a5dc3-123">Atribua funções de helpdesk e de administrador para a análise de chamadas, para que você possa permitir que os profissionais da assistência técnica vejam e solucionem os problemas de suas áreas de responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="a5dc3-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="a5dc3-124">Para obter mais informações, consulte [planejar o conector de dados de chamadas](../sfbhybrid/hybrid/plan-call-data-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="a5dc3-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="a5dc3-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="a5dc3-125">See also</span></span>

[<span data-ttu-id="a5dc3-126">O que foi preterido do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5dc3-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
