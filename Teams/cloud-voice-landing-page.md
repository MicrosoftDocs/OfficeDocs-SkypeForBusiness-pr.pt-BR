---
title: Voz na nuvem no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Página de aterrissagem para implantar a voz na nuvem no Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7a17e207911ad4865cef5b82f7fe7f5f143a172
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236974"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="c6c0e-103">Voz na nuvem no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6c0e-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="c6c0e-104">Você concluiu a [Introdução](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="c6c0e-105">Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="c6c0e-106">Talvez você tenha implantado [reuniões & conferência](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="c6c0e-107">Agora você está pronto para adicionar recursos de voz em nuvem para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="c6c0e-108">A Cloud Voice oferece recursos de PBX (Private Branch Exchange) e opções para conexão à rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="c6c0e-109">Este artigo ajuda você a decidir se precisa alterar qualquer uma das configurações de voz de nuvem padrão, com base nas necessidades de negócios e perfil da sua organização, e o orienta durante cada alteração.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="c6c0e-110">Dividimos as configurações em dois grupos, começando pelo conjunto básico de [alterações que você tem mais probabilidade de fazer](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="c6c0e-111">O segundo grupo inclui [configurações adicionais](#additional-deployment-decisions) que poderão ser configuradas com base nas necessidades de sua organização.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="c6c0e-112">Recomendamos que todas as organizações funcionem pelas decisões básicas e, se a sua organização tiver requisitos adicionais, revise o material a seguir.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="c6c0e-113">Saiba mais sobre a voz na nuvem</span><span class="sxs-lookup"><span data-stu-id="c6c0e-113">Learn more about cloud voice</span></span>

<span data-ttu-id="c6c0e-114">Os artigos a seguir fornecem mais informações sobre a implantação e o uso de recursos de voz na nuvem no Teams:</span><span class="sxs-lookup"><span data-stu-id="c6c0e-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="c6c0e-115">Sistema de telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="c6c0e-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="c6c0e-116">Sistema telefônico com planos de chamada</span><span class="sxs-lookup"><span data-stu-id="c6c0e-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="c6c0e-117">Roteamento Direto do Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="c6c0e-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="c6c0e-118">Implantação do Cloud Voice</span><span class="sxs-lookup"><span data-stu-id="c6c0e-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="c6c0e-119">Soluções de telefonia da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6c0e-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="c6c0e-120">Assista à sessão a seguir para saber mais sobre o sistema telefônico: [introdução ao sistema telefônico no Microsoft Teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="c6c0e-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="c6c0e-121">Decisões importantes sobre implantação</span><span class="sxs-lookup"><span data-stu-id="c6c0e-121">Core deployment decisions</span></span>

<span data-ttu-id="c6c0e-122">Estas são as configurações que a maioria das organizações deseja alterar (se as configurações padrão do Teams não atenderem às necessidades da organização).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="c6c0e-123">Sistema telefônico (Office 365)</span><span class="sxs-lookup"><span data-stu-id="c6c0e-123">Phone System (Office 365)</span></span>

<span data-ttu-id="c6c0e-124">O sistema de telefonia é a tecnologia da Microsoft para habilitar os recursos de controle de chamada e PBX (Private Branch Exchange) na nuvem do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="c6c0e-125">O sistema telefônico permite substituir seu sistema de PBX (Exchange Branch Exchange) existente por um conjunto de recursos entregues diretamente do Office 365 e totalmente integrado à experiência de produtividade na nuvem da empresa.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="c6c0e-126">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="c6c0e-126">Ask yourself</span></span>|<span data-ttu-id="c6c0e-127">Ação</span><span class="sxs-lookup"><span data-stu-id="c6c0e-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="c6c0e-128">Em quais locais e escritórios do usuário devo implementar o sistema telefônico?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="c6c0e-129">Para obter mais informações sobre o sistema telefônico, consulte [o que é o sistema telefônico no Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="c6c0e-130">Conexão com a rede telefônica pública comutada (PSTN)</span><span class="sxs-lookup"><span data-stu-id="c6c0e-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="c6c0e-131">Para conectar o sistema telefônico à rede telefônica pública comutada (PSTN) para que os usuários possam fazer chamadas telefônicas pelo mundo, você tem opções com base na necessidade dos seus negócios.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="c6c0e-132">Pergunte-se o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c6c0e-132">Ask yourself the following:</span></span>


