---
title: Planos de chamada do Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Determine qual plano de Chamada do Sistema de Telefonia da Microsoft atenderá melhor à sua organização no Cloud Voice no Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71fe92646a3a2976e9a4d393e54ea56a7669b400
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031847"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="27042-103">Qual plano de chamadas é ideal para você?</span><span class="sxs-lookup"><span data-stu-id="27042-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="27042-104">Você concluiu o [get started.](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="27042-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="27042-105">Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização.</span><span class="sxs-lookup"><span data-stu-id="27042-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="27042-106">Talvez você tenha implantado [Reuniões & conferência.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="27042-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="27042-107">Agora você está pronto para adicionar cargas de trabalho de voz na nuvem e decidiu usar o Microsoft Phone System com o Plano de Chamada para se conectar à PSTN (Rede Telefônica Pública Comutado).</span><span class="sxs-lookup"><span data-stu-id="27042-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="27042-108">Este artigo descreve as principais decisões de implantação para Planos de Chamada, bem como considerações adicionais que você pode querer configurar, com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="27042-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="27042-109">Você também deve ler [o Cloud Voice no Microsoft Teams](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27042-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="27042-110">Saiba mais sobre planos de chamada</span><span class="sxs-lookup"><span data-stu-id="27042-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="27042-111">Os artigos a seguir fornecem mais informações sobre como implantar e usar os Planos de Chamada da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="27042-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="27042-112">Sistema telefônico no Microsoft 365 ou no Office 365</span><span class="sxs-lookup"><span data-stu-id="27042-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="27042-113">Planos de chamada para o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="27042-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="27042-114">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="27042-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="27042-115">Decisões importantes sobre implantação</span><span class="sxs-lookup"><span data-stu-id="27042-115">Core deployment decisions</span></span>

<span data-ttu-id="27042-116">Para usar a Microsoft como operadora de telefonia, você precisa obter licenças do Plano de Chamada e atribuí-las aos usuários do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="27042-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="27042-117">Há dois tipos de Planos de Chamada disponíveis:</span><span class="sxs-lookup"><span data-stu-id="27042-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="27042-118">Planos de Chamada Doméstica</span><span class="sxs-lookup"><span data-stu-id="27042-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="27042-119">Planos de Chamada Domésticas e Internacionais</span><span class="sxs-lookup"><span data-stu-id="27042-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="27042-120">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="27042-120">Ask yourself</span></span>|<span data-ttu-id="27042-121">Ação</span><span class="sxs-lookup"><span data-stu-id="27042-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="27042-122">Os Planos de Chamada estão disponíveis na minha área?</span><span class="sxs-lookup"><span data-stu-id="27042-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="27042-123">Quais locais do usuário terão serviço de Plano de Chamada?</span><span class="sxs-lookup"><span data-stu-id="27042-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="27042-124">Para obter mais informações, consulte [a disponibilidade de país e região para Planos de Audioconferência e Chamada.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="27042-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="27042-125">Meus usuários precisam de chamada internacional?</span><span class="sxs-lookup"><span data-stu-id="27042-125">Do my users need international calling?</span></span> | <span data-ttu-id="27042-126">Para obter mais informações, consulte [Planos de Chamada do Microsoft 365 ou do Office 365.](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="27042-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="27042-127">Meus usuários têm licenças de Planos de Chamada?</span><span class="sxs-lookup"><span data-stu-id="27042-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="27042-128">Para comprar e atribuir licenças, confira a [Etapa 2: Comprar e atribuir licenças.](set-up-calling-plans.md#step-2-buy-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="27042-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="27042-129">Cada um dos meus usuários tem um número de telefone de discagem direta para dentro (DID) ?</span><span class="sxs-lookup"><span data-stu-id="27042-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="27042-130">Para obter números de telefone, consulte [a Etapa 3: Obter números de telefone.](set-up-calling-plans.md#step-3-get-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="27042-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="27042-131">Transferir números de telefone para o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="27042-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="27042-132">É fácil transferir seus números de telefone do provedor de serviços atual para o Teams.</span><span class="sxs-lookup"><span data-stu-id="27042-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="27042-133">Depois que você portuar seus números de telefone para o Teams, a Microsoft se tornará seu provedor de serviços e cobrará você por esses números de telefone.</span><span class="sxs-lookup"><span data-stu-id="27042-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="27042-134">Para obter mais informações, consulte [Transferir números de telefone para o Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="27042-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="27042-135">Números de telefone e locais de emergência</span><span class="sxs-lookup"><span data-stu-id="27042-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="27042-136">Com os Planos de Chamada no Microsoft 365 ou no Office 365, todos os usuários em sua organização precisam ter um número de telefone de discagem direta (DID) exclusivo e um endereço de emergência validado correspondente.</span><span class="sxs-lookup"><span data-stu-id="27042-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="27042-137">Você também pode especificar um local de emergência dentro do endereço de emergência (por exemplo, um número de escritório ou um número de andar).</span><span class="sxs-lookup"><span data-stu-id="27042-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="27042-138">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="27042-138">Ask yourself</span></span>|<span data-ttu-id="27042-139">Ação</span><span class="sxs-lookup"><span data-stu-id="27042-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="27042-140">Qual é o meu detalhamento para o endereço de emergência e as informações de localização?</span><span class="sxs-lookup"><span data-stu-id="27042-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="27042-141">Para obter mais informações, consulte [O que são locais, endereços e](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)encaminhamento de chamadas de emergência? .</span><span class="sxs-lookup"><span data-stu-id="27042-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="27042-142">Identidade de chamada</span><span class="sxs-lookup"><span data-stu-id="27042-142">Calling identity</span></span>

<span data-ttu-id="27042-143">Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (ID do chamador).</span><span class="sxs-lookup"><span data-stu-id="27042-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="27042-144">O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.</span><span class="sxs-lookup"><span data-stu-id="27042-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="27042-145">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="27042-145">Ask yourself</span></span>|<span data-ttu-id="27042-146">Ação</span><span class="sxs-lookup"><span data-stu-id="27042-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="27042-147">Quero mascarar ou desabilitar a ID de chamador?</span><span class="sxs-lookup"><span data-stu-id="27042-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="27042-148">Para alterar ou bloquear a ID de chamada, consulte Definir a [ID de chamada de um usuário.](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="27042-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




