---
title: Configurar o roteamento de voz para Roteamento Direto
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
description: Saiba como configurar o roteamento de voz com o Roteamento Direto do Microsoft Phone System.
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530988"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="cc3ce-103">Configurar o roteamento de voz para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="cc3ce-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="cc3ce-104">Este artigo descreve como configurar o roteamento de voz para Roteamento Direto do Sistema de Telefone.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="cc3ce-105">Esta é a etapa 3 das seguintes etapas para configurar o Roteamento Direto:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="cc3ce-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-106">Step 1.</span></span> [<span data-ttu-id="cc3ce-107">Conectar o SBC ao Microsoft Phone System e validar a conexão</span><span class="sxs-lookup"><span data-stu-id="cc3ce-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="cc3ce-108">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-108">Step 2.</span></span> [<span data-ttu-id="cc3ce-109">Habilitar usuários para Roteamento Direto, voz e caixa postal</span><span class="sxs-lookup"><span data-stu-id="cc3ce-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="cc3ce-110">**Etapa 3. Configurar roteamento de** voz (este artigo)</span><span class="sxs-lookup"><span data-stu-id="cc3ce-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="cc3ce-111">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-111">Step 4.</span></span> [<span data-ttu-id="cc3ce-112">Traduzir números para um formato alternativo</span><span class="sxs-lookup"><span data-stu-id="cc3ce-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="cc3ce-113">Para obter informações sobre todas as etapas necessárias para configurar o Roteamento Direto, consulte [Configurar Roteamento Direto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="cc3ce-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="cc3ce-114">Visão geral do roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-114">Voice routing overview</span></span>

<span data-ttu-id="cc3ce-115">O Microsoft Phone System tem um mecanismo de roteamento que permite que uma chamada seja enviada para um SBC (Controlador de Borda de Sessão) específico com base em:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="cc3ce-116">O padrão de número chamado</span><span class="sxs-lookup"><span data-stu-id="cc3ce-116">The called number pattern</span></span> 
- <span data-ttu-id="cc3ce-117">O padrão de número chamado mais o usuário específico que faz a chamada</span><span class="sxs-lookup"><span data-stu-id="cc3ce-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="cc3ce-118">Os SBCs podem ser designados como ativos e de backup.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="cc3ce-119">Quando o SBC configurado como ativo não estiver disponível para uma rota de chamada específica, a chamada será roteada para um SBC de backup.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="cc3ce-120">O roteamento de voz é feito dos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="cc3ce-121">**Política de roteamento** de voz – um contêiner para usos de PSTN, que pode ser atribuído a um usuário ou a vários usuários.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="cc3ce-122">**Usos de PSTN** – um contêiner para rotas de voz e usos de PSTN, que podem ser compartilhados em diferentes políticas de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="cc3ce-123">**Rotas de** voz – um padrão de número e um conjunto de gateways PSTN online a ser usado para chamadas em que o número de chamadas corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="cc3ce-124">**Gateway PSTN** online – um ponteiro para um SBC que também armazena a configuração que é aplicada quando uma chamada é feita por meio do SBC, como pai (identidade P-asserted-identity) ou codecs preferenciais; podem ser adicionadas às rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="cc3ce-125">Considerações sobre a política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-125">Voice routing policy considerations</span></span>

<span data-ttu-id="cc3ce-126">Se um usuário tiver uma licença de Plano de Chamada, as chamadas de saída desse usuário serão roteada automaticamente pela infraestrutura PSTN do Plano de Chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="cc3ce-127">Se você configurar e atribuir uma política de roteamento de voz online a um usuário do Plano de Chamada, as chamadas de saída desse usuário serão verificadas para determinar se o número discado corresponde a um padrão de número definido na política de roteamento de voz online.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="cc3ce-128">Se houver uma combinação, a chamada será roteada pelo tronco de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="cc3ce-129">Se não houver nenhuma combinação, a chamada será roteada pela infraestrutura PSTN do Plano de Chamada.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="cc3ce-130">Se você configurar e aplicar a política de roteamento de voz online global (padrão de toda a organização), todos os usuários habilitados para voz em sua organização herdarão essa política, o que pode resultar em chamadas PSTN de usuários do Plano de Chamada sendo roteados inadvertidamente para um tronco de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="cc3ce-131">Se você não quiser que todos os usuários usem a política global de roteamento de voz online, configure uma política de roteamento de voz online personalizada e atribua-a a usuários individuais habilitados para voz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="cc3ce-132">Exemplo 1: Roteamento de voz com um uso PSTN</span><span class="sxs-lookup"><span data-stu-id="cc3ce-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="cc3ce-133">O diagrama a seguir mostra dois exemplos de políticas de roteamento de voz em um fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="cc3ce-134">**Fluxo de Chamada 1 (à esquerda):** Se um usuário fizer uma chamada para +1 425 XXX XX ou +1 206 XXX XX XX, a chamada será roteada para SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="cc3ce-135">Se nenhum sbc1.contoso.biz ou sbc2.contoso.biz estiver disponível, a chamada será retirada.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="cc3ce-136">**Fluxo de Chamada 2 (à direita):** Se um usuário fizer uma chamada para +1 425 XXX XX ou +1 206 XXX XX XX, a chamada será encaminhada primeiro para o SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="cc3ce-137">Se nenhum dos SBC estiver disponível, a rota com prioridade mais baixa será tentada (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="cc3ce-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="cc3ce-138">Se nenhum dos SBCs estiver disponível, a chamada será retirada.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Mostra exemplos de política de roteamento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="cc3ce-140">Em ambos os exemplos, embora a rota de voz seja atribuída a prioridades, os SBCs nas rotas são tentados em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span> <span data-ttu-id="cc3ce-141">Quando dois SBCs são configurados em uma rota, o tráfego de rede deve ser roteável entre SBC ou mídia não será estabelecido em transferências, pois é possível que o novo convite para a transferência seja enviado para um SBC diferente na rota.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-141">When two SBC's are configured in one route, network traffic must be routable between both SBC's or media will fail to be established on transfers as it is possible that the new invite for the transfer will be sent to a different SBC in the route.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cc3ce-142">A menos que o usuário também tenha uma licença do Plano de Chamada da Microsoft, as chamadas para qualquer número, exceto números que coincidem com os padrões +1 425 XXX XX XX ou +1 206 XXX XX XX na configuração de exemplo, serão descartados.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-142">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="cc3ce-143">Se o usuário tiver uma licença de Plano de Chamada, a chamada será roteada automaticamente de acordo com as políticas do Plano de Chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-143">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="cc3ce-144">O Plano de Chamada da Microsoft se aplica automaticamente como a última rota para todos os usuários com a licença do Plano de Chamada da Microsoft e não requer configuração adicional de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-144">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="cc3ce-145">No exemplo mostrado no diagrama a seguir, uma rota de voz é adicionada para enviar chamadas para todos os outros números dos EUA e do Canadá (chamadas que vão para o padrão de número +1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="cc3ce-145">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra a política de roteamento de voz com uma terceira rota](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="cc3ce-147">Para todas as outras chamadas, se um usuário tiver ambas as licenças (Microsoft Phone System e Plano de Chamada da Microsoft), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-147">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="cc3ce-148">Se nada corresponde aos padrões de número nas rotas de voz online criadas pelo administrador, a chamada é roteada pelo Plano de Chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-148">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="cc3ce-149">Se o usuário tiver apenas o Microsoft Phone System, a chamada será descartada porque nenhuma regra correspondente está disponível.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-149">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cc3ce-150">O valor de Prioridade para a rota "Outros +1" não importa nesse caso porque há apenas uma rota que corresponde ao padrão +1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-150">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="cc3ce-151">Se um usuário fizer uma chamada para +1 324 567 89 89 e o sbc5.contoso.biz e sbc6.contoso.biz não estiver disponível, a chamada será desalocar.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-151">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="cc3ce-152">A tabela a seguir resume a configuração usando três rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-152">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="cc3ce-153">Neste exemplo, todas as três rotas fazem parte do mesmo uso de PSTN, "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="cc3ce-153">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="cc3ce-154">Todas as rotas estão associadas ao uso de PSTN "EUA e Canadá" e o uso de PSTN está associado à política de roteamento de voz "Somente eua".</span><span class="sxs-lookup"><span data-stu-id="cc3ce-154">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="cc3ce-155">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-155">**PSTN usage**</span></span>|<span data-ttu-id="cc3ce-156">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-156">**Voice route**</span></span>|<span data-ttu-id="cc3ce-157">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-157">**Number pattern**</span></span>|<span data-ttu-id="cc3ce-158">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-158">**Priority**</span></span>|<span data-ttu-id="cc3ce-159">**Sbc**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-159">**SBC**</span></span>|<span data-ttu-id="cc3ce-160">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-160">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc3ce-161">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="cc3ce-161">US and Canada</span></span>|<span data-ttu-id="cc3ce-162">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-162">"Redmond 1"</span></span>|<span data-ttu-id="cc3ce-163">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="cc3ce-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cc3ce-164">1</span><span class="sxs-lookup"><span data-stu-id="cc3ce-164">1</span></span>|<span data-ttu-id="cc3ce-165">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-165">sbc1.contoso.biz</span></span><br/><span data-ttu-id="cc3ce-166">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-166">sbc2.contoso.biz</span></span>|<span data-ttu-id="cc3ce-167">Rota ativa para números chamados +1 425 XXX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cc3ce-167">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cc3ce-168">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="cc3ce-168">US and Canada</span></span>|<span data-ttu-id="cc3ce-169">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-169">"Redmond 2"</span></span>|<span data-ttu-id="cc3ce-170">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="cc3ce-170">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cc3ce-171">2</span><span class="sxs-lookup"><span data-stu-id="cc3ce-171">2</span></span>|<span data-ttu-id="cc3ce-172">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-172">sbc3.contoso.biz</span></span><br/><span data-ttu-id="cc3ce-173">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-173">sbc4.contoso.biz</span></span>|<span data-ttu-id="cc3ce-174">Rota de backup para os números +1 425 XXX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cc3ce-174">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cc3ce-175">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="cc3ce-175">US and Canada</span></span>|<span data-ttu-id="cc3ce-176">"Outros +1"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-176">"Other +1"</span></span>|<span data-ttu-id="cc3ce-177">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="cc3ce-177">^\\+1(\d{10})$</span></span>|<span data-ttu-id="cc3ce-178">3</span><span class="sxs-lookup"><span data-stu-id="cc3ce-178">3</span></span>|<span data-ttu-id="cc3ce-179">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-179">sbc5.contoso.biz</span></span><br/><span data-ttu-id="cc3ce-180">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-180">sbc6.contoso.biz</span></span>|<span data-ttu-id="cc3ce-181">Rota para números chamados +1 XXX XXX XX XX (exceto +1 425 XXX XX XX ou +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="cc3ce-181">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="cc3ce-182">Exemplo 1: Etapas de configuração</span><span class="sxs-lookup"><span data-stu-id="cc3ce-182">Example 1: Configuration steps</span></span>

<span data-ttu-id="cc3ce-183">O exemplo a seguir mostra como:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-183">The following example shows how to:</span></span>

1. <span data-ttu-id="cc3ce-184">Crie um único uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-184">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="cc3ce-185">Configure três rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-185">Configure three voice routes.</span></span>
3. <span data-ttu-id="cc3ce-186">Criar uma política de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-186">Create a voice routing policy.</span></span>
4. <span data-ttu-id="cc3ce-187">Atribua a política a um usuário chamado Duncan Low.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-187">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="cc3ce-188">Você pode usar o [Centro de administração do Microsoft Teams ou](#admincenterexample1) o [PowerShell](#powershellexample1) para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-188">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cc3ce-189">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc3ce-189">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="cc3ce-190">Etapa 1: Criar o uso de PSTN "EUA e Canadá"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-190">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="cc3ce-191">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Roteamento Direto de Voz e, no canto superior direito, selecione Gerenciar registros de uso  >   **de PSTN.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-191">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="cc3ce-192">Clique **em Adicionar,** digite **EUA e Canadá** e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-192">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="cc3ce-193">Etapa 2: criar três rotas de voz (Redmond 1, Redmond 2 e Other +1)</span><span class="sxs-lookup"><span data-stu-id="cc3ce-193">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="cc3ce-194">As etapas a seguir descrevem como criar uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-194">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="cc3ce-195">Use estas etapas para criar as três rotas de voz chamadas Redmond 1, Redmond 2 e Other +1 para este exemplo usando as configurações descritas na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-195">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="cc3ce-196">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Roteamento Direto de Voz e selecione a  >  guia **Rotas de** voz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="cc3ce-197">Clique **em** Adicionar e insira um nome e uma descrição para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-197">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="cc3ce-198">De definir a prioridade e especificar o padrão de número discado.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-198">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="cc3ce-199">Para registrar um SBC com a rota de voz, em **SBCs** inscritos (opcional), clique em Adicionar **SBCs,** selecione os SBCs que você deseja registrar e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-199">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="cc3ce-200">Para adicionar registros de uso PSTN, em registros de uso **PSTN (opcional),** clique em Adicionar uso **de PSTN,** selecione os registros PSTN que você deseja adicionar e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-200">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="cc3ce-201">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-201">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="cc3ce-202">Etapa 3: criar uma política de roteamento de voz chamada "Somente EUA" e adicionar o uso de PSTN "EUA e Canadá" à política</span><span class="sxs-lookup"><span data-stu-id="cc3ce-202">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="cc3ce-203">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas de roteamento do **Voice** Voice e  >  clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-203">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="cc3ce-204">Digite **US Somente** como o nome e adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-204">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="cc3ce-205">Em **registros de uso PSTN,** clique em Adicionar uso de **PSTN,** selecione o registro de uso PSTN "EUA e Canadá" e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-205">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="cc3ce-206">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-206">Click **Save**.</span></span>

<span data-ttu-id="cc3ce-207">Para saber mais, consulte [Gerenciar políticas de roteamento de voz.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cc3ce-207">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="cc3ce-208">Etapa 4: atribuir a política de roteamento de voz a um usuário chamado Low</span><span class="sxs-lookup"><span data-stu-id="cc3ce-208">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="cc3ce-209">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-209">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="cc3ce-210">Clique **em** Políticas e, ao lado de **Políticas Atribuídas,** clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-210">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="cc3ce-211">Em **Política de roteamento** de voz, selecione a política "Somente EUA" e clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-211">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="cc3ce-212">Para saber mais, consulte [Gerenciar políticas de roteamento de voz.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cc3ce-212">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cc3ce-213">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc3ce-213">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="cc3ce-214">Etapa 1: Criar o uso de PSTN "EUA e Canadá"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-214">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="cc3ce-215">Em uma sessão remota do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-215">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="cc3ce-216">Verifique se o uso foi criado inserindo:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-216">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="cc3ce-217">Que retorna uma lista de nomes que podem ser truncados:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-217">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="cc3ce-218">O exemplo a seguir mostra o resultado da execução do `(Get-CSOnlinePSTNUsage).usage` comando do Powershell para exibir nomes completos (não truncados):</span><span class="sxs-lookup"><span data-stu-id="cc3ce-218">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="cc3ce-219">Etapa 2: criar três rotas de voz (Redmond 1, Redmond 2 e Other +1)</span><span class="sxs-lookup"><span data-stu-id="cc3ce-219">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="cc3ce-220">Para criar a rota "Redmond 1", em uma sessão do PowerShell no Skype for Business Online, insira:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-220">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cc3ce-221">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-221">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="cc3ce-222">Para criar a rota Redmond 2, insira:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-222">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cc3ce-223">Para criar a rota Outros +1, insira:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-223">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="cc3ce-224">Certifique-se de que sua expressão regular no atributo NumberPattern seja uma expressão válida.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-224">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="cc3ce-225">Você pode testá-lo usando este site: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="cc3ce-225">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="cc3ce-226">Em alguns casos, é necessário encaminhar todas as chamadas para o mesmo SBC; use -NumberPattern ".\*"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-226">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="cc3ce-227">Rotee todas as chamadas para o mesmo SBC.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-227">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="cc3ce-228">Verifique se você configurou corretamente a rota executando o comando `Get-CSOnlineVoiceRoute` do PowerShell usando as opções conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-228">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="cc3ce-229">O que deve retornar:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-229">Which should return:</span></span>
<pre>
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
</pre>

<span data-ttu-id="cc3ce-230">No exemplo, a rota "Outros +1" foi atribuída automaticamente à prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-230">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="cc3ce-231">Etapa 3: criar uma política de roteamento de voz chamada "Somente EUA" e adicionar o uso de PSTN "EUA e Canadá" à política</span><span class="sxs-lookup"><span data-stu-id="cc3ce-231">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="cc3ce-232">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-232">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cc3ce-233">O resultado é mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-233">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="cc3ce-234">Etapa 4: atribuir a política de roteamento de voz a um usuário chamado Low</span><span class="sxs-lookup"><span data-stu-id="cc3ce-234">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="cc3ce-235">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-235">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="cc3ce-236">Valide a atribuição de política inserindo este comando:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-236">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="cc3ce-237">O comando retorna o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-237">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="cc3ce-238">Exemplo 2: Roteamento de voz com vários usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="cc3ce-238">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="cc3ce-239">A política de roteamento de voz criada no Exemplo 1 só permite chamadas para números de telefone nos EUA e no Canadá, a menos que a licença do Plano de Chamada da Microsoft também seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-239">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="cc3ce-240">No exemplo a seguir, você pode criar a política de roteamento de voz "Sem Restrições".</span><span class="sxs-lookup"><span data-stu-id="cc3ce-240">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="cc3ce-241">A política reutiliza o uso de PSTN "EUA e Canadá" criado no Exemplo 1, bem como o novo uso de PSTN "Internacional".</span><span class="sxs-lookup"><span data-stu-id="cc3ce-241">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="cc3ce-242">Esta política encaminha todas as outras chamadas para os SBCs sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-242">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="cc3ce-243">Os exemplos que são mostrados atribuem a política somente para os EUA ao usuário Low, e a política Sem Restrições para o usuário John Woods para que o roteamento ocorra da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-243">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="cc3ce-244">Low Low – Política somente para os EUA.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-244">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="cc3ce-245">As chamadas só são permitidas para números dos EUA e do Canadá.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-245">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="cc3ce-246">Ao ligar para o intervalo de números Redmond, o conjunto específico de SBCs deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-246">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="cc3ce-247">Os números que não são dos EUA não serão roteados, a menos que a licença do Plano de Chamada seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-247">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="cc3ce-248">John Woods – Política internacional.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-248">John Woods – International policy.</span></span>  <span data-ttu-id="cc3ce-249">As chamadas são permitidas para qualquer número.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-249">Calls are allowed to any number.</span></span> <span data-ttu-id="cc3ce-250">Ao ligar para o intervalo de números Redmond, o conjunto específico de SBCs deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-250">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="cc3ce-251">Os números que não são dos EUA serão roteados usando sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-251">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário– Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="cc3ce-253">Para todas as outras chamadas, se um usuário tiver ambas as licenças (Microsoft Phone System e Plano de Chamada da Microsoft), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-253">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="cc3ce-254">Se nada corresponde aos padrões de número nas rotas de voz online criadas pelo administrador, a chamada é roteada usando o Plano de Chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-254">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="cc3ce-255">Se o usuário tiver apenas o Microsoft Phone System, a chamada será descartada porque nenhuma regra correspondente está disponível.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-255">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="cc3ce-257">A tabela a seguir resume as designações de uso e as rotas de voz da política de roteamento "Sem Restrições".</span><span class="sxs-lookup"><span data-stu-id="cc3ce-257">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="cc3ce-258">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-258">**PSTN usage**</span></span>|<span data-ttu-id="cc3ce-259">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-259">**Voice route**</span></span>|<span data-ttu-id="cc3ce-260">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-260">**Number pattern**</span></span>|<span data-ttu-id="cc3ce-261">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-261">**Priority**</span></span>|<span data-ttu-id="cc3ce-262">**Sbc**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-262">**SBC**</span></span>|<span data-ttu-id="cc3ce-263">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-263">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc3ce-264">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="cc3ce-264">US and Canada</span></span>|<span data-ttu-id="cc3ce-265">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-265">"Redmond 1"</span></span>|<span data-ttu-id="cc3ce-266">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="cc3ce-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cc3ce-267">1</span><span class="sxs-lookup"><span data-stu-id="cc3ce-267">1</span></span>|<span data-ttu-id="cc3ce-268">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-268">sbc1.contoso.biz</span></span><br/><span data-ttu-id="cc3ce-269">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-269">sbc2.contoso.biz</span></span>|<span data-ttu-id="cc3ce-270">Rota ativa para números de destinatário +1 425 XXX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cc3ce-270">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cc3ce-271">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="cc3ce-271">US and Canada</span></span>|<span data-ttu-id="cc3ce-272">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-272">"Redmond 2"</span></span>|<span data-ttu-id="cc3ce-273">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="cc3ce-273">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cc3ce-274">2</span><span class="sxs-lookup"><span data-stu-id="cc3ce-274">2</span></span>|<span data-ttu-id="cc3ce-275">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-275">sbc3.contoso.biz</span></span><br/><span data-ttu-id="cc3ce-276">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-276">sbc4.contoso.biz</span></span>|<span data-ttu-id="cc3ce-277">Rota de backup para números de destinatário +1 425 XXX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cc3ce-277">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cc3ce-278">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="cc3ce-278">US and Canada</span></span>|<span data-ttu-id="cc3ce-279">"Outros +1"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-279">"Other +1"</span></span>|<span data-ttu-id="cc3ce-280">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="cc3ce-280">^\\+1(\d{10})$</span></span>|<span data-ttu-id="cc3ce-281">3</span><span class="sxs-lookup"><span data-stu-id="cc3ce-281">3</span></span>|<span data-ttu-id="cc3ce-282">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-282">sbc5.contoso.biz</span></span><br/><span data-ttu-id="cc3ce-283">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-283">sbc6.contoso.biz</span></span>|<span data-ttu-id="cc3ce-284">Rota para números de destinatário +1 XXX XXX XX XX (exceto +1 425 XXX XX XX ou +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="cc3ce-284">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="cc3ce-285">International</span><span class="sxs-lookup"><span data-stu-id="cc3ce-285">International</span></span>|<span data-ttu-id="cc3ce-286">International</span><span class="sxs-lookup"><span data-stu-id="cc3ce-286">International</span></span>|<span data-ttu-id="cc3ce-287">\d+</span><span class="sxs-lookup"><span data-stu-id="cc3ce-287">\d+</span></span>|<span data-ttu-id="cc3ce-288">4</span><span class="sxs-lookup"><span data-stu-id="cc3ce-288">4</span></span>|<span data-ttu-id="cc3ce-289">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-289">sbc2.contoso.biz</span></span><br/><span data-ttu-id="cc3ce-290">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cc3ce-290">sbc5.contoso.biz</span></span>|<span data-ttu-id="cc3ce-291">Rote para qualquer padrão de número</span><span class="sxs-lookup"><span data-stu-id="cc3ce-291">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="cc3ce-292">A ordem dos usos de PSTN nas políticas de roteamento de voz é fundamental.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-292">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="cc3ce-293">Os usos são aplicados na ordem e, se uma combinação for encontrada no primeiro uso, outros usos nunca serão avaliados.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-293">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="cc3ce-294">O uso de PSTN "Internacional" deve ser colocado após o uso de PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="cc3ce-294">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="cc3ce-295">Para alterar a ordem dos usos de PSTN, execute o `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-295">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="cc3ce-296">Por exemplo, para alterar a ordem "EUA e Canadá" primeiro e "Internacional" segundo para a ordem inversa, execute:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-296">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="cc3ce-297">A prioridade para rotas de voz "Outros +1" e "Internacionais" são atribuídas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-297">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="cc3ce-298">Eles não importam, desde que tenham prioridades menores do que "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="cc3ce-298">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="cc3ce-299">Exemplo 2: Etapas de configuração</span><span class="sxs-lookup"><span data-stu-id="cc3ce-299">Example 2: Configuration steps</span></span>

<span data-ttu-id="cc3ce-300">O exemplo a seguir mostra como:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-300">The following example shows how to:</span></span>

1. <span data-ttu-id="cc3ce-301">Crie um novo uso de PSTN chamado Internacional.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-301">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="cc3ce-302">Crie uma nova rota de voz chamada Internacional.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-302">Create a new voice route called International.</span></span>
3. <span data-ttu-id="cc3ce-303">Crie uma política de roteamento de voz chamada Sem Restrições.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-303">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="cc3ce-304">Atribua a política ao usuário John Woods.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-304">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="cc3ce-305">Você pode usar o [Centro de administração do Microsoft Teams ou](#admincenterexample2) o [PowerShell](#powershellexample2) para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-305">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cc3ce-306">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc3ce-306">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="cc3ce-307">Etapa 1: Criar o uso de PSTN "Internacional"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-307">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="cc3ce-308">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Roteamento Direto de Voz e, no canto superior direito, selecione Gerenciar registros de uso  >   **de PSTN.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-308">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="cc3ce-309">Clique **em Adicionar,** digite **Internacional** e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-309">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="cc3ce-310">Etapa 2: Criar a rota de voz "Internacional"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-310">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="cc3ce-311">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Roteamento Direto de Voz e selecione a  >  guia **Rotas de** voz.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-311">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="cc3ce-312">Clique **em** Adicionar, insira "Internacional" como o nome e adicione a descrição.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-312">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="cc3ce-313">De definir a prioridade como 4 e, em seguida, definir o padrão de número discado como \d+.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-313">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="cc3ce-314">Em **SBCs inscritos (opcional),** clique em Adicionar **SBCs,** selecione sbc2.contoso.biz e sbc5.contoso.biz e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-314">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="cc3ce-315">Em **registros de uso PSTN (opcional),** clique em Adicionar uso de **PSTN,** selecione o registro de uso PSTN "Internacional" e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-315">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="cc3ce-316">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-316">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="cc3ce-317">Etapa 3: criar uma política de roteamento de voz chamada "Sem Restrições" e adicionar os usos de PSTN "EUA e Canadá" e "Internacional" à política</span><span class="sxs-lookup"><span data-stu-id="cc3ce-317">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="cc3ce-318">O uso de PSTN "EUA e Canadá" é reutilizado nesta política de roteamento de voz para preservar o tratamento especial para chamadas para os números "+1 425 XXX XX XX" e "+1 206 XXX XX XX" como chamadas locais ou locais.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-318">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="cc3ce-319">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas de roteamento do **Voice** Voice e  >  clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-319">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="cc3ce-320">Digite **Sem Restrições** como o nome e adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-320">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="cc3ce-321">Em registros de uso **PSTN,** clique em Adicionar uso **de PSTN,** selecione o registro de uso PSTN "EUA e Canadá" e selecione o registro de uso PSTN "Internacional".</span><span class="sxs-lookup"><span data-stu-id="cc3ce-321">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="cc3ce-322">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-322">Click **Apply**.</span></span>

    <span data-ttu-id="cc3ce-323">Anote a ordem dos usos de PSTN:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-323">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="cc3ce-324">Se uma chamada feita para o número "+1 425 XXX XX XX" com os usos configurados como neste exemplo, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial será aplicada.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-324">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="cc3ce-325">Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como rotas de backup.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-325">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="cc3ce-326">Se o uso de PSTN "Internacional" for antes de "EUA e Canadá", as chamadas para +1 425 XXX XX XX serão roteados para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-326">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="cc3ce-327">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-327">Click **Save**.</span></span>

<span data-ttu-id="cc3ce-328">Para saber mais, consulte [Gerenciar políticas de roteamento de voz.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cc3ce-328">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="cc3ce-329">Etapa 4: atribuir a política de roteamento de voz a um usuário chamado John Woods</span><span class="sxs-lookup"><span data-stu-id="cc3ce-329">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="cc3ce-330">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-330">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="cc3ce-331">Clique **em** Políticas e, ao lado de **Políticas Atribuídas,** clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-331">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="cc3ce-332">Em **Política de roteamento** de voz, selecione a política "Sem Restrições" e clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="cc3ce-332">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="cc3ce-333">O resultado é que a política de voz aplicada às chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponível para as chamadas dos EUA, Canadá e Internacional.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-333">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cc3ce-334">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc3ce-334">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="cc3ce-335">Etapa 1: Criar o uso de PSTN "Internacional"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-335">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="cc3ce-336">Em uma sessão remota do PowerShell no Skype for Business Online, insira:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-336">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="cc3ce-337">Etapa 2: criar uma nova rota de voz chamada "Internacional"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-337">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="cc3ce-338">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-338">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="cc3ce-339">Etapa 3: criar uma política de roteamento de voz chamada "Sem Restrições"</span><span class="sxs-lookup"><span data-stu-id="cc3ce-339">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="cc3ce-340">O uso PSTN "Redmond 1" e "Redmond" são reutilizados nesta política de roteamento de voz para preservar o tratamento especial para chamadas para os números "+1 425 XXX XX XX" e "+1 206 XXX XX" como chamadas locais ou locais.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-340">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="cc3ce-341">Anote a ordem dos usos de PSTN:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-341">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="cc3ce-342">Se uma chamada feita para o número "+1 425 XXX XX XX" com os usos configurados como no exemplo a seguir, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial será aplicada.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-342">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="cc3ce-343">Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como rotas de backup.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-343">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="cc3ce-344">Se o uso de PSTN "Internacional" for antes de "EUA e Canadá", as chamadas para +1 425 XXX XX XX serão roteados para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-344">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="cc3ce-345">Insira o comando:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-345">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="cc3ce-346">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-346">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="cc3ce-347">Etapa 4: atribuir a política de roteamento de voz ao usuário chamado John Woods</span><span class="sxs-lookup"><span data-stu-id="cc3ce-347">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="cc3ce-348">Em seguida, verifique a tarefa usando o comando:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-348">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="cc3ce-349">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="cc3ce-349">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="cc3ce-350">O resultado é que a política de voz aplicada às chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponível para as chamadas dos EUA, Canadá e Internacional.</span><span class="sxs-lookup"><span data-stu-id="cc3ce-350">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc3ce-351">Confira também</span><span class="sxs-lookup"><span data-stu-id="cc3ce-351">See also</span></span>

[<span data-ttu-id="cc3ce-352">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="cc3ce-352">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="cc3ce-353">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="cc3ce-353">Configure Direct Routing</span></span>](direct-routing-configure.md)
