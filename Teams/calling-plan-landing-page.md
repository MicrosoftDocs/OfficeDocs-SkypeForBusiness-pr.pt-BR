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
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Página inicial do plano de chamada
appliesto:
- Microsoft Teams
ms.openlocfilehash: c62ce8a891244920257623aea9a62859161a129f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825189"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="40bf5-103">Qual plano de chamadas é ideal para você?</span><span class="sxs-lookup"><span data-stu-id="40bf5-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="40bf5-104">Você concluiu a [introdução](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="40bf5-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="40bf5-105">Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização.</span><span class="sxs-lookup"><span data-stu-id="40bf5-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="40bf5-106">Talvez você tenha implantado [reuniões & conferência](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="40bf5-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="40bf5-107">Agora, você está pronto para adicionar cargas de trabalho de voz na nuvem e decidiu usar o sistema telefônico da Microsoft com plano de chamadas para se conectar à rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="40bf5-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="40bf5-108">Este artigo descreve as principais decisões de implantação para planos de chamada e outras considerações que você pode querer configurar, com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="40bf5-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="40bf5-109">Você também deve ler [voz na nuvem no Microsoft Teams](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz em nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="40bf5-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="40bf5-110">Saiba mais sobre planos de chamada</span><span class="sxs-lookup"><span data-stu-id="40bf5-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="40bf5-111">Os artigos a seguir fornecem mais informações sobre como implantar e usar planos de chamada da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="40bf5-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="40bf5-112">Sistema de telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="40bf5-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="40bf5-113">Planos de Chamadas do Office 365</span><span class="sxs-lookup"><span data-stu-id="40bf5-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="40bf5-114">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="40bf5-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="40bf5-115">Decisões principais de implantação</span><span class="sxs-lookup"><span data-stu-id="40bf5-115">Core deployment decisions</span></span>

<span data-ttu-id="40bf5-116">Para usar a Microsoft como sua operadora de telefonia, você precisa obter licenças de plano de chamada e atribuí-las aos usuários do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="40bf5-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="40bf5-117">Há dois tipos de planos de chamada disponíveis:</span><span class="sxs-lookup"><span data-stu-id="40bf5-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="40bf5-118">Planos de chamadas domésticas</span><span class="sxs-lookup"><span data-stu-id="40bf5-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="40bf5-119">Planos de chamadas locais e internacionais</span><span class="sxs-lookup"><span data-stu-id="40bf5-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="40bf5-120">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="40bf5-120">Ask yourself</span></span>|<span data-ttu-id="40bf5-121">Ação</span><span class="sxs-lookup"><span data-stu-id="40bf5-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="40bf5-122">Os planos de chamada estão disponíveis na minha área?</span><span class="sxs-lookup"><span data-stu-id="40bf5-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="40bf5-123">Quais locais de usuário terão o serviço plano de chamadas?</span><span class="sxs-lookup"><span data-stu-id="40bf5-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="40bf5-124">Para obter mais informações, consulte [disponibilidade de país e região para conferências de áudio e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="40bf5-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="40bf5-125">Meus usuários precisam fazer chamadas internacionais?</span><span class="sxs-lookup"><span data-stu-id="40bf5-125">Do my users need international calling?</span></span> | <span data-ttu-id="40bf5-126">Para obter mais informações, consulte [planos de chamada do Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="40bf5-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="40bf5-127">Os meus usuários têm licenças de planos de chamada?</span><span class="sxs-lookup"><span data-stu-id="40bf5-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="40bf5-128">Para comprar e atribuir licenças, consulte [etapa 2: comprar e atribuir licenças](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="40bf5-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="40bf5-129">Cada um dos meus usuários tem um número de telefone do Direct Inward Dial (DID)?</span><span class="sxs-lookup"><span data-stu-id="40bf5-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="40bf5-130">Para obter números de telefone, consulte a [etapa 3: obter números de telefone](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="40bf5-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="40bf5-131">Transferir números de telefone para o Office 365</span><span class="sxs-lookup"><span data-stu-id="40bf5-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="40bf5-132">É fácil transferir seus números de telefone de seu provedor de serviços atual para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="40bf5-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="40bf5-133">Depois de portar seus números de telefone para o Microsoft Teams, a Microsoft se tornará seu provedor de serviços e cobrará você por esses números de telefone.</span><span class="sxs-lookup"><span data-stu-id="40bf5-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="40bf5-134">Para obter mais informações, consulte [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="40bf5-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="40bf5-135">Números de telefone e locais de emergência</span><span class="sxs-lookup"><span data-stu-id="40bf5-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="40bf5-136">Com planos de chamada no Office 365, todos os usuários de sua organização precisam ter um número de telefone exclusivo do Direct Inward Dial (DID) e um endereço de emergência validado correspondente.</span><span class="sxs-lookup"><span data-stu-id="40bf5-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="40bf5-137">Você também pode especificar um local de emergência dentro do endereço de emergência (por exemplo, um número de escritório ou um número de chão).</span><span class="sxs-lookup"><span data-stu-id="40bf5-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="40bf5-138">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="40bf5-138">Ask yourself</span></span>|<span data-ttu-id="40bf5-139">Ação</span><span class="sxs-lookup"><span data-stu-id="40bf5-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="40bf5-140">Qual é o nível de detalhamento dos dados do endereço de emergência e do local que devem ser?</span><span class="sxs-lookup"><span data-stu-id="40bf5-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="40bf5-141">Para obter mais informações, consulte [o que são locais de emergência, endereços e encaminhamento de chamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="40bf5-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="40bf5-142">Identidade de chamada</span><span class="sxs-lookup"><span data-stu-id="40bf5-142">Calling identity</span></span>

<span data-ttu-id="40bf5-143">Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (identificação de chamadas).</span><span class="sxs-lookup"><span data-stu-id="40bf5-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="40bf5-144">O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.</span><span class="sxs-lookup"><span data-stu-id="40bf5-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="40bf5-145">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="40bf5-145">Ask yourself</span></span>|<span data-ttu-id="40bf5-146">Ação</span><span class="sxs-lookup"><span data-stu-id="40bf5-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="40bf5-147">Desejo mascarar ou desabilitar o recurso de identificação de chamadas?</span><span class="sxs-lookup"><span data-stu-id="40bf5-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="40bf5-148">Para alterar ou bloquear a identificação de chamadas, consulte [definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="40bf5-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




