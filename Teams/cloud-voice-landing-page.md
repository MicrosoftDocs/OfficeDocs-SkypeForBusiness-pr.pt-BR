---
title: Voz na nuvem no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Página de aterrissagem à implantação de voz de nuvem em equipes
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93a17e76444efbc57f2d8043ca1e6eda68806263
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30465304"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="c11e5-103">Voz na nuvem no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c11e5-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="c11e5-104">Você concluiu a [Introdução](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="c11e5-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="c11e5-105">Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização.</span><span class="sxs-lookup"><span data-stu-id="c11e5-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="c11e5-106">Talvez você implantou [conferência de & de reuniões](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c11e5-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="c11e5-107">Agora você está pronto para adicionar recursos de voz de nuvem para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="c11e5-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="c11e5-108">Voz nuvem oferece recursos de Private Branch Exchange (PBX) e as opções para conectar-se para a comutação telefônica PSTN (rede pública).</span><span class="sxs-lookup"><span data-stu-id="c11e5-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="c11e5-109">Este artigo ajuda você a decidir se você precisa alterar as configurações de voz da nuvem padrão, com base no perfil da sua organização e requisitos de negócios, e em seguida, ele o orienta durante cada alteração.</span><span class="sxs-lookup"><span data-stu-id="c11e5-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="c11e5-110">Podemos ter dividir as configurações em dois grupos, começando com o conjunto básico de [alterações que estão mais provável fazer](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="c11e5-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="c11e5-111">O segundo grupo inclui [configurações adicionais](#additional-deployment-decisions) que poderão ser configuradas com base nas necessidades da organização.</span><span class="sxs-lookup"><span data-stu-id="c11e5-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="c11e5-112">É recomendável que todas as organizações for percorrendo as decisões de núcleo e em seguida, se sua organização tiver requisitos adicionais, examine o material a seguir.</span><span class="sxs-lookup"><span data-stu-id="c11e5-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="c11e5-113">Saiba mais sobre voz de nuvem</span><span class="sxs-lookup"><span data-stu-id="c11e5-113">Learn more about cloud voice</span></span>

<span data-ttu-id="c11e5-114">Os artigos a seguir fornecem mais informações sobre a implantação e uso de recursos de voz de nuvem em equipes:</span><span class="sxs-lookup"><span data-stu-id="c11e5-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="c11e5-115">Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="c11e5-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="c11e5-116">Sistema telefônico com a chamada de plano</span><span class="sxs-lookup"><span data-stu-id="c11e5-116">Phone System with Calling Plan</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="c11e5-117">Roteamento Direto do Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="c11e5-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="c11e5-118">Implantação do Cloud Voice</span><span class="sxs-lookup"><span data-stu-id="c11e5-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="c11e5-119">Soluções de telefonia da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c11e5-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="c11e5-120">Assista a sessão a seguir para saber mais sobre o sistema telefônico: [Introdução ao sistema de telefone em equipes da Microsoft](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="c11e5-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="c11e5-121">Decisões importantes sobre implantação</span><span class="sxs-lookup"><span data-stu-id="c11e5-121">Core deployment decisions</span></span>

<span data-ttu-id="c11e5-122">Estas são as configurações que a maioria das organizações deseja alterar (se as configurações padrão do Teams não atenderem às necessidades da organização).</span><span class="sxs-lookup"><span data-stu-id="c11e5-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="c11e5-123">Sistema telefônico (Office 365)</span><span class="sxs-lookup"><span data-stu-id="c11e5-123">Phone System (Office 365)</span></span>

<span data-ttu-id="c11e5-124">Sistema telefônico é uma tecnologia da Microsoft para habilitar o controle de chamada e os recursos na nuvem do Office 365 Private Branch Exchange (PBX).</span><span class="sxs-lookup"><span data-stu-id="c11e5-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="c11e5-125">Sistema telefônico permite que você substitua o seu sistema Private Branch Exchange (PBX) existente um conjunto de recursos entregues diretamente do Office 365 e estreitamente integrado ao experiência de produtividade de nuvem da empresa.</span><span class="sxs-lookup"><span data-stu-id="c11e5-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="c11e5-126">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="c11e5-126">Ask yourself</span></span>|<span data-ttu-id="c11e5-127">Ação</span><span class="sxs-lookup"><span data-stu-id="c11e5-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="c11e5-128">Em que os locais do usuário ou escritórios eu implementará sistema telefônico?</span><span class="sxs-lookup"><span data-stu-id="c11e5-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="c11e5-129">Para obter mais informações sobre o sistema telefônico, consulte [o que é o sistema telefônico no Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c11e5-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="c11e5-130">A Conexão ao público Switched Telephone Network (PSTN)</span><span class="sxs-lookup"><span data-stu-id="c11e5-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="c11e5-131">Para conectar o sistema telefônico para a comutação telefônica PSTN (rede pública) para que os usuários podem fazer chamadas telefônicas em todo o mundo, você tem opções com base em suas necessidades comerciais.</span><span class="sxs-lookup"><span data-stu-id="c11e5-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="c11e5-132">Pergunte-se o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c11e5-132">Ask yourself the following:</span></span>


|<span data-ttu-id="c11e5-133">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="c11e5-133">Ask yourself</span></span>|<span data-ttu-id="c11e5-134">Ação</span><span class="sxs-lookup"><span data-stu-id="c11e5-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="c11e5-135">Você deseja usar o Microsoft chamar planejar como minha operadora de telefonia?</span><span class="sxs-lookup"><span data-stu-id="c11e5-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="c11e5-136">Para obter mais informações, consulte [Sistema telefônico com planos de chamada](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c11e5-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="c11e5-137">É necessário usar meu próprios operadora de telefonia?</span><span class="sxs-lookup"><span data-stu-id="c11e5-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="c11e5-138">Para obter mais informações, consulte [Sistema telefônico com o roteamento direto](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c11e5-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="c11e5-139">Decisões adicionais de implantação</span><span class="sxs-lookup"><span data-stu-id="c11e5-139">Additional deployment decisions</span></span>

<span data-ttu-id="c11e5-140">Talvez você queira alterar as configurações para o seguinte, com base nas necessidades e a configuração da sua organização:</span><span class="sxs-lookup"><span data-stu-id="c11e5-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="c11e5-141">Caixa postal</span><span class="sxs-lookup"><span data-stu-id="c11e5-141">Voicemail</span></span>
- <span data-ttu-id="c11e5-142">Identificação de chamadas</span><span class="sxs-lookup"><span data-stu-id="c11e5-142">Calling identity</span></span>
- <span data-ttu-id="c11e5-143">Números de telefone da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c11e5-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="c11e5-144">Planos de discagem</span><span class="sxs-lookup"><span data-stu-id="c11e5-144">Dial plans</span></span>
- <span data-ttu-id="c11e5-145">Filas de chamadas</span><span class="sxs-lookup"><span data-stu-id="c11e5-145">Call queues</span></span>
- <span data-ttu-id="c11e5-146">Atendedores automáticos</span><span class="sxs-lookup"><span data-stu-id="c11e5-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="c11e5-147">Caixa postal</span><span class="sxs-lookup"><span data-stu-id="c11e5-147">Voicemail</span></span>

<span data-ttu-id="c11e5-148">Caixa postal de sistema telefônico, possibilitada pela serviços de caixa postal do Azure, suporta depósitos de correio de voz em somente caixas postais do Exchange e não oferece suporte a sistemas de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c11e5-148">Phone System voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="c11e5-149">A caixa postal do Sistema de Telefonia inclui transcrição da caixa postal que, por padrão, está habilitada para todos os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="c11e5-149">Phone System voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="c11e5-150">Suas necessidades de negócios podem exigir que você desative as transcrições de caixa postal para usuários específicos ou todos em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="c11e5-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="c11e5-151">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="c11e5-151">Ask yourself</span></span>|<span data-ttu-id="c11e5-152">Ação</span><span class="sxs-lookup"><span data-stu-id="c11e5-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c11e5-153">Você deseja habilitar a caixa postal de sistema telefônico?</span><span class="sxs-lookup"><span data-stu-id="c11e5-153">Do I want to enable Phone System voicemail?</span></span> | <span data-ttu-id="c11e5-154">Para obter procedimentos de instalação de caixa postal, consulte [Configure a caixa postal do sistema telefônico](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c11e5-154">For voicemail setup procedures, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="c11e5-155">Você deseja habilitar a transcrição do correio de voz para alguns ou todos os meus usuários?</span><span class="sxs-lookup"><span data-stu-id="c11e5-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="c11e5-156">Para desativar a transcrição do correio de voz, consulte [definir políticas de caixa postal na sua organização](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="c11e5-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="c11e5-157">Identificação de chamadas</span><span class="sxs-lookup"><span data-stu-id="c11e5-157">Calling identity</span></span>

<span data-ttu-id="c11e5-158">Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (ID de chamador).</span><span class="sxs-lookup"><span data-stu-id="c11e5-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="c11e5-159">O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.</span><span class="sxs-lookup"><span data-stu-id="c11e5-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="c11e5-160">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="c11e5-160">Ask yourself</span></span>|<span data-ttu-id="c11e5-161">Ação</span><span class="sxs-lookup"><span data-stu-id="c11e5-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="c11e5-162">Eu quiser mascarar ou desabilitar o ID do chamador?</span><span class="sxs-lookup"><span data-stu-id="c11e5-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="c11e5-163">Para alterar ou bloquear a ID do chamador, consulte [definir a identificação do chamador para um usuário](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="c11e5-163">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="c11e5-164">Números de telefone da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c11e5-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="c11e5-165">A Microsoft tem dois tipos de números de telefone disponíveis: números de *telefone do assinante* (usuário), que podem ser atribuídos aos usuários em sua organização e números de *serviço* , disponíveis como Chamada Tarifada e números gratuitos de serviço, que possuem chamada simultânea superior capacidade que os números de telefone do assinante e podem ser atribuídas aos serviços, como a conferência de áudio, atendedores automáticos ou chamada filas.</span><span class="sxs-lookup"><span data-stu-id="c11e5-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="c11e5-166">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="c11e5-166">Ask yourself</span></span>|<span data-ttu-id="c11e5-167">Ação</span><span class="sxs-lookup"><span data-stu-id="c11e5-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="c11e5-168">Quais locais do usuário precisam novos números de telefone da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="c11e5-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="c11e5-169">Para obter informações sobre a obtenção de números de telefone, consulte [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) e [os números de telefone de Introdução para seus usuários](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="c11e5-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span> 
| <span data-ttu-id="c11e5-170">Qual tipo de número de telefone (assinante ou serviço) precisa?</span><span class="sxs-lookup"><span data-stu-id="c11e5-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="c11e5-171">Para ajudá-lo a escolher o tipo de número de telefone que você precisa, consulte [tipos diferentes de números de telefone usados para chamar planos](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="c11e5-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="c11e5-172">Como faço para números de telefone existente do porta para o Office 365?</span><span class="sxs-lookup"><span data-stu-id="c11e5-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="c11e5-173">Para obter mais informações, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c11e5-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="c11e5-174">Planos de discagem</span><span class="sxs-lookup"><span data-stu-id="c11e5-174">Dial plans</span></span>

<span data-ttu-id="c11e5-175">Um plano de discagem no recurso de sistema telefônico do Office 365 é um conjunto de regras de normalização convertem discado números de telefone em um formato alternativo (normalmente o formato e. 164) para autorização de chamada e roteamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="c11e5-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="c11e5-176">Para obter mais informações sobre os planos de discagem, confira [O que são os planos de discagem?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="c11e5-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="c11e5-177">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="c11e5-177">Ask yourself</span></span>|<span data-ttu-id="c11e5-178">Ação</span><span class="sxs-lookup"><span data-stu-id="c11e5-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c11e5-179">Minha organização precisa de um plano de discagem personalizado?</span><span class="sxs-lookup"><span data-stu-id="c11e5-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="c11e5-180">Para ajudar a determinar se você precisa de um plano de discagem personalizado, consulte [Planejando locatário planos de discagem](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="c11e5-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="c11e5-181">Quais usuários exigem um plano de discagem personalizado e qual plano de discagem de locatários deve ser atribuído a cada usuário?</span><span class="sxs-lookup"><span data-stu-id="c11e5-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="c11e5-182">Para adicionar usuários a um plano de discagem personalizada no PowerShell, consulte [criar e gerenciar planos de discagem](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="c11e5-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="c11e5-183">Filas de chamadas</span><span class="sxs-lookup"><span data-stu-id="c11e5-183">Call queues</span></span>

<span data-ttu-id="c11e5-184">Telefonema de sistema filas incluem saudações que são usadas quando alguém chama um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo operador chamada disponíveis lidar com a chamada enquanto as pessoas que chamada está escutando a música em espera.</span><span class="sxs-lookup"><span data-stu-id="c11e5-184">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="c11e5-185">Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="c11e5-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="c11e5-186">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="c11e5-186">Ask yourself</span></span>|<span data-ttu-id="c11e5-187">Ação</span><span class="sxs-lookup"><span data-stu-id="c11e5-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c11e5-188">Minha organização precisa chama filas?</span><span class="sxs-lookup"><span data-stu-id="c11e5-188">Does my organization need call queues?</span></span> | <span data-ttu-id="c11e5-189">Para obter mais informações, consulte [criar uma fila de espera de chamada de sistema telefônico](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) e a [configuração do seu sistema telefônico](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="c11e5-189">For more information, see [Create a Phone System call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="c11e5-190">Atendedores automáticos</span><span class="sxs-lookup"><span data-stu-id="c11e5-190">Auto attendants</span></span>

<span data-ttu-id="c11e5-191">Sistema telefônico atendedores automáticos podem ser usados para criar um sistema de menu para a sua organização que permite que os chamadores externos e internos mover através de um sistema de menu localizar e colocar ou transferir chamadas para usuários da empresa ou departamentos na organização.</span><span class="sxs-lookup"><span data-stu-id="c11e5-191">Phone System auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="c11e5-192">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="c11e5-192">Ask yourself</span></span>|<span data-ttu-id="c11e5-193">Ação</span><span class="sxs-lookup"><span data-stu-id="c11e5-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="c11e5-194">Minha organização precisa de atendedores automáticos?</span><span class="sxs-lookup"><span data-stu-id="c11e5-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="c11e5-195">Para obter mais informações, consulte [Cite atendedores automáticos de sistema telefônico](what-are-phone-system-auto-attendants.md) e [Configurar um atendedor automático de sistema telefônico](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="c11e5-195">For more information, see [What are Phone System auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Phone System auto attendant](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> |

### <a name="devices"></a><span data-ttu-id="c11e5-196">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="c11e5-196">Devices</span></span>

<span data-ttu-id="c11e5-197">Para obter mais informações sobre os dispositivos suportados, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c11e5-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="c11e5-198">Gerenciar seus dispositivos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c11e5-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="c11e5-199">Telefones IP</span><span class="sxs-lookup"><span data-stu-id="c11e5-199">IP Phones</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="c11e5-200">Dispositivos de áudio e vídeos USB</span><span class="sxs-lookup"><span data-stu-id="c11e5-200">USB audio and video devices</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="c11e5-201">Comunicações inteligentes para dispositivos</span><span class="sxs-lookup"><span data-stu-id="c11e5-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


