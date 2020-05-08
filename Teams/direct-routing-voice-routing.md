---
title: Configurar o roteamento de voz para roteamento direto
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
description: Saiba como configurar o roteamento de voz com o roteamento direto do sistema de telefonia da Microsoft.
ms.openlocfilehash: 0611684c79d92572ade41f2545096fe1d9bb4dd2
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159008"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="efbe1-103">Configurar o roteamento de voz para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="efbe1-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="efbe1-104">Este artigo descreve como configurar o roteamento de voz para o roteamento direto do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="efbe1-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="efbe1-105">Esta é a etapa 3 das seguintes etapas para configurar o roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="efbe1-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="efbe1-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="efbe1-106">Step 1.</span></span> [<span data-ttu-id="efbe1-107">Conectar o SBC com o sistema Microsoft Phone e validar a conexão</span><span class="sxs-lookup"><span data-stu-id="efbe1-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="efbe1-108">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="efbe1-108">Step 2.</span></span> [<span data-ttu-id="efbe1-109">Habilite os usuários para roteamento direto, voz e correio de voz</span><span class="sxs-lookup"><span data-stu-id="efbe1-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="efbe1-110">**Etapa 3. Configurar roteamento de voz** (este artigo)</span><span class="sxs-lookup"><span data-stu-id="efbe1-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="efbe1-111">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="efbe1-111">Step 4.</span></span> [<span data-ttu-id="efbe1-112">Converter números em um formato alternativo</span><span class="sxs-lookup"><span data-stu-id="efbe1-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="efbe1-113">Para obter informações sobre todas as etapas necessárias para configurar o roteamento direto, consulte [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="efbe1-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="efbe1-114">Visão geral do roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="efbe1-114">Voice routing overview</span></span>

<span data-ttu-id="efbe1-115">O sistema telefônico da Microsoft tem um mecanismo de roteamento que permite que uma chamada seja enviada para um controlador de borda de sessão (SBC) específico com base em:</span><span class="sxs-lookup"><span data-stu-id="efbe1-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="efbe1-116">O padrão de número chamado</span><span class="sxs-lookup"><span data-stu-id="efbe1-116">The called number pattern</span></span> 
- <span data-ttu-id="efbe1-117">O padrão de número chamado mais o usuário específico que faz a chamada</span><span class="sxs-lookup"><span data-stu-id="efbe1-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="efbe1-118">A SBCs pode ser designada como ativa e de backup.</span><span class="sxs-lookup"><span data-stu-id="efbe1-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="efbe1-119">Quando o SBC que está configurado como ativo não está disponível para uma rota de chamada específica, a chamada será roteada para um SBC de backup.</span><span class="sxs-lookup"><span data-stu-id="efbe1-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="efbe1-120">O roteamento de voz é composto pelos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="efbe1-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="efbe1-121">**Política de roteamento de voz** – um contêiner para usos de PSTN que podem ser atribuídos a um usuário ou a vários usuários.</span><span class="sxs-lookup"><span data-stu-id="efbe1-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="efbe1-122">**Usos de PSTN** – um contêiner para rotas de voz e usos de PSTN, que podem ser compartilhados em diferentes políticas de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="efbe1-123">**Rotas de voz** – um padrão de número e um conjunto de gateways PSTN online a serem usados para chamadas onde o número de chamada corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="efbe1-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="efbe1-124">**Gateway PSTN online** -um ponteiro para um SBC que também armazena a configuração aplicada quando uma chamada é feita por meio do SBC, como encaminhamento P-declarada-identidade (pai) ou codecs preferenciais; pode ser adicionado a roteiros de voz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="efbe1-125">Exemplo 1: roteamento de voz com um uso PSTN</span><span class="sxs-lookup"><span data-stu-id="efbe1-125">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="efbe1-126">O diagrama a seguir mostra dois exemplos de políticas de roteamento de voz em um fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="efbe1-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="efbe1-127">**Fluxo de chamadas 1 (à esquerda):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada para o SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="efbe1-128">Se nem sbc1.contoso.biz nem sbc2.contoso.biz estiverem disponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="efbe1-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="efbe1-129">**Fluxo de chamadas 2 (à direita):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada primeiro para o SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="efbe1-130">Se nenhum SBC estiver disponível, a rota com prioridade menor será tentada (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="efbe1-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="efbe1-131">Se nenhum dos SBCs estiver disponível, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="efbe1-131">If none of the SBCs are available, the call is dropped.</span></span> 

![Mostra exemplos de política de roteamento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="efbe1-133">Nos dois exemplos, enquanto a rota de voz é atribuída às prioridades, o SBCs nos roteiros é tentado em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="efbe1-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="efbe1-134">A menos que o usuário também tenha uma licença do plano de chamadas da Microsoft, as chamadas para qualquer número, exceto números que correspondam aos padrões + 1 425 XXX XX XX ou + 1 206 XXX XX XX no exemplo de configuração são descartados.</span><span class="sxs-lookup"><span data-stu-id="efbe1-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="efbe1-135">Se o usuário tiver uma licença de plano de chamada, a chamada será roteada automaticamente de acordo com as políticas do plano de chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efbe1-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="efbe1-136">O plano de chamadas da Microsoft aplica-se automaticamente como a última rota para todos os usuários com a licença do plano de chamadas da Microsoft e não requer configuração de roteamento de chamadas adicional.</span><span class="sxs-lookup"><span data-stu-id="efbe1-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="efbe1-137">No exemplo mostrado no diagrama a seguir, uma rota de voz é adicionada para enviar chamadas para todos os outros números canadenses e EUA (chamadas que vão para o padrão de número chamado + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="efbe1-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra a política de roteamento de voz com uma terceira rota](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="efbe1-139">Para todas as outras chamadas:</span><span class="sxs-lookup"><span data-stu-id="efbe1-139">For all other calls:</span></span>

- <span data-ttu-id="efbe1-140">Se um usuário tiver licenças (sistema telefônico da Microsoft e Microsoft Calling plano), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="efbe1-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="efbe1-141">Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, a chamada será roteada pelo plano de chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efbe1-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="efbe1-142">Se o usuário tiver apenas o Microsoft Phone System, a chamada será descartada porque nenhuma regra de correspondência estará disponível.</span><span class="sxs-lookup"><span data-stu-id="efbe1-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="efbe1-143">O valor de prioridade para a rota "Other + 1" não importa nesse caso porque há apenas uma rota que corresponde ao padrão + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="efbe1-143">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="efbe1-144">Se um usuário fizer uma chamada para + 1 324 567 89 89 e sbc5.contoso.biz e sbc6.contoso.biz estiverem indisponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="efbe1-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="efbe1-145">A tabela a seguir resume a configuração usando três rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="efbe1-146">Neste exemplo, todas as três rotas fazem parte do mesmo uso de PSTN, "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="efbe1-146">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="efbe1-147">Todas as rotas são associadas ao uso da PSTN "EUA e Canadá" e o uso da PSTN está associado à política de roteamento de voz "apenas EUA".</span><span class="sxs-lookup"><span data-stu-id="efbe1-147">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="efbe1-148">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="efbe1-148">**PSTN usage**</span></span>|<span data-ttu-id="efbe1-149">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="efbe1-149">**Voice route**</span></span>|<span data-ttu-id="efbe1-150">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="efbe1-150">**Number pattern**</span></span>|<span data-ttu-id="efbe1-151">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="efbe1-151">**Priority**</span></span>|<span data-ttu-id="efbe1-152">**SBC**</span><span class="sxs-lookup"><span data-stu-id="efbe1-152">**SBC**</span></span>|<span data-ttu-id="efbe1-153">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="efbe1-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="efbe1-154">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="efbe1-154">US and Canada</span></span>|<span data-ttu-id="efbe1-155">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="efbe1-155">"Redmond 1"</span></span>|<span data-ttu-id="efbe1-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="efbe1-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="efbe1-157">1</span><span class="sxs-lookup"><span data-stu-id="efbe1-157">1</span></span>|<span data-ttu-id="efbe1-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="efbe1-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="efbe1-160">Roteiro ativo para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="efbe1-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="efbe1-161">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="efbe1-161">US and Canada</span></span>|<span data-ttu-id="efbe1-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="efbe1-162">"Redmond 2"</span></span>|<span data-ttu-id="efbe1-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="efbe1-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="efbe1-164">2</span><span class="sxs-lookup"><span data-stu-id="efbe1-164">2</span></span>|<span data-ttu-id="efbe1-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="efbe1-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="efbe1-167">Rota de backup para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="efbe1-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="efbe1-168">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="efbe1-168">US and Canada</span></span>|<span data-ttu-id="efbe1-169">"Outro + 1"</span><span class="sxs-lookup"><span data-stu-id="efbe1-169">"Other +1"</span></span>|<span data-ttu-id="efbe1-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="efbe1-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="efbe1-171">3</span><span class="sxs-lookup"><span data-stu-id="efbe1-171">3</span></span>|<span data-ttu-id="efbe1-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="efbe1-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="efbe1-174">Rota para números chamados + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="efbe1-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="efbe1-175">Exemplo 1: etapas de configuração</span><span class="sxs-lookup"><span data-stu-id="efbe1-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="efbe1-176">O exemplo a seguir mostra como:</span><span class="sxs-lookup"><span data-stu-id="efbe1-176">The following example shows how to:</span></span>

1. <span data-ttu-id="efbe1-177">Crie um único uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="efbe1-177">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="efbe1-178">Configurar três rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-178">Configure three voice routes.</span></span>
3. <span data-ttu-id="efbe1-179">Criar uma política de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-179">Create a voice routing policy.</span></span>
4. <span data-ttu-id="efbe1-180">Atribua a política a um usuário chamado Spencer baixo.</span><span class="sxs-lookup"><span data-stu-id="efbe1-180">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="efbe1-181">Você pode usar o [centro de administração do Microsoft Teams](#admincenterexample1) ou o [PowerShell](#powershellexample1) para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="efbe1-181">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="efbe1-182">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efbe1-182">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="efbe1-183">Etapa 1: criar o uso da PSTN "EUA e Canadá"</span><span class="sxs-lookup"><span data-stu-id="efbe1-183">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="efbe1-184">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**Roteamento direto**de **voz** > e, em seguida, no canto superior direito, selecione **gerenciar registros de uso PSTN**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-184">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="efbe1-185">Clique em **Adicionar**, digite **EUA e Canadá**e, em seguida, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-185">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="efbe1-186">Etapa 2: criar três rotas de voz (Redmond, 1, Redmond 2 e outros + 1)</span><span class="sxs-lookup"><span data-stu-id="efbe1-186">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="efbe1-187">As etapas a seguir descrevem como criar uma rota de voz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-187">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="efbe1-188">Use estas etapas para criar as três rotas de voz chamadas Redmond 1, Redmond 2 e outros + 1 para este exemplo usando as configurações descritas na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="efbe1-188">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="efbe1-189">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**Roteamento direto**de **voz** > e selecione a guia **rotas de voz** .</span><span class="sxs-lookup"><span data-stu-id="efbe1-189">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="efbe1-190">Clique em **Adicionar**e, em seguida, insira um nome e uma descrição para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-190">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="efbe1-191">Defina a prioridade e especifique o padrão de número discado.</span><span class="sxs-lookup"><span data-stu-id="efbe1-191">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="efbe1-192">Para registrar um SBC com a rota de voz, em **SBCS registrado (opcional)**, clique em **Adicionar SBCS**, selecione o SBCS que você deseja registrar e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-192">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="efbe1-193">Para adicionar registros de uso de PSTN, em **registros de uso PSTN (opcional)**, clique em **Adicionar uso de PSTN**, selecione os registros PSTN que você deseja adicionar e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-193">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="efbe1-194">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-194">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="efbe1-195">Etapa 3: criar uma política de roteamento de voz chamada "apenas EUA" e adicionar o uso da PSTN "EUA e Canadá" à política</span><span class="sxs-lookup"><span data-stu-id="efbe1-195">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="efbe1-196">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de roteamento de voz**de **voz** > e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="efbe1-197">Digite **-nos apenas** como o nome e adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="efbe1-197">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="efbe1-198">Em **registros de uso de PSTN**, clique em **Adicionar uso de PSTN**, selecione o registro de uso PSTN "EUA e Canadá" e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-198">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="efbe1-199">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-199">Click **Save**.</span></span>

<span data-ttu-id="efbe1-200">Para saber mais, consulte [gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="efbe1-200">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="efbe1-201">Etapa 4: atribuir a política de roteamento de voz a um usuário chamado Spencer-baixo</span><span class="sxs-lookup"><span data-stu-id="efbe1-201">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="efbe1-202">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="efbe1-202">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="efbe1-203">Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-203">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="efbe1-204">Em **política de roteamento de voz**, selecione a política "somente EUA" e, em seguida, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-204">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="efbe1-205">Para saber mais, consulte [gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="efbe1-205">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="efbe1-206">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="efbe1-206">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="efbe1-207">Etapa 1: criar o uso da PSTN "EUA e Canadá"</span><span class="sxs-lookup"><span data-stu-id="efbe1-207">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="efbe1-208">Em uma sessão remota do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="efbe1-208">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="efbe1-209">Verifique se o uso foi criado inserindo:</span><span class="sxs-lookup"><span data-stu-id="efbe1-209">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="efbe1-210">Que retorna uma lista de nomes que podem estar truncados:</span><span class="sxs-lookup"><span data-stu-id="efbe1-210">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="efbe1-211">O exemplo a seguir mostra o resultado da execução `(Get-CSOnlinePSTNUsage).usage` do comando do PowerShell para exibir nomes completos (não truncados):</span><span class="sxs-lookup"><span data-stu-id="efbe1-211">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="efbe1-212">Etapa 2: criar três rotas de voz (Redmond, 1, Redmond 2 e outros + 1)</span><span class="sxs-lookup"><span data-stu-id="efbe1-212">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="efbe1-213">Para criar a rota "Redmond 1", em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="efbe1-213">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="efbe1-214">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="efbe1-214">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="efbe1-215">Para criar a rota Redmond 2, digite:</span><span class="sxs-lookup"><span data-stu-id="efbe1-215">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="efbe1-216">Para criar a outra rota + 1, digite:</span><span class="sxs-lookup"><span data-stu-id="efbe1-216">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="efbe1-217">Certifique-se de que sua expressão regular no atributo NumberPattern é uma expressão válida.</span><span class="sxs-lookup"><span data-stu-id="efbe1-217">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="efbe1-218">Você pode testá-lo usando este site:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="efbe1-218">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="efbe1-219">Em alguns casos, há a necessidade de rotear todas as chamadas para o mesmo SBC; Use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="efbe1-219">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="efbe1-220">Rotear todas as chamadas para o mesmo SBC.</span><span class="sxs-lookup"><span data-stu-id="efbe1-220">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="efbe1-221">Verifique se você configurou corretamente a rota executando o comando `Get-CSOnlineVoiceRoute` do PowerShell usando as opções conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="efbe1-221">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="efbe1-222">Que deve retornar:</span><span class="sxs-lookup"><span data-stu-id="efbe1-222">Which should return:</span></span>
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

<span data-ttu-id="efbe1-223">No exemplo, a rota "Other + 1" foi automaticamente atribuída à prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="efbe1-223">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="efbe1-224">Etapa 3: criar uma política de roteamento de voz chamada "apenas EUA" e adicionar o uso da PSTN "EUA e Canadá" à política</span><span class="sxs-lookup"><span data-stu-id="efbe1-224">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="efbe1-225">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="efbe1-225">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="efbe1-226">O resultado é mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="efbe1-226">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="efbe1-227">Etapa 4: atribuir a política de roteamento de voz a um usuário chamado Spencer-baixo</span><span class="sxs-lookup"><span data-stu-id="efbe1-227">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="efbe1-228">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="efbe1-228">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="efbe1-229">Valide a atribuição de política inserindo este comando:</span><span class="sxs-lookup"><span data-stu-id="efbe1-229">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="efbe1-230">O comando retorna o seguinte:</span><span class="sxs-lookup"><span data-stu-id="efbe1-230">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="efbe1-231">Exemplo 2: roteamento de voz com vários usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="efbe1-231">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="efbe1-232">A política de roteamento de voz criada no exemplo 1 só permite chamadas para números de telefone nos EUA e no Canadá, a menos que a licença do plano de chamadas da Microsoft também seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="efbe1-232">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="efbe1-233">No exemplo a seguir, você pode criar a política de roteamento de voz "sem restrições".</span><span class="sxs-lookup"><span data-stu-id="efbe1-233">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="efbe1-234">A política reutiliza o uso PSTN "dos EUA e Canadá" criado no exemplo 1, bem como o novo uso de PSTN "internacional".</span><span class="sxs-lookup"><span data-stu-id="efbe1-234">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="efbe1-235">Esta política roteia todas as outras chamadas para o SBCs sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-235">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="efbe1-236">Os exemplos mostrados atribuem a política apenas EUA para o usuário Spencer baixo e a política sem restrições ao usuário John Woods para que o roteamento ocorra da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="efbe1-236">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="efbe1-237">Spencer baixo – política apenas para os EUA.</span><span class="sxs-lookup"><span data-stu-id="efbe1-237">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="efbe1-238">As chamadas são permitidas apenas para números canadenses e Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="efbe1-238">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="efbe1-239">Ao ligar para o intervalo de números Redmond, o conjunto específico de SBCs deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="efbe1-239">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="efbe1-240">Os números que não são dos EUA não serão roteados, a menos que a licença do plano de chamada seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="efbe1-240">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="efbe1-241">John Woods – política internacional.</span><span class="sxs-lookup"><span data-stu-id="efbe1-241">John Woods – International policy.</span></span>  <span data-ttu-id="efbe1-242">As chamadas são permitidas para qualquer número.</span><span class="sxs-lookup"><span data-stu-id="efbe1-242">Calls are allowed to any number.</span></span> <span data-ttu-id="efbe1-243">Ao ligar para o intervalo de números Redmond, o conjunto específico de SBCs deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="efbe1-243">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="efbe1-244">Os números que não são dos EUA serão encaminhados usando sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-244">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário Spencer baixo](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="efbe1-246">Para todas as outras chamadas, se um usuário tiver licenças (sistema telefônico da Microsoft e plano de chamadas da Microsoft), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="efbe1-246">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="efbe1-247">Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, a chamada será roteada usando o plano de chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efbe1-247">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="efbe1-248">Se o usuário tiver apenas um sistema telefônico da Microsoft, a chamada será descartada porque nenhuma regra de correspondência estará disponível.</span><span class="sxs-lookup"><span data-stu-id="efbe1-248">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="efbe1-250">A tabela a seguir resume as designações de uso de política de roteamento "sem restrições" e rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="efbe1-250">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="efbe1-251">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="efbe1-251">**PSTN usage**</span></span>|<span data-ttu-id="efbe1-252">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="efbe1-252">**Voice route**</span></span>|<span data-ttu-id="efbe1-253">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="efbe1-253">**Number pattern**</span></span>|<span data-ttu-id="efbe1-254">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="efbe1-254">**Priority**</span></span>|<span data-ttu-id="efbe1-255">**SBC**</span><span class="sxs-lookup"><span data-stu-id="efbe1-255">**SBC**</span></span>|<span data-ttu-id="efbe1-256">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="efbe1-256">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="efbe1-257">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="efbe1-257">US and Canada</span></span>|<span data-ttu-id="efbe1-258">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="efbe1-258">"Redmond 1"</span></span>|<span data-ttu-id="efbe1-259">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="efbe1-259">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="efbe1-260">1</span><span class="sxs-lookup"><span data-stu-id="efbe1-260">1</span></span>|<span data-ttu-id="efbe1-261">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-261">sbc1.contoso.biz</span></span><br/><span data-ttu-id="efbe1-262">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-262">sbc2.contoso.biz</span></span>|<span data-ttu-id="efbe1-263">Roteiro ativo para números de chamada + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="efbe1-263">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="efbe1-264">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="efbe1-264">US and Canada</span></span>|<span data-ttu-id="efbe1-265">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="efbe1-265">"Redmond 2"</span></span>|<span data-ttu-id="efbe1-266">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="efbe1-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="efbe1-267">2</span><span class="sxs-lookup"><span data-stu-id="efbe1-267">2</span></span>|<span data-ttu-id="efbe1-268">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-268">sbc3.contoso.biz</span></span><br/><span data-ttu-id="efbe1-269">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-269">sbc4.contoso.biz</span></span>|<span data-ttu-id="efbe1-270">Rota de backup para números do chamado + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="efbe1-270">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="efbe1-271">EUA e Canadá</span><span class="sxs-lookup"><span data-stu-id="efbe1-271">US and Canada</span></span>|<span data-ttu-id="efbe1-272">"Outro + 1"</span><span class="sxs-lookup"><span data-stu-id="efbe1-272">"Other +1"</span></span>|<span data-ttu-id="efbe1-273">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="efbe1-273">^\\+1(\d{10})$</span></span>|<span data-ttu-id="efbe1-274">3</span><span class="sxs-lookup"><span data-stu-id="efbe1-274">3</span></span>|<span data-ttu-id="efbe1-275">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-275">sbc5.contoso.biz</span></span><br/><span data-ttu-id="efbe1-276">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-276">sbc6.contoso.biz</span></span>|<span data-ttu-id="efbe1-277">Rota para números de chamada + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="efbe1-277">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="efbe1-278">International</span><span class="sxs-lookup"><span data-stu-id="efbe1-278">International</span></span>|<span data-ttu-id="efbe1-279">International</span><span class="sxs-lookup"><span data-stu-id="efbe1-279">International</span></span>|<span data-ttu-id="efbe1-280">\d +</span><span class="sxs-lookup"><span data-stu-id="efbe1-280">\d+</span></span>|<span data-ttu-id="efbe1-281">4</span><span class="sxs-lookup"><span data-stu-id="efbe1-281">4</span></span>|<span data-ttu-id="efbe1-282">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-282">sbc2.contoso.biz</span></span><br/><span data-ttu-id="efbe1-283">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="efbe1-283">sbc5.contoso.biz</span></span>|<span data-ttu-id="efbe1-284">Rota para qualquer padrão de número</span><span class="sxs-lookup"><span data-stu-id="efbe1-284">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="efbe1-285">A ordem dos usos de PSTN nas políticas de roteamento de voz é crítica.</span><span class="sxs-lookup"><span data-stu-id="efbe1-285">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="efbe1-286">Os usos são aplicados em ordem e, se for encontrada uma coincidência no primeiro uso, outros usos nunca serão avaliados.</span><span class="sxs-lookup"><span data-stu-id="efbe1-286">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="efbe1-287">O uso PSTN "internacional" deve ser colocado após o uso da PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="efbe1-287">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="efbe1-288">Para alterar a ordem dos usos de PSTN, execute o `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="efbe1-288">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="efbe1-289">Por exemplo, para alterar a ordem de "EUA e Canadá" primeiro e "internacional" segundo a execução da ordem inversa:</span><span class="sxs-lookup"><span data-stu-id="efbe1-289">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="efbe1-290">A prioridade para as rotas de voz "Other + 1" e "International" são atribuídas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="efbe1-290">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="efbe1-291">Não importa tão tempo que tenham prioridades menores do que "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="efbe1-291">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="efbe1-292">Exemplo 2: etapas de configuração</span><span class="sxs-lookup"><span data-stu-id="efbe1-292">Example 2: Configuration steps</span></span>

<span data-ttu-id="efbe1-293">O exemplo a seguir mostra como:</span><span class="sxs-lookup"><span data-stu-id="efbe1-293">The following example shows how to:</span></span>

1. <span data-ttu-id="efbe1-294">Crie um novo uso de PSTN chamado International.</span><span class="sxs-lookup"><span data-stu-id="efbe1-294">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="efbe1-295">Crie uma nova rota de voz chamada internacional.</span><span class="sxs-lookup"><span data-stu-id="efbe1-295">Create a new voice route called International.</span></span>
3. <span data-ttu-id="efbe1-296">Crie uma política de roteamento de voz chamada sem restrições.</span><span class="sxs-lookup"><span data-stu-id="efbe1-296">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="efbe1-297">Atribua a política ao usuário John Woods.</span><span class="sxs-lookup"><span data-stu-id="efbe1-297">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="efbe1-298">Você pode usar o [centro de administração do Microsoft Teams](#admincenterexample2) ou o [PowerShell](#powershellexample2) para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="efbe1-298">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="efbe1-299">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efbe1-299">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="efbe1-300">Etapa 1: criar o uso de PSTN "internacional"</span><span class="sxs-lookup"><span data-stu-id="efbe1-300">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="efbe1-301">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**Roteamento direto**de **voz** > e, em seguida, no canto superior direito, selecione **gerenciar registros de uso PSTN**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-301">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="efbe1-302">Clique em **Adicionar**, digite **internacional**e, em seguida, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-302">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="efbe1-303">Etapa 2: criar a rota de voz "internacional"</span><span class="sxs-lookup"><span data-stu-id="efbe1-303">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="efbe1-304">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**Roteamento direto**de **voz** > e selecione a guia **rotas de voz** .</span><span class="sxs-lookup"><span data-stu-id="efbe1-304">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="efbe1-305">Clique em **Adicionar**, digite "internacional" como o nome e, em seguida, adicione a descrição.</span><span class="sxs-lookup"><span data-stu-id="efbe1-305">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="efbe1-306">Defina a prioridade como 4 e, em seguida, defina o padrão de número discado como \d +.</span><span class="sxs-lookup"><span data-stu-id="efbe1-306">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="efbe1-307">Em **SBCS registrado (opcional)**, clique em **Adicionar SBCs**, selecione sbc2.contoso.biz e sbc5.contoso.biz e, em seguida, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-307">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="efbe1-308">Em **registros de uso de PSTN (opcional)**, clique em **Adicionar uso de PSTN**, selecione o registro de uso PSTN "internacional" e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-308">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="efbe1-309">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-309">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="efbe1-310">Etapa 3: criar uma política de roteamento de voz chamada "sem restrições" e adicionar os usos de PSTN "EUA e Canadá" e "internacional" à política</span><span class="sxs-lookup"><span data-stu-id="efbe1-310">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="efbe1-311">O uso de PSTN "EUA e Canadá" é reutilizado nesta política de roteamento de voz para preservar a manipulação especial de chamadas para número "+ 1 425 XXX XX XX XX" e "+ 1 206 XXX XX XX" como chamadas locais ou locais.</span><span class="sxs-lookup"><span data-stu-id="efbe1-311">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="efbe1-312">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de roteamento de voz**de **voz** > e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-312">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="efbe1-313">Digite **nenhuma restrição** como o nome e adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="efbe1-313">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="efbe1-314">Em **registros de uso de PSTN**, clique em **Adicionar uso PSTN**, selecione o registro de uso PSTN "EUA e Canadá" e, em seguida, selecione o registro de uso PSTN "internacional".</span><span class="sxs-lookup"><span data-stu-id="efbe1-314">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="efbe1-315">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-315">Click **Apply**.</span></span>

    <span data-ttu-id="efbe1-316">Tome nota da ordem dos usos de PSTN:</span><span class="sxs-lookup"><span data-stu-id="efbe1-316">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="efbe1-317">Se uma chamada feita ao número "+ 1 425 XXX XX XX" com os usos configurados como neste exemplo, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial será aplicada.</span><span class="sxs-lookup"><span data-stu-id="efbe1-317">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="efbe1-318">Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz primeiro e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como as rotas de backup.</span><span class="sxs-lookup"><span data-stu-id="efbe1-318">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="efbe1-319">Se o uso de PSTN "internacional" for anterior aos "EUA e Canadá", as chamadas para + 1 425 XXX XX XX são roteadas para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento.</span><span class="sxs-lookup"><span data-stu-id="efbe1-319">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="efbe1-320">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-320">Click **Save**.</span></span>

<span data-ttu-id="efbe1-321">Para saber mais, consulte [gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="efbe1-321">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="efbe1-322">Etapa 4: atribuir a política de roteamento de voz a um usuário chamado John Woods</span><span class="sxs-lookup"><span data-stu-id="efbe1-322">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="efbe1-323">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="efbe1-323">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="efbe1-324">Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-324">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="efbe1-325">Em **política de roteamento de voz**, selecione a política "sem restrições" e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="efbe1-325">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="efbe1-326">O resultado é que a política de voz aplicada a chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponível para chamadas para os EUA, Canadá e internacional.</span><span class="sxs-lookup"><span data-stu-id="efbe1-326">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="efbe1-327">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="efbe1-327">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="efbe1-328">Etapa 1: criar o uso de PSTN "internacional"</span><span class="sxs-lookup"><span data-stu-id="efbe1-328">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="efbe1-329">Em uma sessão remota do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="efbe1-329">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="efbe1-330">Etapa 2: criar uma nova rota de voz chamada "internacional"</span><span class="sxs-lookup"><span data-stu-id="efbe1-330">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="efbe1-331">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="efbe1-331">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="efbe1-332">Etapa 3: criar uma política de roteamento de voz chamada "sem restrições"</span><span class="sxs-lookup"><span data-stu-id="efbe1-332">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="efbe1-333">O uso de PSTN "Redmond 1" e "Redmond" é reutilizado nesta política de roteamento de voz para preservar a manipulação especial de chamadas para número "+ 1 425 XXX XX XX XX" e "+ 1 206 XXX XX XX" como chamadas locais ou locais.</span><span class="sxs-lookup"><span data-stu-id="efbe1-333">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="efbe1-334">Tome nota da ordem dos usos de PSTN:</span><span class="sxs-lookup"><span data-stu-id="efbe1-334">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="efbe1-335">Se uma chamada feita ao número "+ 1 425 XXX XX XX" com os usos configurados como no exemplo a seguir, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial for aplicada.</span><span class="sxs-lookup"><span data-stu-id="efbe1-335">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="efbe1-336">Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz primeiro e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como as rotas de backup.</span><span class="sxs-lookup"><span data-stu-id="efbe1-336">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="efbe1-337">Se o uso de PSTN "internacional" for anterior aos "EUA e Canadá", as chamadas para + 1 425 XXX XX XX são roteadas para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento.</span><span class="sxs-lookup"><span data-stu-id="efbe1-337">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="efbe1-338">Digite o comando:</span><span class="sxs-lookup"><span data-stu-id="efbe1-338">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="efbe1-339">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="efbe1-339">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="efbe1-340">Etapa 4: atribuir a política de roteamento de voz ao usuário chamado John Woods</span><span class="sxs-lookup"><span data-stu-id="efbe1-340">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="efbe1-341">Em seguida, verifique a tarefa usando o comando:</span><span class="sxs-lookup"><span data-stu-id="efbe1-341">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="efbe1-342">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="efbe1-342">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="efbe1-343">O resultado é que a política de voz aplicada a chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponível para chamadas para os EUA, Canadá e internacional.</span><span class="sxs-lookup"><span data-stu-id="efbe1-343">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="efbe1-344">Confira também</span><span class="sxs-lookup"><span data-stu-id="efbe1-344">See also</span></span>

[<span data-ttu-id="efbe1-345">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="efbe1-345">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="efbe1-346">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="efbe1-346">Configure Direct Routing</span></span>](direct-routing-configure.md)
