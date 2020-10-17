---
title: Roteamento Direto do Sistema de Telefonia
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre o roteamento direto e entenda as decisões de implantação necessárias que você vai enfrentar.
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c988670a17a9ba2f803c11740d97404de52d4d5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497298"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="a7706-103">Roteamento Direto do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="a7706-103">Phone System Direct Routing</span></span>

<span data-ttu-id="a7706-104">Você concluiu a [Introdução](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="a7706-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="a7706-105">Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização.</span><span class="sxs-lookup"><span data-stu-id="a7706-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="a7706-106">Talvez você tenha implantado [reuniões & conferência](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="a7706-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="a7706-107">Agora, você está pronto para adicionar cargas de trabalho de voz na nuvem e decidiu usar sua própria operadora de telefonia para conectividade PSTN (rede telefônica pública comutada) usando o roteamento direto do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="a7706-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="a7706-108">Com o Roteamento Direto, você pode usar o Sistema de Telefonia praticamente com qualquer portadora de telefonia.</span><span class="sxs-lookup"><span data-stu-id="a7706-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="a7706-109">Este artigo descreve as principais decisões de implantação para roteamento direto, bem como considerações adicionais sobre as quais você pode querer pensar, com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a7706-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="a7706-110">Você também deve ler [voz na nuvem no Microsoft Teams](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz em nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7706-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="a7706-111">Saiba mais sobre o roteamento direto</span><span class="sxs-lookup"><span data-stu-id="a7706-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="a7706-112">Os artigos a seguir fornecem mais informações sobre como configurar e usar o roteamento direto do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="a7706-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="a7706-113">Configurar o roteamento direto requer a compreensão do design de roteamento PSTN.</span><span class="sxs-lookup"><span data-stu-id="a7706-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="a7706-114">Você deve ler todos esses artigos para entender como planejar e configurar o roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="a7706-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="a7706-115">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="a7706-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="a7706-116">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="a7706-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="a7706-117">Lista de controladores de borda da sessão certificados para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="a7706-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="a7706-118">Monitorar e solucionar problemas do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="a7706-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="a7706-119">Além disso, talvez você queira ler os seguintes artigos dependendo dos seus requisitos:</span><span class="sxs-lookup"><span data-stu-id="a7706-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="a7706-120">Configurar um controlador de borda da sessão para vários locatários</span><span class="sxs-lookup"><span data-stu-id="a7706-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="a7706-121">Migrar para o roteamento direto</span><span class="sxs-lookup"><span data-stu-id="a7706-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="a7706-122">Contas de usuário em um ambiente híbrido com conectividade PSTN</span><span class="sxs-lookup"><span data-stu-id="a7706-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="a7706-123">Assista à sessão a seguir para saber mais sobre o roteamento direto: [Roteamento direto no Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="a7706-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="a7706-124">Decisões importantes sobre implantação</span><span class="sxs-lookup"><span data-stu-id="a7706-124">Core deployment decisions</span></span>

<span data-ttu-id="a7706-125">Estas são as principais decisões a serem consideradas para o roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="a7706-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="a7706-126">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="a7706-126">Ask yourself</span></span>|<span data-ttu-id="a7706-127">Ação</span><span class="sxs-lookup"><span data-stu-id="a7706-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="a7706-128">Para quais usuários o roteamento direto será habilitado?</span><span class="sxs-lookup"><span data-stu-id="a7706-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="a7706-129">Para obter mais informações, consulte [habilitar usuários para o serviço de roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="a7706-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="a7706-130">Tenho as licenças necessárias para o roteamento direto?</span><span class="sxs-lookup"><span data-stu-id="a7706-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="a7706-131">Para obter mais informações, consulte [Licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="a7706-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="a7706-132">Considerações sobre o controlador de borda de sessão (SBC)</span><span class="sxs-lookup"><span data-stu-id="a7706-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="a7706-133">Com o roteamento direto, você conecta seu próprio controlador de borda de sessão (SBC) diretamente ao sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="a7706-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="a7706-134">Para obter uma lista de SBCs certificados, consulte [controladores de borda de sessão com suporte](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="a7706-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="a7706-135">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="a7706-135">Ask yourself</span></span>|<span data-ttu-id="a7706-136">Ação</span><span class="sxs-lookup"><span data-stu-id="a7706-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="a7706-137">Onde e como eu implanto o SBCs?</span><span class="sxs-lookup"><span data-stu-id="a7706-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="a7706-138">Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="a7706-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="a7706-139">Tenho vários locatários?</span><span class="sxs-lookup"><span data-stu-id="a7706-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="a7706-140">Para obter mais informações, consulte [configurar um controlador de borda de sessão para vários locatários](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="a7706-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="a7706-141">Considerações de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="a7706-141">Voice routing considerations</span></span>

<span data-ttu-id="a7706-142">Você precisará configurar o sistema de telefonia para direcionar as chamadas para o SBCs específico.</span><span class="sxs-lookup"><span data-stu-id="a7706-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="a7706-143">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="a7706-143">Ask yourself</span></span>|<span data-ttu-id="a7706-144">Ação</span><span class="sxs-lookup"><span data-stu-id="a7706-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="a7706-145">Quais políticas de roteamento de voz, uso de PSTN e rotas de voz preciso criar?</span><span class="sxs-lookup"><span data-stu-id="a7706-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="a7706-146">Para obter informações de roteamento de voz, consulte [Configurar roteamento de voz](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="a7706-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="a7706-147">Quais usuários serão atribuídos à política de roteamento de voz que eu defino?</span><span class="sxs-lookup"><span data-stu-id="a7706-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="a7706-148">Consulte os exemplos em [Configurar roteamento de voz](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="a7706-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="a7706-149">Garanta chamadas de entrada no cliente das equipes usando o TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="a7706-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="a7706-150">O roteamento direto só tem suporte no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a7706-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="a7706-151">Para receber chamadas PSTN por meio do direcionamento direto, você precisa configurar o TeamsUpgradePolicy para garantir que as chamadas recebidas sejam recebidas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a7706-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="a7706-152">Os usuários devem estar no modo somente Teams, que você pode fazer atribuindo a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="a7706-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="a7706-153">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="a7706-153">Ask yourself</span></span>|<span data-ttu-id="a7706-154">Ação</span><span class="sxs-lookup"><span data-stu-id="a7706-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="a7706-155">O que significa o modo somente Teams?</span><span class="sxs-lookup"><span data-stu-id="a7706-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="a7706-156">Para obter mais informações, consulte [orientação de migração e interoperabilidade para organizações que usam o Skype for Business em equipe](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="a7706-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="a7706-157">Considerações adicionais sobre a implantação</span><span class="sxs-lookup"><span data-stu-id="a7706-157">Additional deployment considerations</span></span>

<span data-ttu-id="a7706-158">Você pode considerar o seguinte, com base nas necessidades e configuração da sua organização:</span><span class="sxs-lookup"><span data-stu-id="a7706-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="a7706-159">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="a7706-159">Ask yourself</span></span>| <span data-ttu-id="a7706-160">Ação</span><span class="sxs-lookup"><span data-stu-id="a7706-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="a7706-161">Você tem uma implantação existente do Skype for Business Server com conectividade híbrida configurada?</span><span class="sxs-lookup"><span data-stu-id="a7706-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="a7706-162">Para entender como as contas de usuário em um ambiente híbrido são provisionadas e gerenciadas, consulte [contas de usuário em um ambiente híbrido com conectividade PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a7706-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="a7706-163">Você está migrando para o roteamento direto do plano de chamadas ou de um ambiente local do Skype for Business?</span><span class="sxs-lookup"><span data-stu-id="a7706-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="a7706-164">Para saber mais sobre a migração para o roteamento direto de um ambiente existente, confira [migrar para roteamento direto](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="a7706-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
