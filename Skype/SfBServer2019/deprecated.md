---
title: O que é reduzido do Skype para Business Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: Esses recursos foram removidos do Skype para Business Server 2019.'
ms.openlocfilehash: bd7519e66632c005d81ff9fc110684f6c4854c41
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198968"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="6536e-103">O que é reduzido do Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="6536e-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="6536e-104">Saiba mais sobre os recursos e funcionalidade são reduzidos no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6536e-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="6536e-105">Para obter informações sobre novos recursos do Skype para Business Server 2019, consulte [What's in Skype para Business Server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="6536e-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="6536e-106">Alguns recursos desprovisionamento emphasised estão incluídos na Skype para Business Server 2019 para compatibilidade com versões anteriores do produto.</span><span class="sxs-lookup"><span data-stu-id="6536e-106">Some de-emphasised features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="6536e-107">Recursos reduzidos no Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="6536e-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="6536e-108">Gateways XMPP para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="6536e-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="6536e-109">Skype para Business Server 2015 e seus predecessores permitia configurar um proxy de mensagens extensíveis e protocolo de presença (XMPP) no servidor de borda e um Gateway XMPP no pool de Front-End ou de servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="6536e-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="6536e-110">Essa funcionalidade não está mais disponível no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6536e-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="6536e-111">Chat persistente para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="6536e-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="6536e-112">Servidor de bate-papo persistente é uma função opcional que permite que vários usuários em sua organização participar de conversas de sala de chat que persistam ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="6536e-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="6536e-113">Chat persistente não pode ser implantado com Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6536e-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="6536e-114">Esta função de servidor é removida do construtor de topologia, bem como do código.</span><span class="sxs-lookup"><span data-stu-id="6536e-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="6536e-115">A mesma funcionalidade está disponível em equipes.</span><span class="sxs-lookup"><span data-stu-id="6536e-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="6536e-116">Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="6536e-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="6536e-117">Espelhamento de SQL para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="6536e-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="6536e-118">Espelhamento de SQL não pode ser implantado com Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6536e-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="6536e-119">Outras opções para fornecer alta disponibilidade e recuperação de desastres ainda são suportadas e você deve escolher entre eles.</span><span class="sxs-lookup"><span data-stu-id="6536e-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="6536e-120">Consulte o [plano de alta disponibilidade e recuperação de desastres em Skype para Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) revisar as opções.</span><span class="sxs-lookup"><span data-stu-id="6536e-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="6536e-121">Atualizações in-loco</span><span class="sxs-lookup"><span data-stu-id="6536e-121">In-place upgrades</span></span> 

<span data-ttu-id="6536e-122">Atualizações in-loco estavam disponíveis no Skype para Business Server 2015, mas não são mais suportadas no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6536e-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6536e-123">Lado a lado, atualização e coexistência é suportada, consulte [Migration to Skype para Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6536e-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="6536e-124">Serviço de mobilidade (Mcx)</span><span class="sxs-lookup"><span data-stu-id="6536e-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="6536e-125">Suporte ao serviço de mobilidade usado pelos clientes móveis herdados não está mais disponível no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6536e-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="6536e-126">Isso foi anunciado anteriormente no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6536e-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="6536e-127">Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="6536e-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="6536e-128">Usuários com clientes herdados usando Mcx serão necessário atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="6536e-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="6536e-129">Para obter mais detalhes, consulte [Planejar mobilidade para Skype para Business Server](../SfbServer/plan-your-deployment/mobility.md) e a [comparação de recursos do cliente móvel para Skype para negócios](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="6536e-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="6536e-130">Ferramentas</span><span class="sxs-lookup"><span data-stu-id="6536e-130">Tools</span></span>

<span data-ttu-id="6536e-131">As seguintes ferramentas não estarão disponíveis para uso em uma versão inicial do Skype para Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="6536e-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="6536e-132">Calculadora de planejamento de capacidade do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6536e-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="6536e-133">Skype para Business Server as ferramentas de depuração</span><span class="sxs-lookup"><span data-stu-id="6536e-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="6536e-134">Skype para ferramentas do Business Server Resource Kit (algumas ferramentas serão removidas)</span><span class="sxs-lookup"><span data-stu-id="6536e-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="6536e-135">Parquímetro de Chamada</span><span class="sxs-lookup"><span data-stu-id="6536e-135">Call Parkometer</span></span>
    - <span data-ttu-id="6536e-136">Console do usuário de pesquisa</span><span class="sxs-lookup"><span data-stu-id="6536e-136">Lookup user console</span></span>
    - <span data-ttu-id="6536e-137">Migração de comunicado de número não atribuído</span><span class="sxs-lookup"><span data-stu-id="6536e-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="6536e-138">Não há suporte para as seguintes ferramentas com Skype para Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="6536e-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="6536e-139">Metodologia de qualidade de chamada (mas não chamar o painel de controle de qualidade)</span><span class="sxs-lookup"><span data-stu-id="6536e-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="6536e-140">Scorecard de metodologia de qualidade de chamada da Microsoft, v 1.5</span><span class="sxs-lookup"><span data-stu-id="6536e-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="6536e-141">Skype for Business Server 2015 Planning Tool</span><span class="sxs-lookup"><span data-stu-id="6536e-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="6536e-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="6536e-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="6536e-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="6536e-143">See also</span></span>

[<span data-ttu-id="6536e-144">O que há de novo no Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="6536e-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="6536e-145">Migrar a federação XMPP</span><span class="sxs-lookup"><span data-stu-id="6536e-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