|<span data-ttu-id="c6c0e-133">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="c6c0e-133">Ask yourself</span></span>|<span data-ttu-id="c6c0e-134">Ação</span><span class="sxs-lookup"><span data-stu-id="c6c0e-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="c6c0e-135">Desejo usar o plano de chamadas da Microsoft como minha operadora de telefonia?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="c6c0e-136">Para obter mais informações, consulte [sistema telefônico com planos de chamada](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="c6c0e-137">Preciso usar minha própria operadora de telefonia?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="c6c0e-138">Para obter mais informações, consulte [sistema telefônico com roteamento direto](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="c6c0e-139">Decisões adicionais de implantação</span><span class="sxs-lookup"><span data-stu-id="c6c0e-139">Additional deployment decisions</span></span>

<span data-ttu-id="c6c0e-140">Talvez você queira alterar as configurações para o seguinte, com base nas necessidades e configuração da sua organização:</span><span class="sxs-lookup"><span data-stu-id="c6c0e-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="c6c0e-141">Caixa postal</span><span class="sxs-lookup"><span data-stu-id="c6c0e-141">Voicemail</span></span>
- <span data-ttu-id="c6c0e-142">Identidade de chamada</span><span class="sxs-lookup"><span data-stu-id="c6c0e-142">Calling identity</span></span>
- <span data-ttu-id="c6c0e-143">Números de telefone da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6c0e-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="c6c0e-144">Planos de discagem</span><span class="sxs-lookup"><span data-stu-id="c6c0e-144">Dial plans</span></span>
- <span data-ttu-id="c6c0e-145">Filas de chamadas</span><span class="sxs-lookup"><span data-stu-id="c6c0e-145">Call queues</span></span>
- <span data-ttu-id="c6c0e-146">Atendedores automáticos</span><span class="sxs-lookup"><span data-stu-id="c6c0e-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="c6c0e-147">Caixa postal</span><span class="sxs-lookup"><span data-stu-id="c6c0e-147">Voicemail</span></span>

<span data-ttu-id="c6c0e-148">O correio de voz na nuvem, da plataforma de correio de voz do Azure, oferece suporte a depósitos de correio de voz para trocar caixas de correio somente e não é compatível com sistemas de email</span><span class="sxs-lookup"><span data-stu-id="c6c0e-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="c6c0e-149">O correio de voz na nuvem inclui a transcrição de correio de voz, que é habilitada para todos os usuários da sua organização por padrão.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="c6c0e-150">Suas necessidades comerciais podem exigir que você desabilite a transcrição de correio de voz para usuários específicos ou todos em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="c6c0e-151">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="c6c0e-151">Ask yourself</span></span>|<span data-ttu-id="c6c0e-152">Ação</span><span class="sxs-lookup"><span data-stu-id="c6c0e-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c6c0e-153">Desejo habilitar o correio de voz na nuvem?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="c6c0e-154">Para procedimentos de configuração de correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="c6c0e-155">Desejo habilitar a transcrição de correio de voz para alguns ou todos os meus usuários?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="c6c0e-156">Para desativar a transcrição de correio de voz, consulte [definindo políticas de correio de voz em sua organização](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="c6c0e-157">Identidade de chamada</span><span class="sxs-lookup"><span data-stu-id="c6c0e-157">Calling identity</span></span>

<span data-ttu-id="c6c0e-158">Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (identificação de chamadas).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="c6c0e-159">O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="c6c0e-160">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="c6c0e-160">Ask yourself</span></span>|<span data-ttu-id="c6c0e-161">Ação</span><span class="sxs-lookup"><span data-stu-id="c6c0e-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="c6c0e-162">Desejo mascarar ou desabilitar o recurso de identificação de chamadas?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="c6c0e-163">Para alterar ou bloquear a identificação de chamadas, consulte [definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-163">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="c6c0e-164">Números de telefone da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6c0e-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="c6c0e-165">A Microsoft tem dois tipos de números de telefone \*\* disponíveis: números de assinante (usuário), que podem ser atribuídos a usuários em sua organização e números de *serviço* , disponíveis como chamada de serviço de chamada tarifada e gratuita, que têm uma chamada simultânea maior capacidade do que os números de assinantes e podem ser atribuídos a serviços como conferência de áudio, atendedor automático ou filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="c6c0e-166">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="c6c0e-166">Ask yourself</span></span>|<span data-ttu-id="c6c0e-167">Ação</span><span class="sxs-lookup"><span data-stu-id="c6c0e-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="c6c0e-168">Quais locais de usuário precisam de novos números de telefone da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="c6c0e-169">Para obter informações sobre como obter números de telefone, consulte [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) e [obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="c6c0e-170">Que tipo de número de telefone (assinante ou serviço) eu preciso?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="c6c0e-171">Para ajudá-lo a escolher o tipo de número de telefone necessário, consulte [diferentes tipos de números de telefone usados para planos de chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="c6c0e-172">Como faço para portar números de telefone existentes para o Office 365?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="c6c0e-173">Para obter mais informações, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="c6c0e-174">Planos de discagem</span><span class="sxs-lookup"><span data-stu-id="c6c0e-174">Dial plans</span></span>

