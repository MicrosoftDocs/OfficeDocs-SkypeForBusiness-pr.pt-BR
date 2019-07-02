---
title: O que foi preterido do Skype for Business Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: esses recursos foram removidos do Skype for Business Server 2019.'
ms.openlocfilehash: 9fd6ddc28a3b75b8d4c411aa7909516d4b5c0ab8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418358"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="66edd-103">O que foi preterido do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="66edd-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="66edd-104">Saiba mais sobre os recursos e as funcionalidades preteridos no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="66edd-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="66edd-105">Para obter informações sobre os novos recursos do Skype for Business Server 2019, consulte [o que há no Skype for Business server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="66edd-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="66edd-106">Alguns recursos desenfatizados estão incluídos no Skype for Business Server 2019 para fins de compatibilidade com versões anteriores do produto.</span><span class="sxs-lookup"><span data-stu-id="66edd-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="66edd-107">Recursos preteridos no Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="66edd-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="66edd-108">Gateways XMPP para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="66edd-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="66edd-109">O Skype for Business Server 2015 e seus predecessores permitiam que você configure um proxy de protocolo de mensagens e de presença extensível (XMPP) no servidor de borda e um Gateway XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="66edd-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="66edd-110">Esta funcionalidade não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="66edd-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="66edd-111">Chat persistente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="66edd-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="66edd-112">O servidor de chat persistente é uma função opcional que permite que vários usuários de sua organização participem de conversas da sala de chat que persistem ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="66edd-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="66edd-113">O chat persistente não pode ser implantado com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="66edd-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="66edd-114">Esta função de servidor é removida do construtor de topologias, bem como do código.</span><span class="sxs-lookup"><span data-stu-id="66edd-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="66edd-115">A mesma funcionalidade está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66edd-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="66edd-116">Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="66edd-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="66edd-117">Espelhamento do SQL para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="66edd-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="66edd-118">O espelhamento do SQL não pode ser implantado com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="66edd-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="66edd-119">Outras opções para fornecer alta disponibilidade e recuperação de desastres ainda têm suporte e você deve escolher entre elas.</span><span class="sxs-lookup"><span data-stu-id="66edd-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="66edd-120">Consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar as opções.</span><span class="sxs-lookup"><span data-stu-id="66edd-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="66edd-121">Atualizações in-loco</span><span class="sxs-lookup"><span data-stu-id="66edd-121">In-place upgrades</span></span> 

<span data-ttu-id="66edd-122">As atualizações in-loco estavam disponíveis no Skype for Business Server 2015, mas não são mais compatíveis com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="66edd-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="66edd-123">A atualização lado a lado e a coexistência tem suporte, confira [migrar para o Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="66edd-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="66edd-124">Serviço de mobilidade (MCX)</span><span class="sxs-lookup"><span data-stu-id="66edd-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="66edd-125">O suporte do serviço de mobilidade usado por clientes móveis herdados não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="66edd-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="66edd-126">Isso foi anunciado anteriormente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="66edd-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="66edd-127">Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="66edd-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="66edd-128">Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="66edd-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="66edd-129">Para obter mais detalhes, consulte comparação de recursos do [plano de mobilidade para o Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) e do [cliente móvel para o Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="66edd-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="66edd-130">Tools</span><span class="sxs-lookup"><span data-stu-id="66edd-130">Tools</span></span>

<span data-ttu-id="66edd-131">As seguintes ferramentas não estarão disponíveis para uso na versão inicial do Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="66edd-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="66edd-132">Calculadora de planejamento de capacidade do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="66edd-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="66edd-133">Ferramentas de depuração do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="66edd-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="66edd-134">Ferramentas do kit de recursos do Skype for Business Server (algumas ferramentas serão removidas)</span><span class="sxs-lookup"><span data-stu-id="66edd-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="66edd-135">Parquímetro de Chamada</span><span class="sxs-lookup"><span data-stu-id="66edd-135">Call Parkometer</span></span>
    - <span data-ttu-id="66edd-136">Console de usuário de pesquisa</span><span class="sxs-lookup"><span data-stu-id="66edd-136">Lookup user console</span></span>
    - <span data-ttu-id="66edd-137">Migração de anúncio de número não atribuído</span><span class="sxs-lookup"><span data-stu-id="66edd-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="66edd-138">As seguintes ferramentas não são compatíveis com o Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="66edd-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="66edd-139">Metodologia de qualidade de chamada (mas não chama painel de qualidade)</span><span class="sxs-lookup"><span data-stu-id="66edd-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="66edd-140">Scorecard de metodologia de qualidade de chamada da Microsoft, v 1.5</span><span class="sxs-lookup"><span data-stu-id="66edd-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="66edd-141">Skype for Business Server 2015 Planning Tool</span><span class="sxs-lookup"><span data-stu-id="66edd-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="66edd-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="66edd-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="66edd-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="66edd-143">See also</span></span>

[<span data-ttu-id="66edd-144">O que há de novo no Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="66edd-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="66edd-145">Migrar a federação XMPP</span><span class="sxs-lookup"><span data-stu-id="66edd-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
