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
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre o Roteamento Direto, como configuração, decisões de implantação principais necessárias e considerações de roteamento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c5120f60778879be0978cb80c56daf99e5b5a38
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031817"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="6859c-103">Roteamento Direto do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="6859c-103">Phone System Direct Routing</span></span>

<span data-ttu-id="6859c-104">Você concluiu a [Introdução](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="6859c-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="6859c-105">Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização.</span><span class="sxs-lookup"><span data-stu-id="6859c-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="6859c-106">Talvez você tenha implantado [Reuniões & conferência.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="6859c-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="6859c-107">Agora você está pronto para adicionar cargas de trabalho de voz na nuvem e decidiu usar sua própria operadora de telefonia para conectividade PSTN (Rede Telefônica Pública Comutado) usando Roteamento Direto do Sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="6859c-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="6859c-108">Com o Roteamento Direto, você pode usar o Sistema de Telefonia praticamente com qualquer portadora de telefonia.</span><span class="sxs-lookup"><span data-stu-id="6859c-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="6859c-109">Este artigo descreve as principais decisões de implantação para Roteamento Direto, bem como considerações adicionais que você pode querer pensar, com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6859c-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="6859c-110">Você também deve ler [o Cloud Voice no Microsoft Teams](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6859c-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="6859c-111">Saiba mais sobre o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="6859c-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="6859c-112">Os artigos a seguir fornecem mais informações sobre como configurar e usar o Roteamento Direto do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="6859c-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="6859c-113">Configurar o Roteamento Direto requer compreensão do design de roteamento PSTN.</span><span class="sxs-lookup"><span data-stu-id="6859c-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="6859c-114">Você deve ler todos esses artigos para entender como planejar e configurar o Roteamento Direto:</span><span class="sxs-lookup"><span data-stu-id="6859c-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="6859c-115">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="6859c-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="6859c-116">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="6859c-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="6859c-117">Lista de controladores de borda da sessão certificados para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="6859c-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="6859c-118">Monitorar e solucionar problemas do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="6859c-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="6859c-119">Além disso, talvez você queira ler os seguintes artigos, dependendo das suas necessidades:</span><span class="sxs-lookup"><span data-stu-id="6859c-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="6859c-120">Configurar um controlador de borda da sessão para vários locatários</span><span class="sxs-lookup"><span data-stu-id="6859c-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="6859c-121">Migrar para o roteamento direto</span><span class="sxs-lookup"><span data-stu-id="6859c-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="6859c-122">Contas de usuário em um ambiente híbrido com conectividade PSTN</span><span class="sxs-lookup"><span data-stu-id="6859c-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="6859c-123">Assista à sessão a seguir para saber mais sobre o Roteamento Direto: [Roteamento Direto no Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="6859c-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="6859c-124">Decisões importantes sobre implantação</span><span class="sxs-lookup"><span data-stu-id="6859c-124">Core deployment decisions</span></span>

<span data-ttu-id="6859c-125">Estas são as principais decisões a considerar para o Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="6859c-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="6859c-126">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="6859c-126">Ask yourself</span></span>|<span data-ttu-id="6859c-127">Ação</span><span class="sxs-lookup"><span data-stu-id="6859c-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="6859c-128">Para quais usuários habilitarei o Roteamento Direto?</span><span class="sxs-lookup"><span data-stu-id="6859c-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="6859c-129">Para obter mais informações, consulte [Habilitar usuários para o Serviço de Roteamento Direto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="6859c-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="6859c-130">Eu tenho as licenças necessárias para Roteamento Direto?</span><span class="sxs-lookup"><span data-stu-id="6859c-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="6859c-131">Para obter mais informações, consulte [Licenciamento e outros requisitos.](direct-routing-plan.md#licensing-and-other-requirements)</span><span class="sxs-lookup"><span data-stu-id="6859c-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="6859c-132">Considerações sobre o Controlador de Borda de Sessão (SBC)</span><span class="sxs-lookup"><span data-stu-id="6859c-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="6859c-133">Com o Roteamento Direto, você conecta seu próprio Controlador de Borda de Sessão (SBC) diretamente ao Sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="6859c-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="6859c-134">Para ver uma lista de SBCs certificados, consulte Controladores de Borda de Sessão [com Suporte.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="6859c-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="6859c-135">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="6859c-135">Ask yourself</span></span>|<span data-ttu-id="6859c-136">Ação</span><span class="sxs-lookup"><span data-stu-id="6859c-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="6859c-137">Onde e como implantarei SBCs?</span><span class="sxs-lookup"><span data-stu-id="6859c-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="6859c-138">Para obter mais informações, consulte [Configurar Roteamento Direto](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="6859c-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="6859c-139">Tenho vários locatários?</span><span class="sxs-lookup"><span data-stu-id="6859c-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="6859c-140">Para obter mais informações, [consulte Configurar um Controlador de Borda de Sessão para vários locatários.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="6859c-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="6859c-141">Considerações sobre o roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="6859c-141">Voice routing considerations</span></span>

<span data-ttu-id="6859c-142">Você precisará configurar o Sistema telefônico para encaminhar as chamadas para os SBCs específicos.</span><span class="sxs-lookup"><span data-stu-id="6859c-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="6859c-143">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="6859c-143">Ask yourself</span></span>|<span data-ttu-id="6859c-144">Ação</span><span class="sxs-lookup"><span data-stu-id="6859c-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="6859c-145">Quais políticas de roteamento de voz, uso de PSTN e rotas de voz eu preciso criar?</span><span class="sxs-lookup"><span data-stu-id="6859c-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="6859c-146">Para obter informações de roteamento de voz, consulte [Configurar Roteamento de Voz.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="6859c-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="6859c-147">Quais usuários serão atribuídos à política de roteamento de voz que eu definir?</span><span class="sxs-lookup"><span data-stu-id="6859c-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="6859c-148">Veja os exemplos em [Configurar Roteamento de Voz.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="6859c-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="6859c-149">Garantir que as chamadas de entrada chegam ao cliente do Teams usando o TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="6859c-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="6859c-150">O Roteamento Direto só tem suporte no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6859c-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="6859c-151">Para receber chamadas PSTN por meio do Roteamento Direto, você precisa configurar o TeamsUpgradePolicy para garantir que as chamadas de entrada sejam recebidas no Teams.</span><span class="sxs-lookup"><span data-stu-id="6859c-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="6859c-152">Os usuários devem estar no modo Somente equipes, o que você pode fazer atribuindo a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="6859c-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="6859c-153">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="6859c-153">Ask yourself</span></span>|<span data-ttu-id="6859c-154">Ação</span><span class="sxs-lookup"><span data-stu-id="6859c-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="6859c-155">O que significa o modo Somente equipes?</span><span class="sxs-lookup"><span data-stu-id="6859c-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="6859c-156">Para obter mais informações, consulte as diretrizes de migração e interoperabilidade para [organizações que usam o Teams em conjunto com o Skype for Business.](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="6859c-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="6859c-157">Considerações adicionais sobre a implantação</span><span class="sxs-lookup"><span data-stu-id="6859c-157">Additional deployment considerations</span></span>

<span data-ttu-id="6859c-158">Talvez você queira considerar o seguinte, com base nas necessidades e configurações da sua organização:</span><span class="sxs-lookup"><span data-stu-id="6859c-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="6859c-159">Pergunte a si mesmo</span><span class="sxs-lookup"><span data-stu-id="6859c-159">Ask yourself</span></span>| <span data-ttu-id="6859c-160">Ação</span><span class="sxs-lookup"><span data-stu-id="6859c-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="6859c-161">Você tem uma implantação existente do Skype for Business Server com conectividade híbrida configurada?</span><span class="sxs-lookup"><span data-stu-id="6859c-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="6859c-162">Para entender como as contas de usuário em um ambiente híbrido são provisionadas e gerenciadas, consulte Contas de usuário em um ambiente híbrido com [conectividade PSTN.](direct-routing-user-accounts-in-a-hybrid-environment.md)</span><span class="sxs-lookup"><span data-stu-id="6859c-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="6859c-163">Você está migrando para o Roteamento Direto do Plano de Chamada ou de um ambiente local do Skype for Business?</span><span class="sxs-lookup"><span data-stu-id="6859c-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="6859c-164">Para entender mais sobre como migrar para o Roteamento Direto de um ambiente existente, consulte [Migrar para Roteamento Direto.](direct-routing-migrating.md)</span><span class="sxs-lookup"><span data-stu-id="6859c-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
