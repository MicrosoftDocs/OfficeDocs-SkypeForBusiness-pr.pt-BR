---
title: Chamando planos em equipes da Microsoft
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Página inicial do plano de chamada
appliesto:
- Microsoft Teams
ms.openlocfilehash: cce239825389e11cfbc627d518e7d1e459fa77d3
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351494"
---
# <a name="phone-system-with-calling-plans"></a><span data-ttu-id="0d01b-103">Sistema de Telefonia com Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="0d01b-103">Phone System with Calling Plans</span></span> 

<span data-ttu-id="0d01b-104">Você concluiu a [Introdução](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="0d01b-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="0d01b-105">Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização.</span><span class="sxs-lookup"><span data-stu-id="0d01b-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="0d01b-106">Talvez você implantou [conferência de & de reuniões](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="0d01b-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="0d01b-107">Agora você está pronto para adicionar as cargas de trabalho de voz de nuvem e você decidiu usar o sistema de telefone da Microsoft com chamar planejar para conectar-se para a comutação telefônica PSTN (rede pública).</span><span class="sxs-lookup"><span data-stu-id="0d01b-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="0d01b-108">Este artigo descreve as principais decisões sobre implantação para chamar planos, bem como considerações adicionais que convém configurar, com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0d01b-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="0d01b-109">Você também deve ler [Nuvem de voz equipes da Microsoft](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0d01b-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="0d01b-110">Saiba mais sobre planos de chamada</span><span class="sxs-lookup"><span data-stu-id="0d01b-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="0d01b-111">Os artigos a seguir fornecem mais informações sobre como implantar e usar o Microsoft chamar planos:</span><span class="sxs-lookup"><span data-stu-id="0d01b-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="0d01b-112">Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="0d01b-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="0d01b-113">Planos de Chamadas do Office 365</span><span class="sxs-lookup"><span data-stu-id="0d01b-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="0d01b-114">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="0d01b-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="0d01b-115">Decisões importantes sobre implantação</span><span class="sxs-lookup"><span data-stu-id="0d01b-115">Core deployment decisions</span></span>

<span data-ttu-id="0d01b-116">Para usar o Microsoft como sua operadora de telefonia, você precisará obter licenças chamar planejar e atribuí-las aos usuários de seu sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="0d01b-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="0d01b-117">Há dois tipos de planos de chamar disponíveis:</span><span class="sxs-lookup"><span data-stu-id="0d01b-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="0d01b-118">Planos de chamada domésticas</span><span class="sxs-lookup"><span data-stu-id="0d01b-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="0d01b-119">Planos de chamada nacionais e internacionais</span><span class="sxs-lookup"><span data-stu-id="0d01b-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="0d01b-120">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="0d01b-120">Ask yourself</span></span>|<span data-ttu-id="0d01b-121">Ação</span><span class="sxs-lookup"><span data-stu-id="0d01b-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="0d01b-122">Estão chamar planos disponíveis na minha área?</span><span class="sxs-lookup"><span data-stu-id="0d01b-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="0d01b-123">Quais locais de usuário terá chamar planejar o serviço?</span><span class="sxs-lookup"><span data-stu-id="0d01b-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="0d01b-124">Para obter mais informações, consulte [disponibilidade país e região para conferência de áudio e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="0d01b-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="0d01b-125">Meus usuários preciso chamadas internacionais?</span><span class="sxs-lookup"><span data-stu-id="0d01b-125">Do my users need international calling?</span></span> | <span data-ttu-id="0d01b-126">Para obter mais informações, consulte [Chamando planos do Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0d01b-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="0d01b-127">Meus usuários tem planos de chamar licenças?</span><span class="sxs-lookup"><span data-stu-id="0d01b-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="0d01b-128">Para comprar e atribuir licenças, consulte [etapa 2: comprar e atribuir licenças](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="0d01b-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="0d01b-129">Meus usuários tem uma conexão direta (DID) número de telefone de discagem para dentro?</span><span class="sxs-lookup"><span data-stu-id="0d01b-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="0d01b-130">Para obter os números de telefone, consulte [etapa 3: obter os números de telefone](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="0d01b-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="0d01b-131">Transferir números de telefone para o Office 365</span><span class="sxs-lookup"><span data-stu-id="0d01b-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="0d01b-132">É fácil transferir seus números de telefone do seu provedor de serviços atual para equipes.</span><span class="sxs-lookup"><span data-stu-id="0d01b-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="0d01b-133">Depois que você a porta seus números de telefone para equipes, a Microsoft se tornará o provedor de serviços e bill referentes aos números de telefone.</span><span class="sxs-lookup"><span data-stu-id="0d01b-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="0d01b-134">Para obter mais informações, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0d01b-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="0d01b-135">Números de telefone e locais de emergência</span><span class="sxs-lookup"><span data-stu-id="0d01b-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="0d01b-136">Com a chamada estiver planejando no Office 365, cada usuário na sua organização precisa ter um exclusivo DID discagem direta (DID) números de telefone e um endereço de emergência validado correspondente.</span><span class="sxs-lookup"><span data-stu-id="0d01b-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="0d01b-137">Você também pode especificar um local de emergência dentro o endereço de emergência (por exemplo, um número do escritório ou o número de chão).</span><span class="sxs-lookup"><span data-stu-id="0d01b-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="0d01b-138">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="0d01b-138">Ask yourself</span></span>|<span data-ttu-id="0d01b-139">Ação</span><span class="sxs-lookup"><span data-stu-id="0d01b-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="0d01b-140">Detalhada de como você deseja as informações de endereço e o local de emergência a serem?</span><span class="sxs-lookup"><span data-stu-id="0d01b-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="0d01b-141">Para obter mais informações, consulte [Cite locais de emergência, endereços e roteamento de chamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="0d01b-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="0d01b-142">Identificação de chamadas</span><span class="sxs-lookup"><span data-stu-id="0d01b-142">Calling identity</span></span>

<span data-ttu-id="0d01b-143">Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (ID de chamador).</span><span class="sxs-lookup"><span data-stu-id="0d01b-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="0d01b-144">O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.</span><span class="sxs-lookup"><span data-stu-id="0d01b-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="0d01b-145">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="0d01b-145">Ask yourself</span></span>|<span data-ttu-id="0d01b-146">Ação</span><span class="sxs-lookup"><span data-stu-id="0d01b-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="0d01b-147">Eu quiser mascarar ou desabilitar o ID do chamador?</span><span class="sxs-lookup"><span data-stu-id="0d01b-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="0d01b-148">Para alterar ou bloquear a ID do chamador, consulte [definir a identificação do chamador para um usuário](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="0d01b-148">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||