<span data-ttu-id="c6c0e-175">Um plano de discagem no recurso do sistema de telefonia do Office 365 é um conjunto de regras de normalização que traduz os números de telefone discada em um formato alternativo (geralmente o formato E. 164) para autorização de chamadas e encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="c6c0e-176">Para obter mais informações sobre os planos de discagem, confira [O que são os planos de discagem?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="c6c0e-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="c6c0e-177">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="c6c0e-177">Ask yourself</span></span>|<span data-ttu-id="c6c0e-178">Ação</span><span class="sxs-lookup"><span data-stu-id="c6c0e-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c6c0e-179">Minha organização precisa de um plano de discagem personalizado?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="c6c0e-180">Para ajudar a determinar se você precisa de um plano de discagem personalizado, consulte [planejando planos de discagem de locatários](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="c6c0e-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="c6c0e-181">Quais usuários exigem um plano de discagem personalizado e qual plano de discagem de locatários deve ser atribuído a cada usuário?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="c6c0e-182">Para adicionar usuários a um plano de discagem personalizado no PowerShell, consulte [criar e gerenciar planos](create-and-manage-dial-plans.md)de discagem.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="c6c0e-183">Filas de chamadas</span><span class="sxs-lookup"><span data-stu-id="c6c0e-183">Call queues</span></span>

<span data-ttu-id="c6c0e-184">As filas de chamadas na nuvem incluem Saudações que são usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de Pesquisar o próximo agente de chamada disponível para lidar com a chamada enquanto as pessoas que chamam são ouvindo música em espera.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-184">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="c6c0e-185">Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="c6c0e-186">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="c6c0e-186">Ask yourself</span></span>|<span data-ttu-id="c6c0e-187">Ação</span><span class="sxs-lookup"><span data-stu-id="c6c0e-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c6c0e-188">Minha organização precisa de filas de chamadas?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-188">Does my organization need call queues?</span></span> | <span data-ttu-id="c6c0e-189">Para obter mais informações, consulte [criar uma fila de chamadas em nuvem](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) e [Configurar o sistema telefônico](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="c6c0e-190">Atendedores automáticos</span><span class="sxs-lookup"><span data-stu-id="c6c0e-190">Auto attendants</span></span>

<span data-ttu-id="c6c0e-191">Os atendedores automáticos na nuvem podem ser usados para criar um sistema de menus para a sua organização que permite que chamadores externos e externos se movimentem por meio de um sistema de menus para localizar e fazer ou transferir chamadas para usuários ou departamentos da empresa em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c6c0e-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="c6c0e-192">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="c6c0e-192">Ask yourself</span></span>|<span data-ttu-id="c6c0e-193">Ação</span><span class="sxs-lookup"><span data-stu-id="c6c0e-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c6c0e-194">Minha organização precisa de atendedores automáticos?</span><span class="sxs-lookup"><span data-stu-id="c6c0e-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="c6c0e-195">Para obter mais informações, consulte [o que são atendedores automáticos da nuvem](what-are-phone-system-auto-attendants.md) e [Configure um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0e-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="c6c0e-196">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="c6c0e-196">Devices</span></span>

<span data-ttu-id="c6c0e-197">Para obter mais informações sobre os dispositivos compatíveis, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c6c0e-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="c6c0e-198">Gerenciar seus dispositivos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6c0e-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="c6c0e-199">Telefones IP</span><span class="sxs-lookup"><span data-stu-id="c6c0e-199">IP Phones</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="c6c0e-200">Dispositivos de áudio e vídeo USB</span><span class="sxs-lookup"><span data-stu-id="c6c0e-200">USB audio and video devices</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="c6c0e-201">Comunicações inteligentes para dispositivos</span><span class="sxs-lookup"><span data-stu-id="c6c0e-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


