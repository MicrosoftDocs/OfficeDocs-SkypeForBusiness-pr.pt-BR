---
title: Estudo de caso da Contoso Voice Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudo de caso de voz do teams para Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701219"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="e6ae5-103">Estudo de caso da Contoso: visão geral da migração de voz do teams</span><span class="sxs-lookup"><span data-stu-id="e6ae5-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="e6ae5-104">Este artigo apresenta um estudo de caso sobre como uma empresa multinacional fictícia, contoso, implementou uma solução de voz de equipe para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="e6ae5-105">A contoso implantou o Microsoft 365 Enterprise e corrigiu as principais decisões de design e os detalhes de implementação para o seguinte: rede, identidade, Windows 10 Enterprise, Office 365 ProPlus, gerenciamento de dispositivo móvel, proteção de informações, segurança, atualização do Skype for Business para equipes, sistemas telefônicos e conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="e6ae5-106">Este artigo se concentra na maneira como a contoso migrou seus usuários locais para o Microsoft Teams para comunicação unificada, colaboração e voz.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="e6ae5-107">Para obter informações detalhadas sobre como a contoso acelera a transformação digital usando os serviços de nuvem da Microsoft, consulte todos os artigos principais começando com a [visão geral do estudo de caso da Contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="e6ae5-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="e6ae5-108">Nos artigos principais, você encontrará informações sobre o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6ae5-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="e6ae5-109">Necessidades da infraestrutura de ti da contoso</span><span class="sxs-lookup"><span data-stu-id="e6ae5-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="e6ae5-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="e6ae5-110">Networking</span></span>
- <span data-ttu-id="e6ae5-111">Identidade</span><span class="sxs-lookup"><span data-stu-id="e6ae5-111">Identity</span></span>
- <span data-ttu-id="e6ae5-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e6ae5-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="e6ae5-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="e6ae5-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="e6ae5-114">Gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="e6ae5-114">Mobile device management</span></span>
- <span data-ttu-id="e6ae5-115">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="e6ae5-115">Information protection</span></span>
- <span data-ttu-id="e6ae5-116">Resumo da segurança do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e6ae5-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="e6ae5-117">Equipe para um projeto de melhor segredo</span><span class="sxs-lookup"><span data-stu-id="e6ae5-117">Team for a top-secret project</span></span>
- <span data-ttu-id="e6ae5-118">Site do SharePoint Online para ativos digitais altamente confidenciais</span><span class="sxs-lookup"><span data-stu-id="e6ae5-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="e6ae5-119">Para obter informações sobre como planejar uma atualização, comece a começar a usar [a atualização do Microsoft Teams](upgrade-start-here.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae5-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="e6ae5-120">Metas comerciais da Contoso para Teams</span><span class="sxs-lookup"><span data-stu-id="e6ae5-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="e6ae5-121">Para migrar seus usuários locais para o Microsoft Teams para comunicação unificada, colaboração e voz, a Contoso decidiu nas seguintes metas de negócios:</span><span class="sxs-lookup"><span data-stu-id="e6ae5-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="e6ae5-122">Habilitação de equipes</span><span class="sxs-lookup"><span data-stu-id="e6ae5-122">Teams enablement</span></span> 

  <span data-ttu-id="e6ae5-123">A equipe de comunicação unificada de comunicação e colaboração da Contoso permitiu as políticas corretas para controlar e habilitar a colaboração interna e externa segura.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="e6ae5-124">Atualização do Skype for Business para o Teams</span><span class="sxs-lookup"><span data-stu-id="e6ae5-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="e6ae5-125">O Skype for Business foi amplamente implantado dentro da contoso.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="e6ae5-126">Com a necessidade de sair dos sistemas herdados, a Contoso decidiu atualizar seus usuários do Skype for Business para o Teams.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="e6ae5-127">Para obter mais informações, consulte [estudo de caso da Contoso: plano de atualização do teams](voice-case-study-migration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae5-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="e6ae5-128">Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="e6ae5-128">Phone System</span></span>  

  <span data-ttu-id="e6ae5-129">O Skype for Business com Enterprise Voice foi amplamente implantado dentro da contoso.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="e6ae5-130">Com a necessidade de remover sistemas herdados que foram o próximo nó para seus servidores de mediação, a contoso migrou os usuários do Skype for Business Enterprise Voice para o sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="e6ae5-131">Os sites da Contoso usaram o plano de chamadas da Microsoft, o roteamento direto do sistema telefônico ou uma combinação dos dois.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="e6ae5-132">Para obter mais informações, consulte [estudo de caso da Contoso: sistema telefônico](voice-case-study-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae5-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="e6ae5-133">Roteamento com Base no Local</span><span class="sxs-lookup"><span data-stu-id="e6ae5-133">Location-Based Routing</span></span> 

  <span data-ttu-id="e6ae5-134">Com os locais do Office em países regulamentados pela telefonia, a contoso precisou recriar o roteamento Location-Based que estava presente no Skype for Business em sua implantação de sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="e6ae5-135">Para obter mais informações, consulte [estudo de caso da Contoso: Location-Based roteamento](voice-case-study-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae5-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="e6ae5-136">Chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="e6ae5-136">Emergency Calling</span></span> 

  <span data-ttu-id="e6ae5-137">Onde o roteamento direto foi implementado, a contoso configurou a chamada de emergência com terceiros aprovados.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="e6ae5-138">Para obter mais informações, consulte [estudo de caso da Contoso: chamadas de emergência](voice-case-study-emergency-calling.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae5-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="e6ae5-139">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="e6ae5-139">Audio Conferencing</span></span> 

  <span data-ttu-id="e6ae5-140">A contoso configurou números de serviços de audioconferência que foram hospedados em seu tronco SIP para o provedor de PSTN.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="e6ae5-141">Para obter mais informações, consulte [estudo de caso da Contoso: videoconferência](voice-case-study-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae5-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="e6ae5-142">Otimização de mídia local</span><span class="sxs-lookup"><span data-stu-id="e6ae5-142">Local Media Optimization</span></span> 

  <span data-ttu-id="e6ae5-143">A contoso aproveitou a otimização de mídia local em locais onde tinha um tronco de rota direta para o sistema de telefone da Microsoft que era aproveitado por sites remotos.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="e6ae5-144">Para obter mais informações, consulte [planejar a otimização de mídia local](direct-routing-media-optimization.md) e [Configurar a otimização de mídia local](direct-routing-media-optimization-configure.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae5-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="e6ae5-145">Atendedores automáticos e filas de chamadas</span><span class="sxs-lookup"><span data-stu-id="e6ae5-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="e6ae5-146">Como resultado da Covid-19, a contoso queria oferecer suporte ao recepcionista enquanto a equipe estava trabalhando remotamente.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="e6ae5-147">A contoso usou atendedores automáticos e filas de chamadas para gerenciar as chamadas recebidas para o número de telefone da recepcionista.</span><span class="sxs-lookup"><span data-stu-id="e6ae5-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="e6ae5-148">Para obter mais informações, consulte [estudo de caso da Contoso: atendedores automáticos e filas de chamadas](voice-case-study-call-queues.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae5-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


