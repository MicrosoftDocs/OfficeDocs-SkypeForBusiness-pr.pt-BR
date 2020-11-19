---
title: Criar uma fila de chamadas no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Saiba como configurar o sistema telefônico para filas de chamadas com o Microsoft Teams, que fornecem uma mensagem de saudação, suspender música, redirecionamento de chamada e outros recursos.
ms.openlocfilehash: 57ef565a333f89772f5c9d35d664785c2e166679
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49135939"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="3b342-103">Criar uma fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="3b342-103">Create a call queue</span></span>

<span data-ttu-id="3b342-104">As filas de chamadas fornecem um método de roteamento de chamadores para as pessoas em sua organização que podem ajudá-lo com um problema ou uma pergunta específica.</span><span class="sxs-lookup"><span data-stu-id="3b342-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="3b342-105">As chamadas são distribuídas uma de cada vez para as pessoas na fila (que são conhecidas como *agentes*).</span><span class="sxs-lookup"><span data-stu-id="3b342-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="3b342-106">As filas de chamadas fornecem:</span><span class="sxs-lookup"><span data-stu-id="3b342-106">Call queues provide:</span></span>

- <span data-ttu-id="3b342-107">Uma mensagem de saudação.</span><span class="sxs-lookup"><span data-stu-id="3b342-107">A greeting message.</span></span>

- <span data-ttu-id="3b342-108">Música enquanto as pessoas estão aguardando em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="3b342-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="3b342-109">Roteamento de chamadas em *primeiro lugar, em primeiro lugar* (FIFO) para agentes.</span><span class="sxs-lookup"><span data-stu-id="3b342-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="3b342-110">Opções de manipulação para estouro de fila e tempo limite.</span><span class="sxs-lookup"><span data-stu-id="3b342-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="3b342-111">Verifique se você leu o [plano de atendedores automáticos e filas de chamadas do teams](plan-auto-attendant-call-queue.md) e seguiu as [etapas de introdução](plan-auto-attendant-call-queue.md#getting-started) antes de seguir os procedimentos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="3b342-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="3b342-112">Para configurar uma fila de chamadas, no centro de administração do Teams, expanda **voz**, clique em **filas de chamadas** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3b342-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="3b342-113">Conta e idioma do recurso</span><span class="sxs-lookup"><span data-stu-id="3b342-113">Resource account and language</span></span>

![Captura de tela da conta do recurso e das configurações de idioma](media/call-queue-name-language.png)

1. <span data-ttu-id="3b342-115">Digite um nome para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b342-115">Type a name for the call queue.</span></span> <span data-ttu-id="3b342-116">Os agentes verão esse nome quando receberem uma chamada de entrada da fila.</span><span class="sxs-lookup"><span data-stu-id="3b342-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="3b342-117">Clique em **Adicionar contas**, procure a conta de recurso que você deseja usar com esta fila de chamadas, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3b342-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="3b342-118">Escolha um idioma.</span><span class="sxs-lookup"><span data-stu-id="3b342-118">Choose a language.</span></span> <span data-ttu-id="3b342-119">Esse idioma será usado para solicitações de voz geradas pelo sistema e para a transcrição de correio de voz (se você habilitá-las).</span><span class="sxs-lookup"><span data-stu-id="3b342-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="3b342-120">Saudações e música em espera na fila</span><span class="sxs-lookup"><span data-stu-id="3b342-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="3b342-121">Especifique se deseja reproduzir uma saudação para os chamadores quando chegarem na fila.</span><span class="sxs-lookup"><span data-stu-id="3b342-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="3b342-122">Você deve carregar um arquivo MP3, WAV ou WMA contendo a saudação que deseja reproduzir.</span><span class="sxs-lookup"><span data-stu-id="3b342-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="3b342-123">O Teams oferece música padrão para chamadores enquanto estiverem em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="3b342-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="3b342-124">Se você quiser executar um arquivo de áudio específico, escolha **executar um arquivo de áudio** e carregar um arquivo MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="3b342-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="3b342-125">A gravação carregada não pode ter mais de 5 MB.</span><span class="sxs-lookup"><span data-stu-id="3b342-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="3b342-126">A música padrão fornecida nas filas de chamadas do teams é de graça dos royalties pagos por sua organização.</span><span class="sxs-lookup"><span data-stu-id="3b342-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="3b342-127">Agentes de chamada</span><span class="sxs-lookup"><span data-stu-id="3b342-127">Call agents</span></span>

