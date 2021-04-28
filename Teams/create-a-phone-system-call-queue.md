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
description: Saiba como configurar o Sistema de Telefonia para filas de chamadas com o Microsoft Teams, que fornece uma mensagem de saudação, música de espera, redirecionamento de chamadas e outros recursos.
ms.openlocfilehash: 8b4fe4283ac9734c1dc29bf33759039098578744
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064797"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="c74ef-103">Criar uma fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="c74ef-103">Create a call queue</span></span>

<span data-ttu-id="c74ef-104">As filas de chamadas fornecem um método de roteamento de chamadas para as pessoas da organização que podem ajudar com um problema ou pergunta específica.</span><span class="sxs-lookup"><span data-stu-id="c74ef-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="c74ef-105">As chamadas são distribuídas uma por vez para as pessoas na fila (que são conhecidas como *agentes*).</span><span class="sxs-lookup"><span data-stu-id="c74ef-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="c74ef-106">As filas de chamada fornecem:</span><span class="sxs-lookup"><span data-stu-id="c74ef-106">Call queues provide:</span></span>

- <span data-ttu-id="c74ef-107">Uma mensagem de saudação.</span><span class="sxs-lookup"><span data-stu-id="c74ef-107">A greeting message.</span></span>

- <span data-ttu-id="c74ef-108">Música enquanto as pessoas estão em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="c74ef-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="c74ef-109">Roteamento de chamadas, na ordem *Primeiro a Entrar, Primeiro a Sair* (PEPS), para os agentes.</span><span class="sxs-lookup"><span data-stu-id="c74ef-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="c74ef-110">Opções de administração para estouro da fila e tempo limite.</span><span class="sxs-lookup"><span data-stu-id="c74ef-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="c74ef-111">Certifique-se de ter lido [Plan for Teams auto attendants](plan-auto-attendant-call-queue.md) and call queues and followed the getting started [steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span><span class="sxs-lookup"><span data-stu-id="c74ef-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="c74ef-112">Para configurar uma fila de chamadas, no Centro de administração do Teams, expanda **Voz**, clique em **Filas de chamadas** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="c74ef-113">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="c74ef-113">Video demonstration</span></span>

<span data-ttu-id="c74ef-114">Este vídeo mostra um exemplo básico de como criar uma fila de chamada no Teams.</span><span class="sxs-lookup"><span data-stu-id="c74ef-114">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="resource-account-and-language"></a><span data-ttu-id="c74ef-115">Idioma e conta de recurso</span><span class="sxs-lookup"><span data-stu-id="c74ef-115">Resource account and language</span></span>

![Captura de tela das configurações de idioma e da conta de recurso](media/call-queue-name-language.png)

1. <span data-ttu-id="c74ef-117">Digite um nome para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c74ef-117">Type a name for the call queue.</span></span>

2. <span data-ttu-id="c74ef-118">Clique em **Adicionar contas**, procure a conta de recurso que você deseja usar com a fila de chamadas, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-118">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="c74ef-119">(Os agentes verão o nome da conta de recurso quando receberem uma chamada de entrada.)</span><span class="sxs-lookup"><span data-stu-id="c74ef-119">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="c74ef-120">Escolha um [idioma com suporte](create-a-phone-system-call-queue-languages.md).</span><span class="sxs-lookup"><span data-stu-id="c74ef-120">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="c74ef-121">Esse idioma será usado para comandos de voz gerados pelo sistema e para a transcrição da caixa postal (se habilitados).</span><span class="sxs-lookup"><span data-stu-id="c74ef-121">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="c74ef-122">Saudações e música de espera na fila</span><span class="sxs-lookup"><span data-stu-id="c74ef-122">Greetings and music on hold in queue</span></span>

