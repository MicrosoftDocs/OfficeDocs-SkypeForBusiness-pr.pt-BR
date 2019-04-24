---
title: Roteamento Direto do Sistema Telefônico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: Página de aterrissagem do roteamento direto
appliesto: Microsoft Teams
ms.openlocfilehash: 8f2e213b1e77217640f66e050f470b66f9750ef0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198088"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="470b3-103">Roteamento Direto do Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="470b3-103">Phone System Direct Routing</span></span>

<span data-ttu-id="470b3-104">Você concluiu a [Introdução](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="470b3-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="470b3-105">Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização.</span><span class="sxs-lookup"><span data-stu-id="470b3-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="470b3-106">Talvez você implantou [conferência de & de reuniões](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="470b3-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="470b3-107">Agora você está pronto para adicionar as cargas de trabalho de voz de nuvem e você decidiu usar sua próprias operadora de telefonia para conectividade de rede de telefônica pública comutada (PSTN) usando o recurso de roteamento direto de sistema do telefone.</span><span class="sxs-lookup"><span data-stu-id="470b3-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="470b3-108">Com o roteamento direto, você pode usar o sistema telefônico com praticamente qualquer operadora de telefonia.</span><span class="sxs-lookup"><span data-stu-id="470b3-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="470b3-109">Este artigo descreve as principais decisões sobre implantação para roteamento direto, bem como considerações adicionais que talvez você queira pensar, com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="470b3-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="470b3-110">Você também deve ler [Nuvem de voz equipes da Microsoft](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="470b3-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="470b3-111">Saiba mais sobre o roteamento direto</span><span class="sxs-lookup"><span data-stu-id="470b3-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="470b3-112">Os artigos a seguir fornecem mais informações sobre como configurar e usar roteamento de telefone sistema direto.</span><span class="sxs-lookup"><span data-stu-id="470b3-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="470b3-113">Configurando o roteamento direto requer uma compreensão do design de roteamento de PSTN.</span><span class="sxs-lookup"><span data-stu-id="470b3-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="470b3-114">Você deve ler todos estes artigos para entender como planejar e configurar o roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="470b3-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="470b3-115">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="470b3-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="470b3-116">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="470b3-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="470b3-117">Lista de controladores de borda da sessão certificados para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="470b3-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="470b3-118">Monitorar e solucionar problemas do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="470b3-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="470b3-119">Além disso, convém ler os artigos a seguir, dependendo dos requisitos:</span><span class="sxs-lookup"><span data-stu-id="470b3-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="470b3-120">Configurar um controlador de borda da sessão para vários locatários</span><span class="sxs-lookup"><span data-stu-id="470b3-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="470b3-121">Migrar para o roteamento direto</span><span class="sxs-lookup"><span data-stu-id="470b3-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="470b3-122">Contas de usuário em um ambiente híbrido com conectividade PSTN</span><span class="sxs-lookup"><span data-stu-id="470b3-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="470b3-123">Assista a sessão de seguir para saber mais sobre o roteamento direto: [Roteamento direta em equipes da Microsoft](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="470b3-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="470b3-124">Decisões principais de implantação</span><span class="sxs-lookup"><span data-stu-id="470b3-124">Core deployment decisions</span></span>

<span data-ttu-id="470b3-125">Estas são as decisões principais a serem considerados para roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="470b3-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="470b3-126">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="470b3-126">Ask yourself</span></span>|<span data-ttu-id="470b3-127">Ação</span><span class="sxs-lookup"><span data-stu-id="470b3-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="470b3-128">Para os usuários que eu habilitará o roteamento direto?</span><span class="sxs-lookup"><span data-stu-id="470b3-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="470b3-129">Para obter mais informações, consulte [habilitar usuários para atendimento de roteamento direto](direct-routing-configure.md#enable-users-for-direct-routing-service).</span><span class="sxs-lookup"><span data-stu-id="470b3-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="470b3-130">Eu tenho as licenças necessárias para roteamento direto?</span><span class="sxs-lookup"><span data-stu-id="470b3-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="470b3-131">Para obter mais informações, consulte [licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="470b3-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="470b3-132">Considerações de controlador de borda (SBC) da sessão</span><span class="sxs-lookup"><span data-stu-id="470b3-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="470b3-133">Com o roteamento direto, você pode conectar seu próprio controlador de borda de sessão (SBC) diretamente ao sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="470b3-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="470b3-134">Para obter uma lista de certificados SBCs, consulte [Suporte para controladores de borda de sessão](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="470b3-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="470b3-135">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="470b3-135">Ask yourself</span></span>|<span data-ttu-id="470b3-136">Ação</span><span class="sxs-lookup"><span data-stu-id="470b3-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="470b3-137">Onde e como posso implantará SBCs?</span><span class="sxs-lookup"><span data-stu-id="470b3-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="470b3-138">Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="470b3-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="470b3-139">Eu tenho vários locatários?</span><span class="sxs-lookup"><span data-stu-id="470b3-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="470b3-140">Para obter mais informações, consulte [Configurar um controlador de borda de sessão para vários locatários](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="470b3-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="470b3-141">Considerações sobre o roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="470b3-141">Voice routing considerations</span></span>

<span data-ttu-id="470b3-142">Você precisará configurar o sistema telefônico para rotear as chamadas para os SBCs específicos.</span><span class="sxs-lookup"><span data-stu-id="470b3-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="470b3-143">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="470b3-143">Ask yourself</span></span>|<span data-ttu-id="470b3-144">Ação</span><span class="sxs-lookup"><span data-stu-id="470b3-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="470b3-145">Quais políticas de roteamento de voz, uso da PSTN e roteamentos de voz preciso criar?</span><span class="sxs-lookup"><span data-stu-id="470b3-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="470b3-146">Para informações de roteamento de voz, consulte [Configurar o roteamento de voz](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="470b3-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="470b3-147">Os usuários que serão atribuídos para a política de roteamento de voz que eu definem?</span><span class="sxs-lookup"><span data-stu-id="470b3-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="470b3-148">Consulte os exemplos em [Configurar o roteamento de voz](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="470b3-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="470b3-149">Políticas de chamada e de interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="470b3-149">Calling and interop policies</span></span>

<span data-ttu-id="470b3-150">Roteamento direto somente é compatível com Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="470b3-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="470b3-151">Para fazer ou receber chamadas PSTN por meio de roteamento direto, você precisa configurar as políticas necessárias para garantir que as chamadas recebidas são recebidas em equipes.</span><span class="sxs-lookup"><span data-stu-id="470b3-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="470b3-152">Você pode configurar usuários para definir as equipes como seu cliente preferencial para chamadas por Configurando o usuário para o modo somente equipes ou configuração de equipes como o cliente de chamada preferencial, atribuindo o TeamsCallingPolicy e o TeamsInteropPolicy.</span><span class="sxs-lookup"><span data-stu-id="470b3-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="470b3-153">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="470b3-153">Ask yourself</span></span>|<span data-ttu-id="470b3-154">Ação</span><span class="sxs-lookup"><span data-stu-id="470b3-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="470b3-155">Como serão definidas equipes como cliente preferencial para chamadas?</span><span class="sxs-lookup"><span data-stu-id="470b3-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="470b3-156">Para obter mais informações, consulte [definir equipes da Microsoft como o preferencial chamar cliente para usuários](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span><span class="sxs-lookup"><span data-stu-id="470b3-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="470b3-157">Outras considerações sobre implantação</span><span class="sxs-lookup"><span data-stu-id="470b3-157">Additional deployment considerations</span></span>

<span data-ttu-id="470b3-158">Talvez você queira, considere o seguinte, com base nas necessidades e a configuração da sua organização:</span><span class="sxs-lookup"><span data-stu-id="470b3-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="470b3-159">Pergunte-se</span><span class="sxs-lookup"><span data-stu-id="470b3-159">Ask yourself</span></span>| <span data-ttu-id="470b3-160">Ação</span><span class="sxs-lookup"><span data-stu-id="470b3-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="470b3-161">Você tem um Skype existente para implantação de servidor de negócios com conectividade híbrida configurada?</span><span class="sxs-lookup"><span data-stu-id="470b3-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="470b3-162">Para entender como as contas de usuário em um ambiente híbrido são provisionadas e gerenciados, consulte [contas de usuário em um ambiente híbrido com conectividade PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="470b3-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="470b3-163">Você está migrando roteamento direta a partir de chamar planejar ou um Skype para ambiente de local de negócios?</span><span class="sxs-lookup"><span data-stu-id="470b3-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="470b3-164">Para entender mais sobre a migração para o roteamento direta a partir de um ambiente existente, consulte [Migrando para o roteamento direto](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="470b3-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
