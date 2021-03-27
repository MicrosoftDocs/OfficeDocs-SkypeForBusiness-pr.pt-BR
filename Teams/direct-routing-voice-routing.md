---
title: Configurar roteamento de voz para Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar o roteamento de voz com o Roteamento Direto do Sistema de Telefonia da Microsoft.
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383975"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="8e273-103">Configurar roteamento de voz para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="8e273-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="8e273-104">Este artigo descreve como configurar o roteamento de voz para Roteamento Direto do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="8e273-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="8e273-105">Esta é a etapa 3 das seguintes etapas para configurar o Roteamento Direto:</span><span class="sxs-lookup"><span data-stu-id="8e273-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="8e273-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="8e273-106">Step 1.</span></span> [<span data-ttu-id="8e273-107">Conectar o SBC ao Microsoft Phone System e validar a conexão</span><span class="sxs-lookup"><span data-stu-id="8e273-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="8e273-108">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="8e273-108">Step 2.</span></span> [<span data-ttu-id="8e273-109">Habilitar usuários para Roteamento Direto, voz e caixa postal</span><span class="sxs-lookup"><span data-stu-id="8e273-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="8e273-110">**Etapa 3. Configurar roteamento de** voz (Este artigo)</span><span class="sxs-lookup"><span data-stu-id="8e273-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="8e273-111">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="8e273-111">Step 4.</span></span> [<span data-ttu-id="8e273-112">Traduzir números para um formato alternativo</span><span class="sxs-lookup"><span data-stu-id="8e273-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="8e273-113">Para obter informações sobre todas as etapas necessárias para configurar o Roteamento Direto, consulte [Configure Direct Routing](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="8e273-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="8e273-114">Visão geral do roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="8e273-114">Voice routing overview</span></span>

<span data-ttu-id="8e273-115">O Microsoft Phone System tem um mecanismo de roteamento que permite que uma chamada seja enviada para um SBC (Controlador de Borda de Sessão) específico com base em:</span><span class="sxs-lookup"><span data-stu-id="8e273-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="8e273-116">O padrão de número chamado</span><span class="sxs-lookup"><span data-stu-id="8e273-116">The called number pattern</span></span> 
- <span data-ttu-id="8e273-117">O padrão de número chamado mais o usuário específico que faz a chamada</span><span class="sxs-lookup"><span data-stu-id="8e273-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="8e273-118">Os SBCs podem ser designados como ativos e de backup.</span><span class="sxs-lookup"><span data-stu-id="8e273-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="8e273-119">Quando o SBC configurado como ativo não estiver disponível para uma rota de chamada específica, a chamada será roteada para um SBC de backup.</span><span class="sxs-lookup"><span data-stu-id="8e273-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="8e273-120">O roteamento de voz é feito dos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="8e273-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="8e273-121">**Política de roteamento** de voz – um contêiner para usos PSTN, que pode ser atribuído a um usuário ou a vários usuários.</span><span class="sxs-lookup"><span data-stu-id="8e273-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="8e273-122">**Usos de PSTN** – um contêiner para rotas de voz e usos PSTN, que podem ser compartilhados em diferentes políticas de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="8e273-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="8e273-123">**Rotas de** voz – um padrão de número e um conjunto de gateways PSTN online a ser usado para chamadas em que o número de chamada corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="8e273-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="8e273-124">**Gateway PSTN** Online - Um ponteiro para um SBC que também armazena a configuração aplicada quando uma chamada é feita por meio do SBC, como encaminhar P-Asserted-Identity (PAI) ou Codecs Preferenciais; pode ser adicionado a rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="8e273-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="8e273-125">Considerações sobre a política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="8e273-125">Voice routing policy considerations</span></span>

<span data-ttu-id="8e273-126">Se um usuário tiver uma licença de Plano de Chamadas, as chamadas de saída desse usuário serão roteados automaticamente pela infraestrutura PSTN do Plano de Chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e273-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="8e273-127">Se você configurar e atribuir uma política de roteamento de voz online a um usuário do Plano de Chamadas, as chamadas de saída desse usuário serão verificadas para determinar se o número discado corresponde a um padrão de número definido na política de roteamento de voz online.</span><span class="sxs-lookup"><span data-stu-id="8e273-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="8e273-128">Se houver uma combinação, a chamada será roteada pelo tronco de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="8e273-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="8e273-129">Se não houver nenhuma combinação, a chamada será roteada pela infraestrutura PSTN do Plano de Chamada.</span><span class="sxs-lookup"><span data-stu-id="8e273-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="8e273-130">Se você configurar e aplicar a política de roteamento de voz online global (padrão em toda a organização), todos os usuários habilitados para voz em sua organização herdarão essa política, o que pode resultar em chamadas PSTN de usuários do Plano de Chamadas sendo roteados inadvertidamente para um tronco de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="8e273-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="8e273-131">Se você não quiser que todos os usuários usem a política global de roteamento de voz online, configure uma política de roteamento de voz online personalizada e atribua-a a usuários individuais habilitados para voz.</span><span class="sxs-lookup"><span data-stu-id="8e273-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="8e273-132">Exemplo 1: roteamento de voz com um uso PSTN</span><span class="sxs-lookup"><span data-stu-id="8e273-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="8e273-133">O diagrama a seguir mostra dois exemplos de políticas de roteamento de voz em um fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8e273-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="8e273-134">**Fluxo de chamada 1 (à esquerda):** Se um usuário fizer uma chamada para +1 425 XXX XX XX ou +1 206 XXX XX, a chamada será roteada para SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="8e273-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="8e273-135">Se nem sbc1.contoso.biz nem sbc2.contoso.biz estão disponíveis, a chamada será retirada.</span><span class="sxs-lookup"><span data-stu-id="8e273-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="8e273-136">**Fluxo de chamada 2 (à direita):** Se um usuário fizer uma chamada para +1 425 XXX XX XX ou +1 206 XXX XX, a chamada será roteada pela primeira vez para SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="8e273-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="8e273-137">Se nenhum SBC estiver disponível, a rota com prioridade mais baixa será tentada (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="8e273-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="8e273-138">Se nenhum dos SBCs estiver disponível, a chamada será retirada.</span><span class="sxs-lookup"><span data-stu-id="8e273-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Mostra exemplos de política de roteamento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="8e273-140">Em ambos os exemplos, enquanto a rota de voz é atribuída prioridades, os SBCs nas rotas são tentados em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="8e273-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8e273-141">A menos que o usuário também tenha uma licença do Plano de Chamadas da Microsoft, as chamadas para qualquer número, exceto números que coincidem com os padrões +1 425 XXX XX ou +1 206 XXX XX na configuração de exemplo, serão descartados.</span><span class="sxs-lookup"><span data-stu-id="8e273-141">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="8e273-142">Se o usuário tiver uma licença de Plano de Chamada, a chamada será roteada automaticamente de acordo com as políticas do Plano de Chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e273-142">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="8e273-143">O Plano de Chamadas da Microsoft se aplica automaticamente como a última rota para todos os usuários com a licença do Plano de Chamadas da Microsoft e não exige configuração adicional de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8e273-143">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="8e273-144">No exemplo mostrado no diagrama a seguir, uma rota de voz é adicionada para enviar chamadas para todos os outros números dos EUA e do Canadá (chamadas que vão para o padrão de número chamado +1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="8e273-144">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra a política de roteamento de voz com uma terceira rota](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="8e273-146">Para todas as outras chamadas, se um usuário tiver ambas as licenças (Microsoft Phone System e Plano de Chamadas da Microsoft), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="8e273-146">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="8e273-147">Se nada corresponde aos padrões de número nas rotas de voz online criadas pelo administrador, a chamada será roteada por meio do Plano de Chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e273-147">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="8e273-148">Se o usuário tiver apenas o Microsoft Phone System, a chamada será descartada porque não há regras correspondentes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8e273-148">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8e273-149">O valor priority para a rota "Other +1" não importa nesse caso porque há apenas uma rota que corresponde ao padrão +1 XXX XXX XX.</span><span class="sxs-lookup"><span data-stu-id="8e273-149">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="8e273-150">Se um usuário fizer uma chamada para +1 324 567 89 89 e sbc5.contoso.biz e sbc6.contoso.biz estiver indisponível, a chamada será retirada.</span><span class="sxs-lookup"><span data-stu-id="8e273-150">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="8e273-151">A tabela a seguir resume a configuração usando três rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="8e273-151">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="8e273-152">Neste exemplo, todas as três rotas fazem parte do mesmo uso de PSTN, "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="8e273-152">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="8e273-153">Todas as rotas estão associadas ao uso de PSTN "EUA e Canadá" e o uso de PSTN está associado à política de roteamento de voz "Somente EUA".</span><span class="sxs-lookup"><span data-stu-id="8e273-153">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="8e273-154">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="8e273-154">**PSTN usage**</span></span>|<span data-ttu-id="8e273-155">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="8e273-155">**Voice route**</span></span>|<span data-ttu-id="8e273-156">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="8e273-156">**Number pattern**</span></span>|<span data-ttu-id="8e273-157">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="8e273-157">**Priority**</span></span>|<span data-ttu-id="8e273-158">**SBC**</span><span class="sxs-lookup"><span data-stu-id="8e273-158">**SBC**</span></span>|<span data-ttu-id="8e273-159">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8e273-159">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8e273-160">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="8e273-160">US and Canada</span></span>|<span data-ttu-id="8e273-161">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="8e273-161">"Redmond 1"</span></span>|<span data-ttu-id="8e273-162">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="8e273-162">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="8e273-163">1</span><span class="sxs-lookup"><span data-stu-id="8e273-163">1</span></span>|<span data-ttu-id="8e273-164">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-164">sbc1.contoso.biz</span></span><br/><span data-ttu-id="8e273-165">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-165">sbc2.contoso.biz</span></span>|<span data-ttu-id="8e273-166">Rota ativa para números chamados +1 425 XXX XX XX ou +1 206 XXX XX</span><span class="sxs-lookup"><span data-stu-id="8e273-166">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="8e273-167">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="8e273-167">US and Canada</span></span>|<span data-ttu-id="8e273-168">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="8e273-168">"Redmond 2"</span></span>|<span data-ttu-id="8e273-169">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="8e273-169">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="8e273-170">2</span><span class="sxs-lookup"><span data-stu-id="8e273-170">2</span></span>|<span data-ttu-id="8e273-171">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-171">sbc3.contoso.biz</span></span><br/><span data-ttu-id="8e273-172">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-172">sbc4.contoso.biz</span></span>|<span data-ttu-id="8e273-173">Rota de backup para números chamados +1 425 XXX XX XX ou +1 206 XXX XX</span><span class="sxs-lookup"><span data-stu-id="8e273-173">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="8e273-174">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="8e273-174">US and Canada</span></span>|<span data-ttu-id="8e273-175">"Outros +1"</span><span class="sxs-lookup"><span data-stu-id="8e273-175">"Other +1"</span></span>|<span data-ttu-id="8e273-176">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="8e273-176">^\\+1(\d{10})$</span></span>|<span data-ttu-id="8e273-177">3</span><span class="sxs-lookup"><span data-stu-id="8e273-177">3</span></span>|<span data-ttu-id="8e273-178">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-178">sbc5.contoso.biz</span></span><br/><span data-ttu-id="8e273-179">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-179">sbc6.contoso.biz</span></span>|<span data-ttu-id="8e273-180">Rote para números chamados +1 XXX XXX XX XX (exceto +1 425 XXX XX XX ou +1 206 XXX XX)</span><span class="sxs-lookup"><span data-stu-id="8e273-180">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="8e273-181">Exemplo 1: Etapas de configuração</span><span class="sxs-lookup"><span data-stu-id="8e273-181">Example 1: Configuration steps</span></span>

<span data-ttu-id="8e273-182">O exemplo a seguir mostra como:</span><span class="sxs-lookup"><span data-stu-id="8e273-182">The following example shows how to:</span></span>

1. <span data-ttu-id="8e273-183">Crie um único uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="8e273-183">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="8e273-184">Configure três rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="8e273-184">Configure three voice routes.</span></span>
3. <span data-ttu-id="8e273-185">Crie uma política de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="8e273-185">Create a voice routing policy.</span></span>
4. <span data-ttu-id="8e273-186">Atribua a política a um usuário chamado Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="8e273-186">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="8e273-187">Você pode usar o Centro de [administração do Microsoft Teams](#admincenterexample1) ou o [PowerShell](#powershellexample1) para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="8e273-187">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8e273-188">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8e273-188">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="8e273-189">Etapa 1: Criar o uso de PSTN "EUA e Canadá"</span><span class="sxs-lookup"><span data-stu-id="8e273-189">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="8e273-190">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para Roteamento Direto de Voz e, no canto superior direito, selecione Gerenciar registros de uso  >   **PSTN**.</span><span class="sxs-lookup"><span data-stu-id="8e273-190">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="8e273-191">Clique **em Adicionar**, digite EUA e **Canadá** e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-191">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="8e273-192">Etapa 2: Criar três rotas de voz (Redmond 1, Redmond 2 e Other +1)</span><span class="sxs-lookup"><span data-stu-id="8e273-192">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="8e273-193">As etapas a seguir descrevem como criar uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="8e273-193">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="8e273-194">Use estas etapas para criar as três rotas de voz chamadas Redmond 1, Redmond 2 e Other +1 para este exemplo usando as configurações descritas na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="8e273-194">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="8e273-195">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Roteamento** Direto de Voz e selecione a  >  guia **Rotas de** voz.</span><span class="sxs-lookup"><span data-stu-id="8e273-195">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="8e273-196">Clique **em Adicionar** e insira um nome e uma descrição para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="8e273-196">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="8e273-197">De definir a prioridade e especificar o padrão de número discado.</span><span class="sxs-lookup"><span data-stu-id="8e273-197">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="8e273-198">Para registrar um SBC com a rota de voz, em **SBCs inscritos (opcional),** clique em Adicionar **SBCs,** selecione os SBCs que você deseja registrar e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-198">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="8e273-199">Para adicionar registros de uso PSTN, em Registros de uso **PSTN (opcional),** clique em Adicionar uso **PSTN,** selecione os registros PSTN que você deseja adicionar e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-199">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="8e273-200">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-200">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="8e273-201">Etapa 3: criar uma política de roteamento de voz chamada "Somente EUA" e adicionar o uso de PSTN "EUA e Canadá" à política</span><span class="sxs-lookup"><span data-stu-id="8e273-201">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="8e273-202">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Políticas de roteamento **do Voice** Voice e clique  >  em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-202">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="8e273-203">Digite **US Only** como o nome e adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="8e273-203">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="8e273-204">Em **Registros de uso PSTN,** clique em Adicionar uso de **PSTN,** selecione o registro de uso PSTN "EUA e Canadá" e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-204">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="8e273-205">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-205">Click **Save**.</span></span>

<span data-ttu-id="8e273-206">Para saber mais, confira [Gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8e273-206">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="8e273-207">Etapa 4: Atribuir a política de roteamento de voz a um usuário chamado Spencer Low</span><span class="sxs-lookup"><span data-stu-id="8e273-207">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="8e273-208">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="8e273-208">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="8e273-209">Clique **em Políticas** e, ao lado de Políticas **Atribuídas,** clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-209">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="8e273-210">Em **Política de roteamento de** voz, selecione a política "Somente EUA" e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-210">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="8e273-211">Para saber mais, confira [Gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8e273-211">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8e273-212">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e273-212">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="8e273-213">Etapa 1: Criar o uso de PSTN "EUA e Canadá"</span><span class="sxs-lookup"><span data-stu-id="8e273-213">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="8e273-214">Em uma sessão remota do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="8e273-214">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="8e273-215">Verifique se o uso foi criado inserindo:</span><span class="sxs-lookup"><span data-stu-id="8e273-215">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="8e273-216">Que retorna uma lista de nomes que podem ser truncados:</span><span class="sxs-lookup"><span data-stu-id="8e273-216">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="8e273-217">O exemplo a seguir mostra o resultado da execução do `(Get-CSOnlinePSTNUsage).usage` comando do PowerShell para exibir nomes completos (não truncados):</span><span class="sxs-lookup"><span data-stu-id="8e273-217">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` PowerShell command to display full names (not truncated):</span></span>

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="8e273-218">Etapa 2: Criar três rotas de voz (Redmond 1, Redmond 2 e Other +1)</span><span class="sxs-lookup"><span data-stu-id="8e273-218">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="8e273-219">Para criar a rota "Redmond 1", em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="8e273-219">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="8e273-220">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="8e273-220">Which returns:</span></span>

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

<span data-ttu-id="8e273-221">Para criar a rota Redmond 2, digite:</span><span class="sxs-lookup"><span data-stu-id="8e273-221">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="8e273-222">Para criar a outra rota +1, digite:</span><span class="sxs-lookup"><span data-stu-id="8e273-222">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="8e273-223">Certifique-se de que sua expressão regular no atributo NumberPattern seja uma expressão válida.</span><span class="sxs-lookup"><span data-stu-id="8e273-223">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="8e273-224">Você pode testá-lo usando este site: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="8e273-224">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="8e273-225">Em alguns casos, há a necessidade de rotear todas as chamadas para o mesmo SBC; use -NumberPattern ".\*"</span><span class="sxs-lookup"><span data-stu-id="8e273-225">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="8e273-226">Rotee todas as chamadas para o mesmo SBC.</span><span class="sxs-lookup"><span data-stu-id="8e273-226">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="8e273-227">Verifique se você configurou corretamente a rota executando o `Get-CSOnlineVoiceRoute` comando do PowerShell usando opções conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="8e273-227">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="8e273-228">Que deve retornar:</span><span class="sxs-lookup"><span data-stu-id="8e273-228">Which should return:</span></span>

```console
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
```

<span data-ttu-id="8e273-229">No exemplo, a rota "Outros +1" foi atribuída automaticamente à prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="8e273-229">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="8e273-230">Etapa 3: criar uma política de roteamento de voz chamada "Somente EUA" e adicionar o uso de PSTN "EUA e Canadá" à política</span><span class="sxs-lookup"><span data-stu-id="8e273-230">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="8e273-231">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="8e273-231">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="8e273-232">O resultado é mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="8e273-232">The result is shown in this example:</span></span>

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="8e273-233">Etapa 4: Atribuir a política de roteamento de voz a um usuário chamado Spencer Low</span><span class="sxs-lookup"><span data-stu-id="8e273-233">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="8e273-234">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="8e273-234">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="8e273-235">Valide a atribuição de política inserindo este comando:</span><span class="sxs-lookup"><span data-stu-id="8e273-235">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="8e273-236">O comando retorna o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e273-236">The command returns the following:</span></span>

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="8e273-237">Exemplo 2: roteamento de voz com vários usos PSTN</span><span class="sxs-lookup"><span data-stu-id="8e273-237">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="8e273-238">A política de roteamento de voz criada no Exemplo 1 só permite chamadas para números de telefone nos EUA e no Canadá, a menos que a licença do Plano de Chamadas da Microsoft também seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="8e273-238">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="8e273-239">No exemplo a seguir, você pode criar a política de roteamento de voz "Sem Restrições".</span><span class="sxs-lookup"><span data-stu-id="8e273-239">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="8e273-240">A política reutiliza o uso de PSTN "EUA e Canadá" criado no Exemplo 1, bem como o novo uso de PSTN "Internacional".</span><span class="sxs-lookup"><span data-stu-id="8e273-240">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="8e273-241">Essa política encaminha todas as outras chamadas para os SBCs sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="8e273-241">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="8e273-242">Os exemplos mostrados atribuem a política Somente EUA ao usuário Spencer Low e a política Sem Restrições ao usuário John Woods para que o roteamento ocorra da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="8e273-242">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="8e273-243">Spencer Low – Política somente eua.</span><span class="sxs-lookup"><span data-stu-id="8e273-243">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="8e273-244">As chamadas só são permitidas para números dos EUA e do Canadá.</span><span class="sxs-lookup"><span data-stu-id="8e273-244">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="8e273-245">Ao chamar para o intervalo de números redmond, o conjunto específico de SBCs deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="8e273-245">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="8e273-246">Os números que não são dos EUA não serão roteados, a menos que a licença do Plano de Chamada seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="8e273-246">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="8e273-247">John Woods – Política internacional.</span><span class="sxs-lookup"><span data-stu-id="8e273-247">John Woods – International policy.</span></span>  <span data-ttu-id="8e273-248">As chamadas têm permissão para qualquer número.</span><span class="sxs-lookup"><span data-stu-id="8e273-248">Calls are allowed to any number.</span></span> <span data-ttu-id="8e273-249">Ao chamar para o intervalo de números redmond, o conjunto específico de SBCs deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="8e273-249">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="8e273-250">Os números que não são dos EUA serão roteados usando sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="8e273-250">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="8e273-252">Para todas as outras chamadas, se um usuário tiver ambas as licenças (Microsoft Phone System e Plano de Chamadas da Microsoft), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="8e273-252">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="8e273-253">Se nada corresponde aos padrões de número nas rotas de voz online criadas pelo administrador, a chamada será roteada usando o Plano de Chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e273-253">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="8e273-254">Se o usuário tiver apenas o Microsoft Phone System, a chamada será descartada porque não há regras correspondentes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8e273-254">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="8e273-256">A tabela a seguir resume as designações de uso e as rotas de voz da política de roteamento "Sem Restrições".</span><span class="sxs-lookup"><span data-stu-id="8e273-256">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

| <span data-ttu-id="8e273-257">Uso de PSTN</span><span class="sxs-lookup"><span data-stu-id="8e273-257">PSTN usage</span></span> | <span data-ttu-id="8e273-258">Rota de voz</span><span class="sxs-lookup"><span data-stu-id="8e273-258">Voice route</span></span> | <span data-ttu-id="8e273-259">Padrão do número</span><span class="sxs-lookup"><span data-stu-id="8e273-259">Number pattern</span></span> | <span data-ttu-id="8e273-260">Prioridade</span><span class="sxs-lookup"><span data-stu-id="8e273-260">Priority</span></span> | <span data-ttu-id="8e273-261">SBC</span><span class="sxs-lookup"><span data-stu-id="8e273-261">SBC</span></span> | <span data-ttu-id="8e273-262">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e273-262">Description</span></span> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8e273-263">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="8e273-263">US and Canada</span></span>|<span data-ttu-id="8e273-264">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="8e273-264">"Redmond 1"</span></span>|<span data-ttu-id="8e273-265">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="8e273-265">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="8e273-266">1</span><span class="sxs-lookup"><span data-stu-id="8e273-266">1</span></span>|<span data-ttu-id="8e273-267">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-267">sbc1.contoso.biz</span></span><br/><span data-ttu-id="8e273-268">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-268">sbc2.contoso.biz</span></span>|<span data-ttu-id="8e273-269">Rota ativa para números de chamador +1 425 XXX XX XX ou +1 206 XXX XX</span><span class="sxs-lookup"><span data-stu-id="8e273-269">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="8e273-270">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="8e273-270">US and Canada</span></span>|<span data-ttu-id="8e273-271">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="8e273-271">"Redmond 2"</span></span>|<span data-ttu-id="8e273-272">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="8e273-272">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="8e273-273">2</span><span class="sxs-lookup"><span data-stu-id="8e273-273">2</span></span>|<span data-ttu-id="8e273-274">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-274">sbc3.contoso.biz</span></span><br/><span data-ttu-id="8e273-275">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-275">sbc4.contoso.biz</span></span>|<span data-ttu-id="8e273-276">Rota de backup para números de chamador +1 425 XXX XX XX ou +1 206 XXX XX</span><span class="sxs-lookup"><span data-stu-id="8e273-276">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="8e273-277">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="8e273-277">US and Canada</span></span>|<span data-ttu-id="8e273-278">"Outros +1"</span><span class="sxs-lookup"><span data-stu-id="8e273-278">"Other +1"</span></span>|<span data-ttu-id="8e273-279">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="8e273-279">^\\+1(\d{10})$</span></span>|<span data-ttu-id="8e273-280">3</span><span class="sxs-lookup"><span data-stu-id="8e273-280">3</span></span>|<span data-ttu-id="8e273-281">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-281">sbc5.contoso.biz</span></span><br/><span data-ttu-id="8e273-282">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-282">sbc6.contoso.biz</span></span>|<span data-ttu-id="8e273-283">Rote para números de chamador +1 XXX XXX XX XX (exceto +1 425 XXX XX XX ou +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="8e273-283">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="8e273-284">International</span><span class="sxs-lookup"><span data-stu-id="8e273-284">International</span></span>|<span data-ttu-id="8e273-285">International</span><span class="sxs-lookup"><span data-stu-id="8e273-285">International</span></span>|<span data-ttu-id="8e273-286">\d+</span><span class="sxs-lookup"><span data-stu-id="8e273-286">\d+</span></span>|<span data-ttu-id="8e273-287">4</span><span class="sxs-lookup"><span data-stu-id="8e273-287">4</span></span>|<span data-ttu-id="8e273-288">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-288">sbc2.contoso.biz</span></span><br/><span data-ttu-id="8e273-289">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="8e273-289">sbc5.contoso.biz</span></span>|<span data-ttu-id="8e273-290">Rote para qualquer padrão de número</span><span class="sxs-lookup"><span data-stu-id="8e273-290">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="8e273-291">A ordem dos usos de PSTN em políticas de roteamento de voz é crítica.</span><span class="sxs-lookup"><span data-stu-id="8e273-291">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="8e273-292">Os usos são aplicados em ordem e, se uma combinação for encontrada no primeiro uso, outros usos nunca serão avaliados.</span><span class="sxs-lookup"><span data-stu-id="8e273-292">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="8e273-293">O uso de PSTN "Internacional" deve ser colocado após o uso de PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="8e273-293">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="8e273-294">Para alterar a ordem dos usos PSTN, execute o `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="8e273-294">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="8e273-295">Por exemplo, para alterar a ordem de "EUA e Canadá" primeiro e "Internacional" segundo para a ordem inversa executar:</span><span class="sxs-lookup"><span data-stu-id="8e273-295">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="8e273-296">A prioridade para "Outras rotas de voz +1" e "Internacional" é atribuída automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8e273-296">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="8e273-297">Eles não importam desde que tenham prioridades inferiores que "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="8e273-297">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="8e273-298">Exemplo 2: Etapas de configuração</span><span class="sxs-lookup"><span data-stu-id="8e273-298">Example 2: Configuration steps</span></span>

<span data-ttu-id="8e273-299">O exemplo a seguir mostra como:</span><span class="sxs-lookup"><span data-stu-id="8e273-299">The following example shows how to:</span></span>

1. <span data-ttu-id="8e273-300">Crie um novo uso PSTN chamado Internacional.</span><span class="sxs-lookup"><span data-stu-id="8e273-300">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="8e273-301">Crie uma nova rota de voz chamada Internacional.</span><span class="sxs-lookup"><span data-stu-id="8e273-301">Create a new voice route called International.</span></span>
3. <span data-ttu-id="8e273-302">Crie uma política de roteamento de voz chamada Sem Restrições.</span><span class="sxs-lookup"><span data-stu-id="8e273-302">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="8e273-303">Atribua a política ao usuário John Woods.</span><span class="sxs-lookup"><span data-stu-id="8e273-303">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="8e273-304">Você pode usar o Centro de [administração do Microsoft Teams](#admincenterexample2) ou o [PowerShell](#powershellexample2) para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="8e273-304">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8e273-305">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8e273-305">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="8e273-306">Etapa 1: Criar o uso de PSTN "Internacional"</span><span class="sxs-lookup"><span data-stu-id="8e273-306">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="8e273-307">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para Roteamento Direto de Voz e, no canto superior direito, selecione Gerenciar registros de uso  >   **PSTN**.</span><span class="sxs-lookup"><span data-stu-id="8e273-307">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="8e273-308">Clique **em Adicionar**, digite **Internacional** e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-308">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="8e273-309">Etapa 2: Criar a rota de voz "Internacional"</span><span class="sxs-lookup"><span data-stu-id="8e273-309">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="8e273-310">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **Roteamento** Direto de Voz e selecione a  >  guia **Rotas de** voz.</span><span class="sxs-lookup"><span data-stu-id="8e273-310">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="8e273-311">Clique **em** Adicionar , insira "Internacional" como o nome e adicione a descrição.</span><span class="sxs-lookup"><span data-stu-id="8e273-311">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="8e273-312">De definir a prioridade como 4 e, em seguida, definir o padrão de número discado como \d+.</span><span class="sxs-lookup"><span data-stu-id="8e273-312">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="8e273-313">Em **SBCs inscritos (opcional),** clique em **Adicionar SBCs,** selecione sbc2.contoso.biz e sbc5.contoso.biz e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-313">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="8e273-314">Em **Registros de uso PSTN (opcional),** clique em Adicionar uso de **PSTN,** selecione o registro de uso de PSTN "Internacional" e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-314">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="8e273-315">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-315">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="8e273-316">Etapa 3: criar uma política de roteamento de voz chamada "Sem Restrições" e adicionar os usos de PSTN "EUA e Canadá" e "Internacional" à política</span><span class="sxs-lookup"><span data-stu-id="8e273-316">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="8e273-317">O uso de PSTN "EUA e Canadá" é reutilizado nesta política de roteamento de voz para preservar o tratamento especial para chamadas para o número "+1 425 XXX XX XX" e "+1 206 XXX XX XX" como chamadas locais ou locais.</span><span class="sxs-lookup"><span data-stu-id="8e273-317">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="8e273-318">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Políticas de roteamento **do Voice** Voice e clique  >  em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-318">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="8e273-319">Digite **Sem Restrições** como o nome e adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="8e273-319">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="8e273-320">Em **Registros de uso PSTN,** clique em Adicionar uso de **PSTN,** selecione o registro de uso PSTN "EUA e Canadá" e selecione o registro de uso de PSTN "Internacional".</span><span class="sxs-lookup"><span data-stu-id="8e273-320">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="8e273-321">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-321">Click **Apply**.</span></span>

    <span data-ttu-id="8e273-322">Anote a ordem de usos PSTN:</span><span class="sxs-lookup"><span data-stu-id="8e273-322">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="8e273-323">Se uma chamada feita para o número "+1 425 XXX XX XX" com os usos configurados como neste exemplo, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial será aplicada.</span><span class="sxs-lookup"><span data-stu-id="8e273-323">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="8e273-324">Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz primeiro e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como rotas de backup.</span><span class="sxs-lookup"><span data-stu-id="8e273-324">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="8e273-325">Se o uso de PSTN "Internacional" for antes de "EUA e Canadá", as chamadas para +1 425 XXX XX serão roteados para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento.</span><span class="sxs-lookup"><span data-stu-id="8e273-325">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="8e273-326">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-326">Click **Save**.</span></span>

<span data-ttu-id="8e273-327">Para saber mais, confira [Gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8e273-327">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="8e273-328">Etapa 4: Atribuir a política de roteamento de voz a um usuário chamado John Woods</span><span class="sxs-lookup"><span data-stu-id="8e273-328">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="8e273-329">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="8e273-329">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="8e273-330">Clique **em Políticas** e, ao lado de Políticas **Atribuídas,** clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-330">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="8e273-331">Em **Política de roteamento de** voz, selecione a política "Sem restrições" e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8e273-331">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="8e273-332">O resultado é que a política de voz aplicada às chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponíveis para chamadas dos EUA, Canadá e Internacional.</span><span class="sxs-lookup"><span data-stu-id="8e273-332">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8e273-333">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e273-333">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="8e273-334">Etapa 1: Criar o uso de PSTN "Internacional"</span><span class="sxs-lookup"><span data-stu-id="8e273-334">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="8e273-335">Em uma sessão remota do PowerShell no Skype for Business Online, insira:</span><span class="sxs-lookup"><span data-stu-id="8e273-335">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="8e273-336">Etapa 2: Criar uma nova rota de voz chamada "Internacional"</span><span class="sxs-lookup"><span data-stu-id="8e273-336">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

<span data-ttu-id="8e273-337">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="8e273-337">Which returns:</span></span>

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="8e273-338">Etapa 3: Criar uma política de roteamento de voz chamada "Sem Restrições"</span><span class="sxs-lookup"><span data-stu-id="8e273-338">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="8e273-339">O uso de PSTN "Redmond 1" e "Redmond" são reutilizados nesta política de roteamento de voz para preservar o tratamento especial para chamadas para o número "+1 425 XXX XX XX" e "+1 206 XXX XX XX" como chamadas locais ou locais.</span><span class="sxs-lookup"><span data-stu-id="8e273-339">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="8e273-340">Anote a ordem de usos PSTN:</span><span class="sxs-lookup"><span data-stu-id="8e273-340">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="8e273-341">Se uma chamada feita para o número "+1 425 XXX XX XX" com os usos configurados como no exemplo a seguir, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial será aplicada.</span><span class="sxs-lookup"><span data-stu-id="8e273-341">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="8e273-342">Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz primeiro e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como rotas de backup.</span><span class="sxs-lookup"><span data-stu-id="8e273-342">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="8e273-343">Se o uso de PSTN "Internacional" for antes de "EUA e Canadá", as chamadas para +1 425 XXX XX serão roteados para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento.</span><span class="sxs-lookup"><span data-stu-id="8e273-343">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="8e273-344">Insira o comando:</span><span class="sxs-lookup"><span data-stu-id="8e273-344">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="8e273-345">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="8e273-345">Which returns:</span></span>

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="8e273-346">Etapa 4: Atribuir a política de roteamento de voz ao usuário chamado John Woods</span><span class="sxs-lookup"><span data-stu-id="8e273-346">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="8e273-347">Em seguida, verifique a atribuição usando o comando:</span><span class="sxs-lookup"><span data-stu-id="8e273-347">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="8e273-348">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="8e273-348">Which returns:</span></span>

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

<span data-ttu-id="8e273-349">O resultado é que a política de voz aplicada às chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponíveis para chamadas dos EUA, canadá e internacional.</span><span class="sxs-lookup"><span data-stu-id="8e273-349">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e273-350">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e273-350">See also</span></span>

[<span data-ttu-id="8e273-351">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="8e273-351">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="8e273-352">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="8e273-352">Configure Direct Routing</span></span>](direct-routing-configure.md)