<span data-ttu-id="c74ef-123">Especifique se você deseja reproduzir uma saudação aos chamadores quando eles chegarem na fila.</span><span class="sxs-lookup"><span data-stu-id="c74ef-123">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="c74ef-124">Carregue um arquivo MP3, WAV ou WMA contendo a saudação que deseja reproduzir.</span><span class="sxs-lookup"><span data-stu-id="c74ef-124">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="c74ef-125">O Teams fornece música padrão aos chamadores enquanto eles estão em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="c74ef-125">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="c74ef-126">Se você quiser reproduzir um arquivo de áudio específico, escolha **Reproduzir um arquivo de áudio** e carregue um arquivo MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="c74ef-126">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="c74ef-127">A gravação carregada não pode ser maior do que 5 MB.</span><span class="sxs-lookup"><span data-stu-id="c74ef-127">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="c74ef-128">A música padrão fornecida nas filas de chamadas do Teams é livre de royalties pagáveis pela organização.</span><span class="sxs-lookup"><span data-stu-id="c74ef-128">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="c74ef-129">Agentes de chamada</span><span class="sxs-lookup"><span data-stu-id="c74ef-129">Call agents</span></span>

<span data-ttu-id="c74ef-130">Revise os [pré-requisitos para adicionar agentes a uma fila de chamada.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="c74ef-130">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Captura de tela das configurações de usuários e grupos para filas de chamada](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="c74ef-132">Canal do Teams</span><span class="sxs-lookup"><span data-stu-id="c74ef-132">Teams channel</span></span>

<span data-ttu-id="c74ef-133">Você pode adicionar até 200 agentes por meio de um canal do Teams.</span><span class="sxs-lookup"><span data-stu-id="c74ef-133">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="c74ef-134">Se você quiser usar [um canal do Teams](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)para gerenciar a fila, selecione a opção Escolher uma **equipe** e clique em Adicionar **um canal**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-134">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="c74ef-135">Pesquise a equipe que você deseja usar, selecione-a e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-135">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="c74ef-136">Selecione o canal que você deseja usar e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-136">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="c74ef-137">Os seguintes clientes são suportados ao usar um canal do Teams para filas de chamada:</span><span class="sxs-lookup"><span data-stu-id="c74ef-137">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="c74ef-138">Cliente Microsoft Teams Windows</span><span class="sxs-lookup"><span data-stu-id="c74ef-138">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="c74ef-139">Cliente Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="c74ef-139">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="c74ef-140">Usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="c74ef-140">Users and groups</span></span>

<span data-ttu-id="c74ef-141">Você pode adicionar até 20 agentes individualmente e até 200 agentes por meio de grupos.</span><span class="sxs-lookup"><span data-stu-id="c74ef-141">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="c74ef-142">Se você quiser adicionar usuários ou grupos individuais à fila, selecione a **opção Escolher usuários e grupos.**</span><span class="sxs-lookup"><span data-stu-id="c74ef-142">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="c74ef-143">Para adicionar um usuário à fila, clique em **Adicionar usuários**, procure o usuário, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-143">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="c74ef-144">Para adicionar um grupo à fila, clique em **Adicionar grupos**, procure o grupo, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-144">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="c74ef-145">Use listas de distribuição, grupos de segurança, grupos do Microsoft 365 ou equipes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c74ef-145">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="c74ef-146">Os novos usuários adicionados a um grupo podem levar até oito horas para receberem a sua primeira chamada.</span><span class="sxs-lookup"><span data-stu-id="c74ef-146">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="c74ef-147">Roteamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="c74ef-147">Call routing</span></span>

![Captura de tela das configurações de método de roteamento e modo de conferência](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="c74ef-149">O **Modo de conferência** reduz significativamente o tempo necessário para que um chamador seja conectado a um agente, depois que o agente aceita a chamada.</span><span class="sxs-lookup"><span data-stu-id="c74ef-149">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="c74ef-150">Para que o modo de conferência funcione, os agentes na fila de chamada devem usar um dos seguintes clientes:</span><span class="sxs-lookup"><span data-stu-id="c74ef-150">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="c74ef-151">A versão mais recente do cliente de área de trabalho do Microsoft Teams, do aplicativo Android ou do aplicativo iOS</span><span class="sxs-lookup"><span data-stu-id="c74ef-151">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="c74ef-152">Versão de telefone do Microsoft Teams 1449/1.0.94.2020051601 ou posterior</span><span class="sxs-lookup"><span data-stu-id="c74ef-152">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="c74ef-153">As contas do Teams dos agentes precisam ser definidas para o modo apenas Teams.</span><span class="sxs-lookup"><span data-stu-id="c74ef-153">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="c74ef-154">Os agentes que não atendem aos requisitos não são incluídos na lista de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c74ef-154">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="c74ef-155">É recomendável habilitar o modo de conferência para suas filas de chamadas se todos os agentes estiverem usando clientes compatíveis.</span><span class="sxs-lookup"><span data-stu-id="c74ef-155">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="c74ef-156">O modo de conferência não será suportado se as chamadas telefônicas são roteadas para a fila de um gateway de Roteamento Direto habilitado para Roteamento Baseado em Local.</span><span class="sxs-lookup"><span data-stu-id="c74ef-156">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="c74ef-157">O **método de roteamento** determina a ordem na qual os agentes recebem chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="c74ef-157">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="c74ef-158">Escolha uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="c74ef-158">Choose from these options:</span></span>

- <span data-ttu-id="c74ef-159">O **Roteamento de atendedor** chama todos os agentes na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c74ef-159">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="c74ef-160">O primeiro agente de chamada que atender recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="c74ef-160">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="c74ef-161">O **Roteamento em série** chama todos os agentes de chamada, um por um, na ordem especificada na **lista de agentes de chamada**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-161">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="c74ef-162">Se um agente ignora ou não atende uma chamada, ela tocará para o próximo agente e tentará com todos os agentes até que seja atendida ou atinja o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="c74ef-162">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="c74ef-163">O **Round robin** equilibra o roteamento das chamadas de entrada para que cada agente de chamada receba o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="c74ef-163">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="c74ef-164">Isso pode ser desejável em um ambiente de vendas de entrada para garantir igualdade de oportunidades entre todos os agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="c74ef-164">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="c74ef-165">O **Ocioso por mais tempo** encaminha cada chamada para o agente que está ocioso há mais tempo.</span><span class="sxs-lookup"><span data-stu-id="c74ef-165">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="c74ef-166">Um agente é considerado ocioso se seu estado de presença estiver Disponível ou se o estado de presença estiver Ausente por menos de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="c74ef-166">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="c74ef-167">Os agentes cujo estado de presença esteja ausente há mais de 10 minutos não são considerados ociosos e não poderão receber chamadas até que alterem a presença para Disponível.</span><span class="sxs-lookup"><span data-stu-id="c74ef-167">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Captura de tela das configurações de roteamento, recusa e tempo de alerta](media/call-queue-presence-agents-time.png)


<span data-ttu-id="c74ef-169">O **Roteamento baseado em presença** usa o status de disponibilidade dos agentes de chamada para determinar se um agente deve ser incluído na lista de roteamento de chamadas para o método de roteamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="c74ef-169">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="c74ef-170">Os agentes de chamada cujo status de disponibilidade está definido como **Disponível**, estão incluídos na lista de roteamento de chamadas e podem receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="c74ef-170">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="c74ef-171">Os agentes cujo status de disponibilidade está definido com qualquer outro status, são excluídos da lista de roteamento de chamadas e não receberão chamadas até que seu status de disponibilidade volte para **Disponível**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-171">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="c74ef-172">Habilite o roteamento de chamadas baseado em presença com qualquer um dos métodos de roteamento.</span><span class="sxs-lookup"><span data-stu-id="c74ef-172">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="c74ef-173">Se um agente optar por não receber chamadas, ele não será incluído na lista de roteamento de chamadas, independentemente do status de disponibilidade definido.</span><span class="sxs-lookup"><span data-stu-id="c74ef-173">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="c74ef-174">Os agentes que usam o cliente do Skype for Business não são incluídos na lista de roteamento de chamadas quando o roteamento baseado em presença está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c74ef-174">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="c74ef-175">Se você tiver agentes que usam o Skype for Business, não habilite o roteamento de chamadas baseado em presença.</span><span class="sxs-lookup"><span data-stu-id="c74ef-175">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="c74ef-176">O **Tempo de alerta do agente** especifica por quanto tempo o telefone de um agente tocará antes que a fila redirecione a chamada para o próximo agente.</span><span class="sxs-lookup"><span data-stu-id="c74ef-176">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="c74ef-177">As seguintes configurações são recomendadas:</span><span class="sxs-lookup"><span data-stu-id="c74ef-177">The following settings are recommended:</span></span>

- <span data-ttu-id="c74ef-178">**Modo de conferência** para **Automático**</span><span class="sxs-lookup"><span data-stu-id="c74ef-178">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="c74ef-179">**Método de roteamento** para **Round robin** ou **Ocioso por mais tempo**</span><span class="sxs-lookup"><span data-stu-id="c74ef-179">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="c74ef-180">**Roteamento baseado em presença** para **Ativado**</span><span class="sxs-lookup"><span data-stu-id="c74ef-180">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="c74ef-181">**Tempo de alerta do agente:** para **20 segundos**</span><span class="sxs-lookup"><span data-stu-id="c74ef-181">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="c74ef-182">Se o roteamento baseado em presença não for habilitado e houver várias chamadas na fila, o sistema apresentará essas chamadas simultaneamente aos agentes, independentemente do status de presença.</span><span class="sxs-lookup"><span data-stu-id="c74ef-182">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="c74ef-183">Isso resultará em várias notificações de chamada aos agentes, particularmente se alguns agentes não atenderem à chamada inicial apresentada.</span><span class="sxs-lookup"><span data-stu-id="c74ef-183">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="c74ef-184">Administração de estouro de chamadas</span><span class="sxs-lookup"><span data-stu-id="c74ef-184">Call overflow handling</span></span>

![Captura de tela das configurações de estouro de chamadas](media/call-queue-overflow-handling.png)

<span data-ttu-id="c74ef-186">O **Número máximo de chamadas na fila** especifica o número máximo de chamadas que podem esperar na fila a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="c74ef-186">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="c74ef-187">O padrão é 50, mas pode variar de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="c74ef-187">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="c74ef-188">Quando o limite é atingido, a chamada é tratada como especificado pela configuração **Quando é atingido o número máximo de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-188">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="c74ef-189">Você pode optar por desconectar a chamada ou redirecioná-la para qualquer um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c74ef-189">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="c74ef-190">Por exemplo, você pode pedir ao chamador que deixe uma mensagem de voz para os agentes na fila.</span><span class="sxs-lookup"><span data-stu-id="c74ef-190">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="c74ef-191">Para transferências externas, consulte [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) e [transferências de números de telefone externos – detalhes técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para formatação de números.</span><span class="sxs-lookup"><span data-stu-id="c74ef-191">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="c74ef-192">Se o número máximo de chamadas for definido como 0, então a mensagem de saudação não será reproduzida.</span><span class="sxs-lookup"><span data-stu-id="c74ef-192">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="c74ef-193">Administração de tempo limite de chamada</span><span class="sxs-lookup"><span data-stu-id="c74ef-193">Call timeout handling</span></span>

![Captura de tela das configurações de tempo limite de chamada](media/call-queue-timeout-handling.png)

<span data-ttu-id="c74ef-195">**Tempo limite de chamada: o tempo máximo de espera** especifica o tempo máximo que uma chamada pode estar em espera na fila antes de ser redirecionada ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="c74ef-195">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="c74ef-196">É possível especificar um valor de 0 segundos a 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="c74ef-196">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="c74ef-197">Você pode optar por desconectar a chamada ou redirecioná-la para um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c74ef-197">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="c74ef-198">Por exemplo, você pode pedir ao chamador que deixe uma mensagem de voz para os agentes na fila.</span><span class="sxs-lookup"><span data-stu-id="c74ef-198">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="c74ef-199">Para transferências externas, consulte [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) e [transferências de números de telefone externos – detalhes técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para formatação de números.</span><span class="sxs-lookup"><span data-stu-id="c74ef-199">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="c74ef-200">Quando você tiver selecionado as opções de tempo limite de chamada, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c74ef-200">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="c74ef-201">Identificação de Chamadas para chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="c74ef-201">Caller ID for outbound calls</span></span>

<span data-ttu-id="c74ef-202">Como os agentes em uma fila de chamadas podem discar para retornar uma chamada do cliente, considere configurar a identificação de chamadas dos membros de uma fila de chamadas para o número de serviço de um atendedor automático apropriado.</span><span class="sxs-lookup"><span data-stu-id="c74ef-202">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="c74ef-203">Para mais informações, confira [Gerenciar políticas de identificação de chamadas no Microsoft Teams](caller-id-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c74ef-203">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="c74ef-204">Clientes com suporte</span><span class="sxs-lookup"><span data-stu-id="c74ef-204">Supported clients</span></span>

<span data-ttu-id="c74ef-205">Os clientes a seguir têm suporte para agentes de chamada em uma fila de chamada:</span><span class="sxs-lookup"><span data-stu-id="c74ef-205">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="c74ef-206">Cliente de área de trabalho do Skype for Business 2016 (versões 32-bit e 64-bit)</span><span class="sxs-lookup"><span data-stu-id="c74ef-206">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c74ef-207">Cliente de área de trabalho do Lync 2013 (versões 32-bit e 64-bit)</span><span class="sxs-lookup"><span data-stu-id="c74ef-207">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c74ef-208">Todos os modelos de telefone IP com suporte para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c74ef-208">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="c74ef-209">Confira [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="c74ef-209">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="c74ef-210">Cliente Skype for Business para Mac (versão 16.8.196 e posterior)</span><span class="sxs-lookup"><span data-stu-id="c74ef-210">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="c74ef-211">Cliente Skype for Business para Android (versão 6.16.0.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="c74ef-211">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="c74ef-212">Cliente Skype for Business para iPhone (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="c74ef-212">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="c74ef-213">Cliente Skype for Business para iPad (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="c74ef-213">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="c74ef-214">Cliente Microsoft Teams para Windows (versões 32-bit e 64-bit)</span><span class="sxs-lookup"><span data-stu-id="c74ef-214">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c74ef-215">Cliente Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="c74ef-215">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="c74ef-216">Microsoft Teams na [Infraestrutura de Área de Trabalho Virtualizada](/microsoftteams/teams-for-vdi) (Área de Trabalho Virtual do Windows, Citrix e VMware)</span><span class="sxs-lookup"><span data-stu-id="c74ef-216">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="c74ef-217">Aplicativo Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="c74ef-217">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="c74ef-218">Aplicativo Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="c74ef-218">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="c74ef-219">As filas de chamadas que recebem um número de roteamento direto não têm suporte para clientes Skype for Business, clientes Lync ou para Telefones IP do Skype for Business como agentes.</span><span class="sxs-lookup"><span data-stu-id="c74ef-219">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="c74ef-220">Cmdlets de fila de chamada</span><span class="sxs-lookup"><span data-stu-id="c74ef-220">Call queue cmdlets</span></span>

<span data-ttu-id="c74ef-221">Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c74ef-221">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="c74ef-222">Veja aqui os cmdlets usados para administrar uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c74ef-222">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="c74ef-223">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c74ef-223">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="c74ef-224">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c74ef-224">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="c74ef-225">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c74ef-225">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="c74ef-226">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c74ef-226">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="c74ef-227">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c74ef-227">Related topics</span></span>

[<span data-ttu-id="c74ef-228">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="c74ef-228">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c74ef-229">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="c74ef-229">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="c74ef-230">Disponibilidade de Audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="c74ef-230">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="c74ef-231">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c74ef-231">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="c74ef-232">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c74ef-232">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
