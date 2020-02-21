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
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157923"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="4234a-103">Configurar o roteamento de voz para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="4234a-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="4234a-104">Este artigo descreve como configurar o roteamento de voz para o roteamento direto do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="4234a-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="4234a-105">Esta é a etapa 3 das seguintes etapas para configurar o roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="4234a-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="4234a-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="4234a-106">Step 1.</span></span> [<span data-ttu-id="4234a-107">Conectar o SBC com o sistema Microsoft Phone e validar a conexão</span><span class="sxs-lookup"><span data-stu-id="4234a-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="4234a-108">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="4234a-108">Step 2.</span></span> [<span data-ttu-id="4234a-109">Habilite os usuários para roteamento direto, voz e correio de voz</span><span class="sxs-lookup"><span data-stu-id="4234a-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)    
- <span data-ttu-id="4234a-110">**Etapa 3. Configurar roteamento de voz** (este artigo)</span><span class="sxs-lookup"><span data-stu-id="4234a-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="4234a-111">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="4234a-111">Step 4.</span></span> [<span data-ttu-id="4234a-112">Converter números em um formato alternativo</span><span class="sxs-lookup"><span data-stu-id="4234a-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="4234a-113">Para obter informações sobre todas as etapas necessárias para configurar o roteamento direto, consulte [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="4234a-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="4234a-114">Visão geral do roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="4234a-114">Voice routing overview</span></span>

<span data-ttu-id="4234a-115">O sistema telefônico da Microsoft tem um mecanismo de roteamento que permite que uma chamada seja enviada para um controlador de borda de sessão (SBC) específico com base em:</span><span class="sxs-lookup"><span data-stu-id="4234a-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="4234a-116">O padrão de número chamado</span><span class="sxs-lookup"><span data-stu-id="4234a-116">The called number pattern</span></span> 
- <span data-ttu-id="4234a-117">O padrão de número chamado mais o usuário específico que faz a chamada</span><span class="sxs-lookup"><span data-stu-id="4234a-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="4234a-118">A SBCs pode ser designada como ativa e de backup.</span><span class="sxs-lookup"><span data-stu-id="4234a-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="4234a-119">Quando o SBC que está configurado como ativo não está disponível para uma rota de chamada específica, a chamada será roteada para um SBC de backup.</span><span class="sxs-lookup"><span data-stu-id="4234a-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="4234a-120">O roteamento de voz é composto pelos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="4234a-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="4234a-121">**Política de roteamento de voz** – um contêiner para usos de PSTN que podem ser atribuídos a um usuário ou a vários usuários.</span><span class="sxs-lookup"><span data-stu-id="4234a-121">**Voice routing policy** – A container for PSTN Usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="4234a-122">**Usos de PSTN** – um contêiner para rotas de voz e usos de PSTN, que podem ser compartilhados em diferentes políticas de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="4234a-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="4234a-123">**Rotas de voz** – um padrão de número e um conjunto de gateways PSTN online a serem usados para chamadas onde o número de chamada corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="4234a-123">**Voice Routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="4234a-124">**Gateway PSTN online** -um ponteiro para um SBC que também armazena a configuração aplicada quando uma chamada é feita por meio do SBC, como encaminhamento P-declarada-identidade (pai) ou codecs preferenciais; pode ser adicionado a roteiros de voz.</span><span class="sxs-lookup"><span data-stu-id="4234a-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="4234a-125">Exemplo 1: roteamento de voz com um uso PSTN</span><span class="sxs-lookup"><span data-stu-id="4234a-125">Example 1: Voice routing with one PSTN Usage</span></span>

<span data-ttu-id="4234a-126">O diagrama a seguir mostra dois exemplos de políticas de roteamento de voz em um fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="4234a-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="4234a-127">**Fluxo de chamadas 1 (à esquerda):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada para o SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="4234a-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="4234a-128">Se nem sbc1.contoso.biz nem sbc2.contoso.biz estiverem disponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="4234a-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="4234a-129">**Fluxo de chamadas 2 (à direita):** Se um usuário fizer uma chamada para + 1 425 XXX XX XX ou + 1 206 XXX XX XX, a chamada será roteada primeiro para o SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="4234a-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="4234a-130">Se nenhum SBC estiver disponível, a rota com prioridade menor será tentada (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="4234a-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="4234a-131">Se nenhum dos SBCs estiver disponível, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="4234a-131">If none of the SBCs are available, the call is dropped.</span></span> 

![Mostra exemplos de política de roteamento de voz](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="4234a-133">Nos dois exemplos, enquanto a rota de voz é atribuída às prioridades, o SBCs nos roteiros é tentado em ordem aleatória.</span><span class="sxs-lookup"><span data-stu-id="4234a-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4234a-134">A menos que o usuário também tenha uma licença do plano de chamadas da Microsoft, as chamadas para qualquer número, exceto números que correspondam aos padrões + 1 425 XXX XX XX ou + 1 206 XXX XX XX no exemplo de configuração são descartados.</span><span class="sxs-lookup"><span data-stu-id="4234a-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="4234a-135">Se o usuário tiver uma licença de plano de chamada, a chamada será roteada automaticamente de acordo com as políticas do plano de chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4234a-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="4234a-136">O plano de chamadas da Microsoft aplica-se automaticamente como a última rota para todos os usuários com a licença do plano de chamadas da Microsoft e não requer configuração de roteamento de chamadas adicional.</span><span class="sxs-lookup"><span data-stu-id="4234a-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="4234a-137">No exemplo mostrado no diagrama a seguir, uma rota de voz é adicionada para enviar chamadas para todos os outros números canadenses e EUA (chamadas que vão para o padrão de número chamado + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="4234a-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra a política de roteamento de voz com uma terceira rota](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="4234a-139">Para todas as outras chamadas:</span><span class="sxs-lookup"><span data-stu-id="4234a-139">For all other calls:</span></span>

- <span data-ttu-id="4234a-140">Se um usuário tiver licenças (sistema telefônico da Microsoft e Microsoft Calling plano), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="4234a-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="4234a-141">Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, a chamada será roteada pelo plano de chamadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4234a-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="4234a-142">Se o usuário tiver apenas o Microsoft Phone System, a chamada será descartada porque nenhuma regra de correspondência estará disponível.</span><span class="sxs-lookup"><span data-stu-id="4234a-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4234a-143">O valor de prioridade para a rota "Other + 1" não importa nesse caso porque há apenas uma rota que corresponde ao padrão + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="4234a-143">The Priority value for route "Other +1" doesn’t matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="4234a-144">Se um usuário fizer uma chamada para + 1 324 567 89 89 e sbc5.contoso.biz e sbc6.contoso.biz estiverem indisponíveis, a chamada será interrompida.</span><span class="sxs-lookup"><span data-stu-id="4234a-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="4234a-145">A tabela a seguir resume a configuração usando três rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="4234a-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="4234a-146">Neste exemplo, todas as três rotas fazem parte do mesmo uso de PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="4234a-146">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>  <span data-ttu-id="4234a-147">Todas as rotas são associadas ao uso de PSTN "EUA e Canadá" e o uso de PSTN está associado apenas à política de roteamento de voz "apenas para os EUA".</span><span class="sxs-lookup"><span data-stu-id="4234a-147">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> 

|<span data-ttu-id="4234a-148">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="4234a-148">**PSTN usage**</span></span>|<span data-ttu-id="4234a-149">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="4234a-149">**Voice route**</span></span>|<span data-ttu-id="4234a-150">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="4234a-150">**Number pattern**</span></span>|<span data-ttu-id="4234a-151">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="4234a-151">**Priority**</span></span>|<span data-ttu-id="4234a-152">**SBC**</span><span class="sxs-lookup"><span data-stu-id="4234a-152">**SBC**</span></span>|<span data-ttu-id="4234a-153">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4234a-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4234a-154">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="4234a-154">US only</span></span>|<span data-ttu-id="4234a-155">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="4234a-155">"Redmond 1"</span></span>|<span data-ttu-id="4234a-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4234a-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4234a-157">1</span><span class="sxs-lookup"><span data-stu-id="4234a-157">1</span></span>|<span data-ttu-id="4234a-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="4234a-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="4234a-160">Roteiro ativo para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4234a-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4234a-161">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="4234a-161">US only</span></span>|<span data-ttu-id="4234a-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="4234a-162">"Redmond 2"</span></span>|<span data-ttu-id="4234a-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4234a-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4234a-164">2</span><span class="sxs-lookup"><span data-stu-id="4234a-164">2</span></span>|<span data-ttu-id="4234a-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="4234a-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="4234a-167">Rota de backup para números chamados + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4234a-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4234a-168">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="4234a-168">US only</span></span>|<span data-ttu-id="4234a-169">"Outro + 1"</span><span class="sxs-lookup"><span data-stu-id="4234a-169">"Other +1"</span></span>|<span data-ttu-id="4234a-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="4234a-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="4234a-171">3</span><span class="sxs-lookup"><span data-stu-id="4234a-171">3</span></span>|<span data-ttu-id="4234a-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="4234a-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="4234a-174">Rota para números chamados + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="4234a-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||


### <a name="example-1-configuration-steps"></a><span data-ttu-id="4234a-175">Exemplo 1: etapas de configuração</span><span class="sxs-lookup"><span data-stu-id="4234a-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="4234a-176">O exemplo a seguir mostra como:</span><span class="sxs-lookup"><span data-stu-id="4234a-176">The following example shows how to:</span></span>

- <span data-ttu-id="4234a-177">Criar um único uso de PSTN</span><span class="sxs-lookup"><span data-stu-id="4234a-177">Create a single PSTN Usage</span></span> 
- <span data-ttu-id="4234a-178">Configurar três rotas de voz</span><span class="sxs-lookup"><span data-stu-id="4234a-178">Configure three voice routes</span></span>
- <span data-ttu-id="4234a-179">Criar uma política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="4234a-179">Create a voice routing policy</span></span>
- <span data-ttu-id="4234a-180">Atribuir a política ao usuário Spencer-baixo</span><span class="sxs-lookup"><span data-stu-id="4234a-180">Assign the policy to user Spencer Low</span></span>

<span data-ttu-id="4234a-181">**Etapa 1:** Criar o uso de PSTN "EUA e Canadá"</span><span class="sxs-lookup"><span data-stu-id="4234a-181">**Step 1:** Create the PSTN Usage "US and Canada"</span></span>

<span data-ttu-id="4234a-182">Em uma sessão do PowerShell remoto do Skype for Business, digite:</span><span class="sxs-lookup"><span data-stu-id="4234a-182">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="4234a-183">Valide se o uso foi criado inserindo:</span><span class="sxs-lookup"><span data-stu-id="4234a-183">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="4234a-184">Que retorna uma lista de nomes que podem estar truncados:</span><span class="sxs-lookup"><span data-stu-id="4234a-184">Which returns a list of names that may be truncated:</span></span>
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="4234a-185">O exemplo a seguir mostra o resultado da execução do comando `(Get-CSOnlinePSTNUsage).usage` do PowerShell para exibir nomes completos (não truncados):</span><span class="sxs-lookup"><span data-stu-id="4234a-185">The example below shows the result of  running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated):</span></span>

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

<span data-ttu-id="4234a-186">**Etapa 2:** Em uma sessão do PowerShell no Skype for Business Online, crie três rotas: Redmond 1, Redmond 2 e outros + 1, conforme mostrado na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="4234a-186">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as shown in the previous table</span></span>

<span data-ttu-id="4234a-187">Para criar a rota "Redmond 1", digite:</span><span class="sxs-lookup"><span data-stu-id="4234a-187">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4234a-188">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="4234a-188">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="4234a-189">Para criar a rota Redmond 2, digite:</span><span class="sxs-lookup"><span data-stu-id="4234a-189">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4234a-190">Para criar a outra rota + 1, digite:</span><span class="sxs-lookup"><span data-stu-id="4234a-190">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="4234a-191">Certifique-se de que sua expressão regular no atributo NumberPattern é uma expressão válida.</span><span class="sxs-lookup"><span data-stu-id="4234a-191">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="4234a-192">Você pode testá-lo usando este site:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="4234a-192">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="4234a-193">Em alguns casos, há a necessidade de rotear todas as chamadas para o mesmo SBC; Use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="4234a-193">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="4234a-194">Rotear todas as chamadas para o mesmo SBC.</span><span class="sxs-lookup"><span data-stu-id="4234a-194">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="4234a-195">Valide se você configurou corretamente a rota executando o comando `Get-CSOnlineVoiceRoute` do PowerShell usando as opções, conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="4234a-195">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="4234a-196">Que deve retornar:</span><span class="sxs-lookup"><span data-stu-id="4234a-196">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="4234a-197">No exemplo, a rota "Other + 1" foi automaticamente atribuída à prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="4234a-197">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="4234a-198">**Etapa 3:** Crie uma política de roteamento de voz "apenas EUA" e adicione à política o uso de PSTN "EUA e Canadá".</span><span class="sxs-lookup"><span data-stu-id="4234a-198">**Step 3:** Create a voice routing policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="4234a-199">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="4234a-199">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4234a-200">O resultado é mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="4234a-200">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="4234a-201">**Etapa 4:** Ao usar o PowerShell, conceda a política de roteamento de voz ao usuário Spencer para baixo:</span><span class="sxs-lookup"><span data-stu-id="4234a-201">**Step 4:** By using PowerShell, grant the voice routing policy to the user Spencer Low:</span></span>

<span data-ttu-id="4234a-202">Em uma sessão do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="4234a-202">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="4234a-203">Valide a atribuição de política inserindo este comando:</span><span class="sxs-lookup"><span data-stu-id="4234a-203">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="4234a-204">O comando retorna o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4234a-204">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="4234a-205">Exemplo 2: roteamento de voz com vários usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="4234a-205">Example 2: Voice routing with multiple PSTN Usages</span></span>

<span data-ttu-id="4234a-206">A política de roteamento de voz criada no exemplo 1 só permite chamadas para números de telefone nos EUA e no Canadá, a menos que a licença do plano de chamadas da Microsoft também seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="4234a-206">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="4234a-207">No exemplo a seguir, você pode criar a política de roteamento de voz "sem restrições".</span><span class="sxs-lookup"><span data-stu-id="4234a-207">In the example that follows, you can create the voice routing policy "No Restrictions."</span></span> <span data-ttu-id="4234a-208">A política reutiliza o uso de PSTN "EUA e Canadá" criado no exemplo 1, bem como o novo uso de PSTN "internacional".</span><span class="sxs-lookup"><span data-stu-id="4234a-208">The policy reuses the PSTN Usage "US and Canada" created in Example 1, as well as the new PSTN Usage "International."</span></span>  <span data-ttu-id="4234a-209">Esta política roteia todas as outras chamadas para o SBCs sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="4234a-209">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> 

<span data-ttu-id="4234a-210">Os exemplos mostrados atribuem a política apenas EUA para o usuário Spencer baixo e a política sem restrições ao usuário John Woods para que o roteamento ocorra da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4234a-210">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="4234a-211">Spencer baixo – política apenas para os EUA.</span><span class="sxs-lookup"><span data-stu-id="4234a-211">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="4234a-212">As chamadas são permitidas apenas para números canadenses e Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="4234a-212">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="4234a-213">Ao ligar para o intervalo de números Redmond, o conjunto específico de SBCs deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="4234a-213">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="4234a-214">Os números que não são dos EUA não serão roteados, a menos que a licença do plano de chamada seja atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="4234a-214">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="4234a-215">John Woods – política internacional.</span><span class="sxs-lookup"><span data-stu-id="4234a-215">John Woods – International policy.</span></span>  <span data-ttu-id="4234a-216">As chamadas são permitidas para qualquer número.</span><span class="sxs-lookup"><span data-stu-id="4234a-216">Calls are allowed to any number.</span></span> <span data-ttu-id="4234a-217">Ao ligar para o intervalo de números Redmond, o conjunto específico de SBCs deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="4234a-217">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="4234a-218">Os números que não são dos EUA serão encaminhados usando sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="4234a-218">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário Spencer baixo](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="4234a-220">Para todas as outras chamadas, se um usuário tiver licenças (sistema telefônico da Microsoft e plano de chamadas da Microsoft), a rota automática será usada.</span><span class="sxs-lookup"><span data-stu-id="4234a-220">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="4234a-221">Se nada coincidir com os padrões de número nas rotas de voz online criadas pelo administrador, a chamada será roteada usando o plano de chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4234a-221">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="4234a-222">Se o usuário tiver apenas um sistema telefônico da Microsoft, a chamada será descartada porque nenhuma regra de correspondência estará disponível.</span><span class="sxs-lookup"><span data-stu-id="4234a-222">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra a política de roteamento de voz atribuída ao usuário John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="4234a-224">A tabela a seguir resume as designações de uso de política de roteamento "sem restrições" e rotas de voz.</span><span class="sxs-lookup"><span data-stu-id="4234a-224">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="4234a-225">**Uso de PSTN**</span><span class="sxs-lookup"><span data-stu-id="4234a-225">**PSTN usage**</span></span>|<span data-ttu-id="4234a-226">**Rota de voz**</span><span class="sxs-lookup"><span data-stu-id="4234a-226">**Voice route**</span></span>|<span data-ttu-id="4234a-227">**Padrão de número**</span><span class="sxs-lookup"><span data-stu-id="4234a-227">**Number pattern**</span></span>|<span data-ttu-id="4234a-228">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="4234a-228">**Priority**</span></span>|<span data-ttu-id="4234a-229">**SBC**</span><span class="sxs-lookup"><span data-stu-id="4234a-229">**SBC**</span></span>|<span data-ttu-id="4234a-230">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4234a-230">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4234a-231">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="4234a-231">US Only</span></span>|<span data-ttu-id="4234a-232">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="4234a-232">"Redmond 1"</span></span>|<span data-ttu-id="4234a-233">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4234a-233">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4234a-234">1</span><span class="sxs-lookup"><span data-stu-id="4234a-234">1</span></span>|<span data-ttu-id="4234a-235">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-235">sbc1.contoso.biz</span></span><br/><span data-ttu-id="4234a-236">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-236">sbc2.contoso.biz</span></span>|<span data-ttu-id="4234a-237">Roteiro ativo para números de chamada + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4234a-237">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4234a-238">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="4234a-238">US Only</span></span>|<span data-ttu-id="4234a-239">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="4234a-239">"Redmond 2"</span></span>|<span data-ttu-id="4234a-240">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4234a-240">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4234a-241">2</span><span class="sxs-lookup"><span data-stu-id="4234a-241">2</span></span>|<span data-ttu-id="4234a-242">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-242">sbc3.contoso.biz</span></span><br/><span data-ttu-id="4234a-243">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-243">sbc4.contoso.biz</span></span>|<span data-ttu-id="4234a-244">Rota de backup para números do chamado + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4234a-244">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4234a-245">Somente EUA</span><span class="sxs-lookup"><span data-stu-id="4234a-245">US Only</span></span>|<span data-ttu-id="4234a-246">"Outro + 1"</span><span class="sxs-lookup"><span data-stu-id="4234a-246">"Other +1"</span></span>|<span data-ttu-id="4234a-247">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="4234a-247">^\\+1(\d{10})$</span></span>|<span data-ttu-id="4234a-248">3</span><span class="sxs-lookup"><span data-stu-id="4234a-248">3</span></span>|<span data-ttu-id="4234a-249">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-249">sbc5.contoso.biz</span></span><br/><span data-ttu-id="4234a-250">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-250">sbc6>.contoso.biz</span></span>|<span data-ttu-id="4234a-251">Rota para números de chamada + 1 XXX XXX XX XX (exceto + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="4234a-251">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="4234a-252">International</span><span class="sxs-lookup"><span data-stu-id="4234a-252">International</span></span>|<span data-ttu-id="4234a-253">International</span><span class="sxs-lookup"><span data-stu-id="4234a-253">International</span></span>|<span data-ttu-id="4234a-254">\d +</span><span class="sxs-lookup"><span data-stu-id="4234a-254">\d+</span></span>|<span data-ttu-id="4234a-255">4</span><span class="sxs-lookup"><span data-stu-id="4234a-255">4</span></span>|<span data-ttu-id="4234a-256">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-256">sbc2.contoso.biz</span></span><br/><span data-ttu-id="4234a-257">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4234a-257">sbc5.contoso.biz</span></span>|<span data-ttu-id="4234a-258">Rota para qualquer padrão de número</span><span class="sxs-lookup"><span data-stu-id="4234a-258">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="4234a-259">A ordem dos usos de PSTN nas políticas de roteamento de voz é crítica.</span><span class="sxs-lookup"><span data-stu-id="4234a-259">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="4234a-260">Os usos são aplicados em ordem e, se for encontrada uma coincidência no primeiro uso, outros usos nunca serão avaliados.</span><span class="sxs-lookup"><span data-stu-id="4234a-260">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="4234a-261">O uso de PSTN "internacional" deve ser colocado após o uso de PSTN "somente EUA".</span><span class="sxs-lookup"><span data-stu-id="4234a-261">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="4234a-262">Para alterar a ordem dos usos de PSTN, execute o `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="4234a-262">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="4234a-263">Por exemplo, para alterar a ordem de "EUA e Canadá" primeiro e "internacional" segundo a execução da ordem inversa:</span><span class="sxs-lookup"><span data-stu-id="4234a-263">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="4234a-264">A prioridade para as rotas de voz "Other + 1" e "International" são atribuídas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4234a-264">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="4234a-265">Não importa tão tempo que tenham prioridades menores do que "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="4234a-265">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>


### <a name="example-2-configuration-steps"></a><span data-ttu-id="4234a-266">Exemplo 2: etapas de configuração</span><span class="sxs-lookup"><span data-stu-id="4234a-266">Example 2: Configuration steps</span></span>

<span data-ttu-id="4234a-267">O exemplo a seguir mostra como:</span><span class="sxs-lookup"><span data-stu-id="4234a-267">The following example shows how to:</span></span>

- <span data-ttu-id="4234a-268">Criar um novo uso de PSTN chamado International</span><span class="sxs-lookup"><span data-stu-id="4234a-268">Create a new PSTN Usage called International</span></span>
- <span data-ttu-id="4234a-269">Criar uma nova rota de voz chamada internacional</span><span class="sxs-lookup"><span data-stu-id="4234a-269">Create a new voice route called International</span></span>
- <span data-ttu-id="4234a-270">Criar uma política de roteamento de voz chamada sem restrições</span><span class="sxs-lookup"><span data-stu-id="4234a-270">Create a voice routing policy called No Restrictions</span></span>
- <span data-ttu-id="4234a-271">Atribuir a política ao usuário John Woods</span><span class="sxs-lookup"><span data-stu-id="4234a-271">Assign the policy to user John Woods</span></span>


<span data-ttu-id="4234a-272">**Etapa 1**: criar o uso de PSTN "internacional".</span><span class="sxs-lookup"><span data-stu-id="4234a-272">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="4234a-273">Em uma sessão remota do PowerShell no Skype for Business Online, digite:</span><span class="sxs-lookup"><span data-stu-id="4234a-273">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="4234a-274">**Etapa 2**: criar a nova rota de voz "internacional".</span><span class="sxs-lookup"><span data-stu-id="4234a-274">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="4234a-275">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="4234a-275">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="4234a-276">**Etapa 3**: criar uma política de roteamento de voz "sem restrições".</span><span class="sxs-lookup"><span data-stu-id="4234a-276">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="4234a-277">O uso de PSTN "Redmond 1" e "Redmond" é reutilizado nesta política de roteamento de voz para preservar a manipulação especial de chamadas para número "+ 1 425 XXX XX XX XX" e "+ 1 206 XXX XX XX" como chamadas locais ou locais.</span><span class="sxs-lookup"><span data-stu-id="4234a-277">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="4234a-278">Tome nota da ordem dos usos de PSTN:</span><span class="sxs-lookup"><span data-stu-id="4234a-278">Take note of the order of PSTN Usages:</span></span>

  <span data-ttu-id="4234a-279">a.</span><span class="sxs-lookup"><span data-stu-id="4234a-279">a.</span></span> <span data-ttu-id="4234a-280">Se uma chamada feita ao número "+ 1 425 XXX XX XX" com os usos configurados como no exemplo a seguir, a chamada seguirá a rota definida no uso "EUA e Canadá" e a lógica de roteamento especial for aplicada.</span><span class="sxs-lookup"><span data-stu-id="4234a-280">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="4234a-281">Ou seja, a chamada é roteada usando sbc1.contoso.biz e sbc2.contoso.biz primeiro e, em seguida, sbc3.contoso.biz e sbc4.contoso.biz como as rotas de backup.</span><span class="sxs-lookup"><span data-stu-id="4234a-281">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  <span data-ttu-id="4234a-282">b.</span><span class="sxs-lookup"><span data-stu-id="4234a-282">b.</span></span> <span data-ttu-id="4234a-283">Se o uso de PSTN "internacional" for anterior aos "EUA e Canadá", as chamadas para + 1 425 XXX XX XX são roteadas para sbc2.contoso.biz e sbc5.contoso.biz como parte da lógica de roteamento.</span><span class="sxs-lookup"><span data-stu-id="4234a-283">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="4234a-284">Digite o comando:</span><span class="sxs-lookup"><span data-stu-id="4234a-284">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="4234a-285">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="4234a-285">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

<span data-ttu-id="4234a-286">**Etapa 4**: atribua a política de roteamento de voz ao usuário "John Woods" usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="4234a-286">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="4234a-287">Em seguida, verifique a tarefa usando o comando:</span><span class="sxs-lookup"><span data-stu-id="4234a-287">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="4234a-288">Que retorna:</span><span class="sxs-lookup"><span data-stu-id="4234a-288">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="4234a-289">O resultado é que a política de voz aplicada a chamadas de John Woods é irrestrita e seguirá a lógica de roteamento de chamadas disponível para chamadas para os EUA, Canadá e internacional.</span><span class="sxs-lookup"><span data-stu-id="4234a-289">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>



## <a name="see-also"></a><span data-ttu-id="4234a-290">Confira também</span><span class="sxs-lookup"><span data-stu-id="4234a-290">See also</span></span>

[<span data-ttu-id="4234a-291">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="4234a-291">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="4234a-292">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="4234a-292">Configure Direct Routing</span></span>](direct-routing-configure.md)
