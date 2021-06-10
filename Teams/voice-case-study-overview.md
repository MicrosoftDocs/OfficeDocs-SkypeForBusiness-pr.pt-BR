---
title: Teams de caso contoso de voz
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
description: Teams de caso de voz para corporação multi-nacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097487"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="db374-103">Estudo de caso contoso: Teams de migração de voz</span><span class="sxs-lookup"><span data-stu-id="db374-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="db374-104">Este artigo apresenta um estudo de caso para como uma corporação multi-nacional fictícia, Contoso, implementou uma solução Teams voz para sua organização.</span><span class="sxs-lookup"><span data-stu-id="db374-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="db374-105">A Contoso implantou o Microsoft 365 Enterprise e abordou as principais decisões de design e detalhes de implementação para os seguintes: rede, identidade, Windows 10 Enterprise, Office 365 ProPlus, gerenciamento de dispositivo móvel, proteção de informações, segurança, atualização do Skype for Business para Teams, Sistema de Telefonia e Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="db374-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="db374-106">Este artigo se concentra em como a Contoso migrou seus usuários locais para Teams comunicação unificada, colaboração e voz.</span><span class="sxs-lookup"><span data-stu-id="db374-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="db374-107">Para obter informações em segundo plano sobre como a Contoso acelerou sua transformação digital usando os serviços de nuvem da Microsoft, consulte todos os artigos principais começando com a visão geral do estudo de caso [contoso.](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="db374-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="db374-108">Nos artigos principais, você encontrará informações sobre o seguinte:</span><span class="sxs-lookup"><span data-stu-id="db374-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="db374-109">Necessidades de infraestrutura de TI da Contoso</span><span class="sxs-lookup"><span data-stu-id="db374-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="db374-110">Rede</span><span class="sxs-lookup"><span data-stu-id="db374-110">Networking</span></span>
- <span data-ttu-id="db374-111">Identidade</span><span class="sxs-lookup"><span data-stu-id="db374-111">Identity</span></span>
- <span data-ttu-id="db374-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db374-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="db374-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="db374-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="db374-114">Gerenciamento de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="db374-114">Mobile device management</span></span>
- <span data-ttu-id="db374-115">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="db374-115">Information protection</span></span>
- <span data-ttu-id="db374-116">Resumo da Microsoft 365 Enterprise segurança</span><span class="sxs-lookup"><span data-stu-id="db374-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="db374-117">Equipe para um projeto ultra-secreto</span><span class="sxs-lookup"><span data-stu-id="db374-117">Team for a top-secret project</span></span>
- <span data-ttu-id="db374-118">SharePoint Site online para ativos digitais altamente confidenciais</span><span class="sxs-lookup"><span data-stu-id="db374-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="db374-119">Para obter informações sobre como planejar uma atualização, você vai querer começar com a atualização de Microsoft Teams [.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="db374-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="db374-120">Metas de negócios da Contoso para Teams</span><span class="sxs-lookup"><span data-stu-id="db374-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="db374-121">Para migrar seus usuários locais para Teams comunicação unificada, colaboração e voz, a Contoso decidiu os seguintes objetivos comerciais:</span><span class="sxs-lookup"><span data-stu-id="db374-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="db374-122">Teams habilitação</span><span class="sxs-lookup"><span data-stu-id="db374-122">Teams enablement</span></span> 

  <span data-ttu-id="db374-123">A equipe unificada de comunicação e colaboração da Contoso Teams com as políticas corretas para governar e habilitar a colaboração interna e externa segura.</span><span class="sxs-lookup"><span data-stu-id="db374-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="db374-124">Atualização do Skype for Business para o Teams</span><span class="sxs-lookup"><span data-stu-id="db374-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="db374-125">Skype for Business foi amplamente implantado dentro da Contoso.</span><span class="sxs-lookup"><span data-stu-id="db374-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="db374-126">Com a necessidade de sair de sistemas herdado, a Contoso decidiu atualizar seus usuários Skype for Business para Teams.</span><span class="sxs-lookup"><span data-stu-id="db374-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="db374-127">Para obter mais informações, consulte [Estudo de caso contoso: Teams plano de atualização](voice-case-study-migration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="db374-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="db374-128">Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="db374-128">Phone System</span></span>  

  <span data-ttu-id="db374-129">Skype for Business com voz corporativa foi amplamente implantado dentro da Contoso.</span><span class="sxs-lookup"><span data-stu-id="db374-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="db374-130">Com a necessidade de mover os sistemas herdados que eram o próximo salto para seus servidores de mediação, a Contoso migrou seus usuários de voz Skype for Business corporativos para Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="db374-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="db374-131">Os sites da Contoso usavam o Plano de Chamadas da Microsoft, Sistema de Telefonia Roteamento Direto ou uma combinação de ambos.</span><span class="sxs-lookup"><span data-stu-id="db374-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="db374-132">Para obter mais informações, consulte Estudo de caso [contoso: Sistema de Telefonia](voice-case-study-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="db374-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="db374-133">Roteamento com Base no Local</span><span class="sxs-lookup"><span data-stu-id="db374-133">Location-Based Routing</span></span> 

  <span data-ttu-id="db374-134">Com locais de escritório em países regulamentados por telefonia, a Contoso precisava recriar o roteamento de Location-Based que estava presente no Skype for Business em sua implantação Sistema de Telefonia de telefonia.</span><span class="sxs-lookup"><span data-stu-id="db374-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="db374-135">Para obter mais informações, consulte [Estudo de caso contoso: Location-Based Routing](voice-case-study-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="db374-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="db374-136">Chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="db374-136">Emergency Calling</span></span> 

  <span data-ttu-id="db374-137">Onde o Roteamento Direto foi implementado, a Contoso definiu chamadas de emergência com terceiros aprovados.</span><span class="sxs-lookup"><span data-stu-id="db374-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="db374-138">Para obter mais informações, consulte [Estudo de caso contoso: Chamada de emergência](voice-case-study-emergency-calling.md).</span><span class="sxs-lookup"><span data-stu-id="db374-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="db374-139">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="db374-139">Audio Conferencing</span></span> 

  <span data-ttu-id="db374-140">A Contoso definiu números de serviço de Audioconferência hospedados no tronco SIP para o provedor PSTN.</span><span class="sxs-lookup"><span data-stu-id="db374-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="db374-141">Para obter mais informações, consulte [Estudo de caso contoso: Audioconferência](voice-case-study-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="db374-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="db374-142">Otimização de mídia local</span><span class="sxs-lookup"><span data-stu-id="db374-142">Local Media Optimization</span></span> 

  <span data-ttu-id="db374-143">A Contoso aproveitou a Otimização de Mídia Local em locais onde eles tinham um tronco de rota direta para Telefone Microsoft Sistema que foi aproveitado por sites remotos.</span><span class="sxs-lookup"><span data-stu-id="db374-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="db374-144">Para obter mais informações, consulte [Plan for Local Media Optimization](direct-routing-media-optimization.md) and Configure Local Media [Optimization](direct-routing-media-optimization-configure.md).</span><span class="sxs-lookup"><span data-stu-id="db374-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="db374-145">Atendimentos Automáticos e Filas de Chamada</span><span class="sxs-lookup"><span data-stu-id="db374-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="db374-146">Como resultado do Covid-19, a Contoso queria oferecer suporte de recepcionista enquanto sua equipe estava trabalhando remotamente.</span><span class="sxs-lookup"><span data-stu-id="db374-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="db374-147">A Contoso usou os atendimentos automáticos e filas de chamadas para gerenciar chamadas de entrada para o número de telefone da recepcionista.</span><span class="sxs-lookup"><span data-stu-id="db374-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="db374-148">Para obter mais informações, consulte [Estudo de caso contoso: Atendimento Automático e Filas de Chamada.](voice-case-study-call-queues.md)</span><span class="sxs-lookup"><span data-stu-id="db374-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>