<span data-ttu-id="3b342-128">Confira os [pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) para poder adicionar agentes a uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b342-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![Captura de tela de configurações de usuários e grupos para filas de chamadas](media/call-queue-users-groups.png)

<span data-ttu-id="3b342-130">Você pode adicionar até 20 agentes individualmente e até 200 agentes por meio de grupos.</span><span class="sxs-lookup"><span data-stu-id="3b342-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="3b342-131">Para adicionar um usuário à fila, clique em **Adicionar usuários**, procure o usuário, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3b342-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="3b342-132">Para adicionar um grupo à fila, clique em **Adicionar grupos**, procure o grupo, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3b342-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="3b342-133">Você pode usar listas de distribuição, grupos de segurança e grupos do Microsoft 365 ou Microsoft Teams Teams.</span><span class="sxs-lookup"><span data-stu-id="3b342-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="3b342-134">Novos usuários adicionados a um grupo podem levar até oito horas para que a primeira chamada seja recebida.</span><span class="sxs-lookup"><span data-stu-id="3b342-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="3b342-135">Roteamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="3b342-135">Call routing</span></span>

![Captura de tela das configurações do modo de conferência e do método de roteamento](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="3b342-137">O **modo de conferência** reduz significativamente o tempo necessário para que um chamador seja conectado a um agente, após o agente aceitar a chamada.</span><span class="sxs-lookup"><span data-stu-id="3b342-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="3b342-138">Para que o modo de conferência funcione, os agentes na fila de chamadas devem usar um dos seguintes clientes:</span><span class="sxs-lookup"><span data-stu-id="3b342-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="3b342-139">A versão mais recente do cliente de desktop do Microsoft Teams, do aplicativo Android ou do aplicativo iOS</span><span class="sxs-lookup"><span data-stu-id="3b342-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="3b342-140">Microsoft Teams Phone versão 1449/1.0.94.2020051601 ou posterior</span><span class="sxs-lookup"><span data-stu-id="3b342-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="3b342-141">Contas de equipe dos agentes devem ser definidas no modo somente para equipes.</span><span class="sxs-lookup"><span data-stu-id="3b342-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="3b342-142">Os agentes que não atendem aos requisitos não são incluídos na lista de circulação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b342-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="3b342-143">Recomendamos habilitar o modo de conferência para suas filas de chamadas se os seus agentes estiverem usando clientes compatíveis.</span><span class="sxs-lookup"><span data-stu-id="3b342-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="3b342-144">Ocupado em ocupado não é compatível com o modo de conferência.</span><span class="sxs-lookup"><span data-stu-id="3b342-144">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="3b342-145">Os agentes em chamadas de fila de não chamada ainda poderão ser apresentados com uma chamada na fila de chamadas se o roteamento baseado em presença não estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="3b342-145">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="3b342-146">O **método de roteamento** determina a ordem em que os agentes recebem chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="3b342-146">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="3b342-147">Escolha uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="3b342-147">Choose from these options:</span></span>

- <span data-ttu-id="3b342-148">O **Roteamento do atendente** toca todos os agentes na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="3b342-148">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="3b342-149">O primeiro agente de chamadas para atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="3b342-149">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="3b342-150">O **Roteamento serial** toca todos os agentes de chamada um por um na ordem especificada na lista de **agentes de chamada** .</span><span class="sxs-lookup"><span data-stu-id="3b342-150">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="3b342-151">Se um agente ignorar ou não atender a chamada, a chamada tocará no próximo agente e experimentará todos os agentes até que ele seja retirado ou expirado.</span><span class="sxs-lookup"><span data-stu-id="3b342-151">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="3b342-152">A **repetição redonda** equilibra o roteamento de chamadas de entrada para que cada agente de chamadas obtenha o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="3b342-152">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="3b342-153">Isso pode ser desejável em um ambiente de vendas de entrada para garantir uma oportunidade igual entre todos os agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b342-153">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="3b342-154">O mais **longo** é direcionado a cada chamada para o agente que esteve ocioso ao longo do tempo mais longo.</span><span class="sxs-lookup"><span data-stu-id="3b342-154">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="3b342-155">Um agente será considerado ocioso se seu estado de presença estiver disponível ou se o estado de presença ficar ausente por menos de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="3b342-155">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="3b342-156">Os agentes cujo estado de presença esteve ausente por mais de 10 minutos não são considerados ociosos e não ficarão qualificados para receber chamadas até que eles alterem sua presença para disponível.</span><span class="sxs-lookup"><span data-stu-id="3b342-156">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Captura de tela das configurações de roteamento, cancelamento e tempo de alerta](media/call-queue-presence-agents-time.png)


<span data-ttu-id="3b342-158">O **roteamento baseado em presença** usa o status de disponibilidade dos agentes de chamada para determinar se um agente deve ser incluído na lista de roteamento de chamadas para o método de roteamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="3b342-158">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="3b342-159">Os agentes de chamada cujo status de disponibilidade está definido como **disponível** estão incluídos na lista de circulação de chamadas e podem receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b342-159">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="3b342-160">Os agentes cujo status de disponibilidade é definido como qualquer outro status serão excluídos da lista de roteamento de chamadas e não receberão chamadas até que seu status de disponibilidade mude novamente para **disponível**.</span><span class="sxs-lookup"><span data-stu-id="3b342-160">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="3b342-161">Você pode habilitar o roteamento de chamadas baseado em presença com qualquer um dos métodos de roteamento.</span><span class="sxs-lookup"><span data-stu-id="3b342-161">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="3b342-162">Se um agente optar por não receber chamadas, ele não será incluído na lista de roteamento de chamadas, independentemente do seu status de disponibilidade definido como.</span><span class="sxs-lookup"><span data-stu-id="3b342-162">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="3b342-163">Os agentes que usam o cliente Skype for Business não são incluídos na lista de roteamento de chamadas quando o roteamento baseado em presença está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3b342-163">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="3b342-164">Se você tiver agentes que usam o Skype for Business, não habilite o encaminhamento de chamadas baseado em presença.</span><span class="sxs-lookup"><span data-stu-id="3b342-164">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="3b342-165">**Tempo de alerta do agente** especifica quanto tempo o telefone do agente tocará antes de a fila redirecionar a chamada para o próximo agente.</span><span class="sxs-lookup"><span data-stu-id="3b342-165">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="3b342-166">Para filas de alto volume, recomendamos as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="3b342-166">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="3b342-167">**Modo de conferência** para **automático**</span><span class="sxs-lookup"><span data-stu-id="3b342-167">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="3b342-168">**Método de roteamento** para o **Roteamento do atendente**</span><span class="sxs-lookup"><span data-stu-id="3b342-168">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="3b342-169">**Roteamento baseado em presença** para **ativado**</span><span class="sxs-lookup"><span data-stu-id="3b342-169">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="3b342-170">**Tempo de alerta do agente:** para **20 segundos**</span><span class="sxs-lookup"><span data-stu-id="3b342-170">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="3b342-171">Tratamento de estouro de chamadas</span><span class="sxs-lookup"><span data-stu-id="3b342-171">Call overflow handling</span></span>

![Captura de tela das configurações de estouro de chamadas](media/call-queue-overflow-handling.png)

<span data-ttu-id="3b342-173">O **máximo de chamadas na fila** especifica o número máximo de chamadas que podem esperar na fila a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="3b342-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="3b342-174">O padrão é 50, mas pode variar de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="3b342-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="3b342-175">Quando esse limite for atingido, a chamada será manipulada conforme especificado pela configuração **quando o número máximo de chamadas for atingido** .</span><span class="sxs-lookup"><span data-stu-id="3b342-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="3b342-176">Você pode optar por desconectar a chamada ou redirecioná-la para qualquer um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b342-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="3b342-177">Por exemplo, você pode ter o chamador deixar um correio de voz para os agentes na fila.</span><span class="sxs-lookup"><span data-stu-id="3b342-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="3b342-178">Para transferências externas, consulte [pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) e as [transferências de número de telefone externo-detalhes técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) de formatação de números.</span><span class="sxs-lookup"><span data-stu-id="3b342-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="3b342-179">Se o número máximo de chamadas for definido como 0, a mensagem de saudação não será reproduzida.</span><span class="sxs-lookup"><span data-stu-id="3b342-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="3b342-180">Tratamento de tempo limite de chamada</span><span class="sxs-lookup"><span data-stu-id="3b342-180">Call timeout handling</span></span>

![Captura de tela das configurações de tempo limite de chamada](media/call-queue-timeout-handling.png)

<span data-ttu-id="3b342-182">Tempo **limite de chamada: o tempo de espera máximo** especifica o tempo máximo que uma chamada pode estar em espera na fila antes de ser redirecionada ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="3b342-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="3b342-183">Você pode especificar um valor entre 0 segundo e 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="3b342-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="3b342-184">Você pode optar por desconectar a chamada ou redirecioná-la para um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b342-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="3b342-185">Por exemplo, você pode ter o chamador deixar um correio de voz para os agentes na fila.</span><span class="sxs-lookup"><span data-stu-id="3b342-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="3b342-186">Para transferências externas, consulte [pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) e as [transferências de número de telefone externo-detalhes técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) de formatação de números.</span><span class="sxs-lookup"><span data-stu-id="3b342-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="3b342-187">Depois de selecionar as opções de tempo limite de uma chamada, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="3b342-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="3b342-188">IDENTIFICAÇÃO de chamada para chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="3b342-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="3b342-189">Como os agentes em uma fila de chamadas podem discar para retornar uma chamada de cliente, considere definir a identificação de chamadas para membros de uma fila de chamadas para o número de serviço de um atendedor automático apropriado.</span><span class="sxs-lookup"><span data-stu-id="3b342-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="3b342-190">Consulte [gerenciar políticas de identificação de chamadas no Microsoft Teams](caller-id-policies.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3b342-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="3b342-191">Clientes com suporte</span><span class="sxs-lookup"><span data-stu-id="3b342-191">Supported clients</span></span>

<span data-ttu-id="3b342-192">Os seguintes clientes têm suporte para agentes de chamada em uma fila de chamadas:</span><span class="sxs-lookup"><span data-stu-id="3b342-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="3b342-193">Cliente de área de trabalho do Skype for Business 2016 (versões de 32 bits e de 64 bits)</span><span class="sxs-lookup"><span data-stu-id="3b342-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="3b342-194">Lync desktop cliente 2013 (versões de 32 bits e de 64 bits)</span><span class="sxs-lookup"><span data-stu-id="3b342-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="3b342-195">Todos os modelos de telefone IP com suporte para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3b342-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="3b342-196">Consulte [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="3b342-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="3b342-197">Cliente Skype for Business para Mac (versão 16.8.196 e posterior)</span><span class="sxs-lookup"><span data-stu-id="3b342-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="3b342-198">Cliente Skype for Business Android (versão 6.16.0.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="3b342-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="3b342-199">Cliente Skype for Business (versão 6.16.0 e posterior) do iPhone</span><span class="sxs-lookup"><span data-stu-id="3b342-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="3b342-200">Cliente Skype for Business para iPad (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="3b342-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="3b342-201">Microsoft Teams Windows Client (versões de 32 bits e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="3b342-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="3b342-202">Cliente Mac do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b342-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="3b342-203">Aplicativo iPhone do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b342-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="3b342-204">Aplicativo Android do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b342-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b342-205">As filas de chamadas atribuídas a um número de roteamento direto não dão suporte a clientes Skype for Business, clientes do Lync ou telefones IP do Skype for Business como agentes.</span><span class="sxs-lookup"><span data-stu-id="3b342-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="3b342-206">Cmdlets da fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="3b342-206">Call queue cmdlets</span></span>

<span data-ttu-id="3b342-207">Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b342-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="3b342-208">Estes são os cmdlets que você usa para gerenciar uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b342-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="3b342-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3b342-209">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="3b342-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3b342-210">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="3b342-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3b342-211">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="3b342-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="3b342-212">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="3b342-213">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3b342-213">Related topics</span></span>

[<span data-ttu-id="3b342-214">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="3b342-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="3b342-215">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="3b342-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="3b342-216">Disponibilidade de audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="3b342-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="3b342-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="3b342-217">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="3b342-218">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3b342-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
