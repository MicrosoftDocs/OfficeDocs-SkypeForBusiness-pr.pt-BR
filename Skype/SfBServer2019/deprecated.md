---
title: O que foi preterido do Skype for Business Server 2019
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
description: 'Resumo: Esses recursos foram removidos do Skype for Business Server 2019.'
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808721"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="d77da-103">O que foi preterido do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d77da-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="d77da-104">Saiba mais sobre os recursos e funcionalidades preterido no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d77da-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="d77da-105">Para saber mais sobre os novos recursos do Skype for Business Server 2019, confira o que há [no Skype for Business Server 2019.](whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="d77da-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="d77da-106">Alguns recursos sem ênfase estão incluídos no Skype for Business Server 2019 para compatibilidade com versões anteriores do produto.</span><span class="sxs-lookup"><span data-stu-id="d77da-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="d77da-107">Recursos preterido no Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d77da-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="d77da-108">XMPP Gateways for Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d77da-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="d77da-109">O Skype for Business Server 2015 e seus predecessores permitiram configurar um proxy XMPP (Extensible Messaging and Presence Protocol) no Servidor de Borda e um Gateway XMPP no servidor front-end ou pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="d77da-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="d77da-110">Essa funcionalidade não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d77da-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="d77da-111">Chat Persistente para Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d77da-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="d77da-112">O Servidor de Chat Persistente é uma função opcional que permite que vários usuários em sua organização participem de conversas de sala de chat que persistem ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="d77da-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="d77da-113">O chat persistente não pode ser implantado com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d77da-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="d77da-114">Essa função de servidor é removida do Construtor de Topologias, bem como do código.</span><span class="sxs-lookup"><span data-stu-id="d77da-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="d77da-115">A mesma funcionalidade está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="d77da-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="d77da-116">Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="d77da-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="d77da-117">SQL Mirroring for Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d77da-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="d77da-118">O espelhamento SQL não pode ser implantado com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d77da-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="d77da-119">Outras opções para fornecer alta disponibilidade e recuperação de desastres ainda são suportadas e você deve escolher entre elas.</span><span class="sxs-lookup"><span data-stu-id="d77da-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="d77da-120">Consulte [Plano para alta disponibilidade e recuperação de desastres no Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar as opções.</span><span class="sxs-lookup"><span data-stu-id="d77da-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="d77da-121">Atualizações no local</span><span class="sxs-lookup"><span data-stu-id="d77da-121">In-place upgrades</span></span> 

<span data-ttu-id="d77da-122">As atualizações in-place estavam disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d77da-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d77da-123">Há suporte para atualização e coexistência lado a lado, confira Migração para [o Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d77da-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="d77da-124">Mobility Service (Mcx)</span><span class="sxs-lookup"><span data-stu-id="d77da-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="d77da-125">O suporte ao Mobility Service usado por clientes móveis herdados não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d77da-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="d77da-126">Isso foi anunciado anteriormente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d77da-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="d77da-127">Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="d77da-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="d77da-128">Os usuários com clientes herddos usando o Mcx precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="d77da-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="d77da-129">Para obter mais detalhes, [consulte Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for [Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="d77da-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="d77da-130">Ferramentas</span><span class="sxs-lookup"><span data-stu-id="d77da-130">Tools</span></span>

<span data-ttu-id="d77da-131">As seguintes ferramentas não estarão disponíveis para uso na versão inicial do Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="d77da-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="d77da-132">Calculadora de Planejamento de Capacidade do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d77da-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="d77da-133">Ferramentas de depuração do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d77da-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="d77da-134">Ferramentas do Kit de Recursos do Skype for Business Server (algumas ferramentas serão removidas)</span><span class="sxs-lookup"><span data-stu-id="d77da-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="d77da-135">Estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="d77da-135">Call Parkometer</span></span>
    - <span data-ttu-id="d77da-136">Lookup user console</span><span class="sxs-lookup"><span data-stu-id="d77da-136">Lookup user console</span></span>
    - <span data-ttu-id="d77da-137">Migração de comunicados de número não atribuído</span><span class="sxs-lookup"><span data-stu-id="d77da-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="d77da-138">As seguintes ferramentas não são suportadas com o Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="d77da-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="d77da-139">Metodologia de qualidade de chamada (mas não painel de qualidade de chamada)</span><span class="sxs-lookup"><span data-stu-id="d77da-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="d77da-140">Scorecard da Metodologia de Qualidade de Chamada da Microsoft, v1.5</span><span class="sxs-lookup"><span data-stu-id="d77da-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="d77da-141">Ferramenta de Planejamento do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d77da-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="d77da-142">Ferramenta de Stress and Performance do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d77da-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="d77da-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="d77da-143">See also</span></span>

[<span data-ttu-id="d77da-144">Novidades no Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d77da-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="d77da-145">Migrar a federação XMPP</span><span class="sxs-lookup"><span data-stu-id="d77da-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
