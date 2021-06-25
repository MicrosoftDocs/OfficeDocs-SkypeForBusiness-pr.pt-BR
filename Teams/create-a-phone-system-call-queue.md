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
description: Saiba como configurar filas de chamada para grandes organizações no Microsoft Teams, que fornece uma mensagem de saudação, música de espera, redirecionamento de chamada e outros recursos.
ms.openlocfilehash: c07c5a42241a62f9ecfe90340cab473800469ca9
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126887"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="95d73-103">Criar uma fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="95d73-103">Create a call queue</span></span>

<span data-ttu-id="95d73-104">As filas de chamadas fornecem um método de roteamento de chamadas para as pessoas da organização que podem ajudar com um problema ou pergunta específica.</span><span class="sxs-lookup"><span data-stu-id="95d73-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="95d73-105">As chamadas são distribuídas uma por vez para as pessoas na fila (que são conhecidas como *agentes*).</span><span class="sxs-lookup"><span data-stu-id="95d73-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="95d73-106">Este artigo é para grandes organizações.</span><span class="sxs-lookup"><span data-stu-id="95d73-106">This article is for large organizations.</span></span> <span data-ttu-id="95d73-107">Se sua organização for uma pequena empresa, leia Criar uma fila [de chamada - tutorial de pequenas](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) empresas.</span><span class="sxs-lookup"><span data-stu-id="95d73-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="95d73-108">As filas de chamada fornecem:</span><span class="sxs-lookup"><span data-stu-id="95d73-108">Call queues provide:</span></span>

- <span data-ttu-id="95d73-109">Uma mensagem de saudação.</span><span class="sxs-lookup"><span data-stu-id="95d73-109">A greeting message.</span></span>

- <span data-ttu-id="95d73-110">Música enquanto as pessoas estão em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="95d73-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="95d73-111">Roteamento de chamadas, na ordem *Primeiro a Entrar, Primeiro a Sair* (PEPS), para os agentes.</span><span class="sxs-lookup"><span data-stu-id="95d73-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="95d73-112">Opções de administração para estouro da fila e tempo limite.</span><span class="sxs-lookup"><span data-stu-id="95d73-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="95d73-113">Leia Plan for Teams auto attendants and [call queues](plan-auto-attendant-call-queue.md) [](plan-auto-attendant-call-queue.md#getting-started) e siga as etapas de início antes de seguir os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="95d73-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="95d73-114">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="95d73-114">Video demonstration</span></span>

<span data-ttu-id="95d73-115">Este vídeo mostra um exemplo básico de como criar uma fila de chamada no Teams.</span><span class="sxs-lookup"><span data-stu-id="95d73-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="95d73-116">Criar a fila de chamada</span><span class="sxs-lookup"><span data-stu-id="95d73-116">Create the call queue</span></span>

<span data-ttu-id="95d73-117">Para configurar uma fila de chamadas, no Centro de administração do Teams, expanda **Voz**, clique em **Filas de chamadas** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="95d73-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

<span data-ttu-id="95d73-118">Digite um nome para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="95d73-118">Type a name for the call queue.</span></span>

### <a name="resource-accounts"></a><span data-ttu-id="95d73-119">Contas de recursos</span><span class="sxs-lookup"><span data-stu-id="95d73-119">Resource accounts</span></span>

![Captura de tela das configurações da conta de recurso](media/call-queue-name-language.png)

<span data-ttu-id="95d73-121">Clique em **Adicionar contas**, procure a conta de recurso que você deseja usar com a fila de chamadas, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="95d73-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="95d73-122">(Os agentes verão o nome da conta de recurso quando receberem uma chamada de entrada.)</span><span class="sxs-lookup"><span data-stu-id="95d73-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

### <a name="assign-calling-id"></a><span data-ttu-id="95d73-123">Atribuir ID de chamada</span><span class="sxs-lookup"><span data-stu-id="95d73-123">Assign calling ID</span></span>

![Captura de tela das configurações de ID de chamada](media/call-queue-assign-calling-id.png)

<span data-ttu-id="95d73-125">Se você planeja usar um canal Teams para seus agentes de chamada, pode atribuir um número de ID do chamador de saída para os agentes especificando uma ou mais contas de recurso com um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="95d73-125">If you plan to use a Teams channel for your call agents, you can assign an outbound caller ID number for the agents by specifying one or more resource accounts with a phone number.</span></span>

<span data-ttu-id="95d73-126">Clique **em** Adicionar , pesquise as contas de recurso que você deseja permitir que os agentes para fins de ID de chamada ao fazer chamadas de saída, clique em Adicionar **e** em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="95d73-126">Click **Add**, search for the resource accounts that you want to allow agents to for calling ID purposes when making outbound calls, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="95d73-127">Se você não estiver usando um canal Teams para controlar a associação de agentes, considere definir diretamente a ID do chamador para membros da fila de chamada para o número de serviço da fila de chamada ou o atendimento automático apropriado.</span><span class="sxs-lookup"><span data-stu-id="95d73-127">If you are not using a Teams channel to control agent membership, consider directly setting the caller ID for members of the call queue to the service number of the call queue or appropriate auto attendant.</span></span> <span data-ttu-id="95d73-128">Para mais informações, confira [Gerenciar políticas de identificação de chamadas no Microsoft Teams](caller-id-policies.md).</span><span class="sxs-lookup"><span data-stu-id="95d73-128">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

### <a name="language"></a><span data-ttu-id="95d73-129">Linguagem</span><span class="sxs-lookup"><span data-stu-id="95d73-129">Language</span></span>

![Captura de tela das configurações de idioma](media/call-queue-language.png)

<span data-ttu-id="95d73-131">Escolha um [idioma com suporte](create-a-phone-system-call-queue-languages.md).</span><span class="sxs-lookup"><span data-stu-id="95d73-131">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="95d73-132">Esse idioma será usado para comandos de voz gerados pelo sistema e para a transcrição da caixa postal (se habilitados).</span><span class="sxs-lookup"><span data-stu-id="95d73-132">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

### <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="95d73-133">Saudações e música de espera na fila</span><span class="sxs-lookup"><span data-stu-id="95d73-133">Greetings and music on hold in queue</span></span>

![Captura de tela de saudações e música em espera nas configurações de fila](media/call-queue-greetings-music.png)

<span data-ttu-id="95d73-135">Especifique se você deseja reproduzir uma saudação aos chamadores quando eles chegarem na fila.</span><span class="sxs-lookup"><span data-stu-id="95d73-135">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="95d73-136">Carregue um arquivo MP3, WAV ou WMA contendo a saudação que deseja reproduzir.</span><span class="sxs-lookup"><span data-stu-id="95d73-136">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="95d73-137">O Teams fornece música padrão aos chamadores enquanto eles estão em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="95d73-137">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="95d73-138">Se você quiser reproduzir um arquivo de áudio específico, escolha **Reproduzir um arquivo de áudio** e carregue um arquivo MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="95d73-138">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="95d73-139">A gravação carregada não pode ser maior do que 5 MB.</span><span class="sxs-lookup"><span data-stu-id="95d73-139">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="95d73-140">A música padrão fornecida nas filas de chamadas do Teams é livre de royalties pagáveis pela organização.</span><span class="sxs-lookup"><span data-stu-id="95d73-140">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

### <a name="call-agents"></a><span data-ttu-id="95d73-141">Agentes de chamada</span><span class="sxs-lookup"><span data-stu-id="95d73-141">Call agents</span></span>

<span data-ttu-id="95d73-142">Revise os [pré-requisitos para adicionar agentes a uma fila de chamada.](plan-auto-attendant-call-queue.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="95d73-142">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Captura de tela das configurações de usuários e grupos para filas de chamada](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="95d73-144">Teams canal</span><span class="sxs-lookup"><span data-stu-id="95d73-144">Teams channel</span></span>

<span data-ttu-id="95d73-145">Você pode adicionar até 200 agentes por meio de um Teams canal.</span><span class="sxs-lookup"><span data-stu-id="95d73-145">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="95d73-146">Se você quiser usar [um canal Teams para gerenciar](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)a fila, selecione a opção Escolher uma **equipe** e clique em Adicionar **um canal**.</span><span class="sxs-lookup"><span data-stu-id="95d73-146">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="95d73-147">Pesquise a equipe que você deseja usar, selecione-a e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="95d73-147">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="95d73-148">Selecione o canal que você deseja usar e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="95d73-148">Select the channel that you want to use and click **Apply**.</span></span> <span data-ttu-id="95d73-149">Você deve ser membro da equipe ou criador ou proprietário do canal.</span><span class="sxs-lookup"><span data-stu-id="95d73-149">You must be a member of the team or the creator of or an owner of the channel.</span></span>

<span data-ttu-id="95d73-150">Os seguintes clientes são suportados ao usar um canal Teams para filas de chamada:</span><span class="sxs-lookup"><span data-stu-id="95d73-150">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="95d73-151">Microsoft Teams Windows cliente</span><span class="sxs-lookup"><span data-stu-id="95d73-151">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="95d73-152">Cliente Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="95d73-152">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="95d73-153">Usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="95d73-153">Users and groups</span></span>

<span data-ttu-id="95d73-154">Você pode adicionar até 20 agentes individualmente e até 200 agentes por meio de grupos.</span><span class="sxs-lookup"><span data-stu-id="95d73-154">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="95d73-155">Se você quiser adicionar usuários ou grupos individuais à fila, selecione a **opção Escolher usuários e grupos.**</span><span class="sxs-lookup"><span data-stu-id="95d73-155">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="95d73-156">Para adicionar um usuário à fila, clique em **Adicionar usuários**, procure o usuário, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="95d73-156">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="95d73-157">Para adicionar um grupo à fila, clique em **Adicionar grupos**, procure o grupo, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="95d73-157">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="95d73-158">Use listas de distribuição, grupos de segurança, grupos do Microsoft 365 ou equipes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="95d73-158">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="95d73-159">Os novos usuários adicionados a um grupo podem levar até oito horas para receberem a sua primeira chamada.</span><span class="sxs-lookup"><span data-stu-id="95d73-159">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

### <a name="call-routing"></a><span data-ttu-id="95d73-160">Roteamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="95d73-160">Call routing</span></span>

![Captura de tela das configurações de método de roteamento e modo de conferência](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="95d73-162">O **Modo de conferência** reduz significativamente o tempo necessário para que um chamador seja conectado a um agente, depois que o agente aceita a chamada.</span><span class="sxs-lookup"><span data-stu-id="95d73-162">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="95d73-163">Para que o modo de conferência funcione, os agentes na fila de chamada devem usar um dos seguintes clientes:</span><span class="sxs-lookup"><span data-stu-id="95d73-163">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="95d73-164">A versão mais recente do cliente de área de trabalho do Microsoft Teams, do aplicativo Android ou do aplicativo iOS</span><span class="sxs-lookup"><span data-stu-id="95d73-164">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="95d73-165">Versão de telefone do Microsoft Teams 1449/1.0.94.2020051601 ou posterior</span><span class="sxs-lookup"><span data-stu-id="95d73-165">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="95d73-166">As contas do Teams dos agentes precisam ser definidas para o modo apenas Teams.</span><span class="sxs-lookup"><span data-stu-id="95d73-166">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="95d73-167">Os agentes que não atendem aos requisitos não são incluídos na lista de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="95d73-167">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="95d73-168">É recomendável habilitar o modo de conferência para suas filas de chamadas se todos os agentes estiverem usando clientes compatíveis.</span><span class="sxs-lookup"><span data-stu-id="95d73-168">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="95d73-169">O modo de conferência não será suportado se as chamadas telefônicas são roteadas para a fila de um gateway de Roteamento Direto habilitado para Roteamento Baseado em Local.</span><span class="sxs-lookup"><span data-stu-id="95d73-169">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="95d73-170">O **método de roteamento** determina a ordem na qual os agentes recebem chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="95d73-170">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="95d73-171">Escolha uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="95d73-171">Choose from these options:</span></span>

- <span data-ttu-id="95d73-172">O **Roteamento de atendedor** chama todos os agentes na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="95d73-172">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="95d73-173">O primeiro agente de chamada que atender recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="95d73-173">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="95d73-174">O **Roteamento em série** chama todos os agentes de chamada, um por um, na ordem especificada na **lista de agentes de chamada**.</span><span class="sxs-lookup"><span data-stu-id="95d73-174">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="95d73-175">Se um agente ignora ou não atende uma chamada, ela tocará para o próximo agente e tentará com todos os agentes até que seja atendida ou atinja o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="95d73-175">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="95d73-176">O **Round robin** equilibra o roteamento das chamadas de entrada para que cada agente de chamada receba o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="95d73-176">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="95d73-177">Isso pode ser desejável em um ambiente de vendas de entrada para garantir igualdade de oportunidades entre todos os agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="95d73-177">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="95d73-178">O **Ocioso por mais tempo** encaminha cada chamada para o agente que está ocioso há mais tempo.</span><span class="sxs-lookup"><span data-stu-id="95d73-178">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="95d73-179">Um agente é considerado ocioso se seu estado de presença estiver Disponível ou se o estado de presença estiver Ausente por menos de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="95d73-179">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="95d73-180">Os agentes cujo estado de presença esteja ausente há mais de 10 minutos não são considerados ociosos e não poderão receber chamadas até que alterem a presença para Disponível.</span><span class="sxs-lookup"><span data-stu-id="95d73-180">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Captura de tela das configurações de roteamento, recusa e tempo de alerta](media/call-queue-presence-agents-time.png)

<span data-ttu-id="95d73-182">O **Roteamento baseado em presença** usa o status de disponibilidade dos agentes de chamada para determinar se um agente deve ser incluído na lista de roteamento de chamadas para o método de roteamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="95d73-182">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="95d73-183">Os agentes de chamada cujo status de disponibilidade está definido como **Disponível**, estão incluídos na lista de roteamento de chamadas e podem receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="95d73-183">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="95d73-184">Os agentes cujo status de disponibilidade está definido com qualquer outro status, são excluídos da lista de roteamento de chamadas e não receberão chamadas até que seu status de disponibilidade volte para **Disponível**.</span><span class="sxs-lookup"><span data-stu-id="95d73-184">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="95d73-185">Habilite o roteamento de chamadas baseado em presença com qualquer um dos métodos de roteamento.</span><span class="sxs-lookup"><span data-stu-id="95d73-185">You can enable presence-based call routing with any of the routing methods.</span></span>

> [!NOTE]
> <span data-ttu-id="95d73-186">Quando **ocioso** mais longo é selecionado como o método de roteamento, o roteamento  baseado em presença é necessário e automaticamente habilitado, mesmo que a alternância de roteamento baseada em presença seja desligada e acinzenada.</span><span class="sxs-lookup"><span data-stu-id="95d73-186">When **Longest idle** is selected as the routing method, presence-based routing is required and automatically enabled even though the Presence-based routing toggle will be **Off** and grayed out.</span></span>

<span data-ttu-id="95d73-187">Se um agente optar por não receber chamadas, ele não será incluído na lista de roteamento de chamadas, independentemente do status de disponibilidade definido.</span><span class="sxs-lookup"><span data-stu-id="95d73-187">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="95d73-188">Os agentes que usam o cliente do Skype for Business não são incluídos na lista de roteamento de chamadas quando o roteamento baseado em presença está habilitado.</span><span class="sxs-lookup"><span data-stu-id="95d73-188">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="95d73-189">Se você tiver agentes que usam o Skype for Business, não habilite o roteamento de chamadas baseado em presença.</span><span class="sxs-lookup"><span data-stu-id="95d73-189">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="95d73-190">O **Tempo de alerta do agente** especifica por quanto tempo o telefone de um agente tocará antes que a fila redirecione a chamada para o próximo agente.</span><span class="sxs-lookup"><span data-stu-id="95d73-190">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="95d73-191">As seguintes configurações são recomendadas:</span><span class="sxs-lookup"><span data-stu-id="95d73-191">The following settings are recommended:</span></span>

- <span data-ttu-id="95d73-192">**Modo de conferência** para **Automático**</span><span class="sxs-lookup"><span data-stu-id="95d73-192">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="95d73-193">**Método de roteamento** para **Round robin** ou **Ocioso por mais tempo**</span><span class="sxs-lookup"><span data-stu-id="95d73-193">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="95d73-194">**Roteamento baseado em presença** para **Ativado**</span><span class="sxs-lookup"><span data-stu-id="95d73-194">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="95d73-195">**Tempo de alerta do agente:** para **20 segundos**</span><span class="sxs-lookup"><span data-stu-id="95d73-195">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="95d73-196">Se o roteamento baseado em presença não for habilitado e houver várias chamadas na fila, o sistema apresentará essas chamadas simultaneamente aos agentes, independentemente do status de presença.</span><span class="sxs-lookup"><span data-stu-id="95d73-196">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="95d73-197">Isso resultará em várias notificações de chamada aos agentes, particularmente se alguns agentes não atenderem à chamada inicial apresentada.</span><span class="sxs-lookup"><span data-stu-id="95d73-197">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

### <a name="call-overflow-handling"></a><span data-ttu-id="95d73-198">Administração de estouro de chamadas</span><span class="sxs-lookup"><span data-stu-id="95d73-198">Call overflow handling</span></span>

![Captura de tela das configurações de estouro de chamadas](media/call-queue-overflow-handling.png)

<span data-ttu-id="95d73-200">O **Número máximo de chamadas na fila** especifica o número máximo de chamadas que podem esperar na fila a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="95d73-200">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="95d73-201">O padrão é 50, mas pode variar de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="95d73-201">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="95d73-202">Quando o limite é atingido, a chamada é tratada como especificado pela configuração **Quando é atingido o número máximo de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="95d73-202">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="95d73-203">Você pode optar por desconectar a chamada ou redirecioná-la para qualquer um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="95d73-203">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="95d73-204">Por exemplo, você pode pedir ao chamador que deixe uma mensagem de voz para os agentes na fila.</span><span class="sxs-lookup"><span data-stu-id="95d73-204">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="95d73-205">Para transferências externas, consulte [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) e [transferências de números de telefone externos – detalhes técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para formatação de números.</span><span class="sxs-lookup"><span data-stu-id="95d73-205">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="95d73-206">Se o número máximo de chamadas for definido como 0, então a mensagem de saudação não será reproduzida.</span><span class="sxs-lookup"><span data-stu-id="95d73-206">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

### <a name="call-timeout-handling"></a><span data-ttu-id="95d73-207">Administração de tempo limite de chamada</span><span class="sxs-lookup"><span data-stu-id="95d73-207">Call timeout handling</span></span>

![Captura de tela das configurações de tempo limite de chamada](media/call-queue-timeout-handling.png)

<span data-ttu-id="95d73-209">**Tempo limite de chamada: o tempo máximo de espera** especifica o tempo máximo que uma chamada pode estar em espera na fila antes de ser redirecionada ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="95d73-209">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="95d73-210">É possível especificar um valor de 0 segundos a 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="95d73-210">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="95d73-211">Você pode optar por desconectar a chamada ou redirecioná-la para um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="95d73-211">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="95d73-212">Por exemplo, você pode pedir ao chamador que deixe uma mensagem de voz para os agentes na fila.</span><span class="sxs-lookup"><span data-stu-id="95d73-212">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="95d73-213">Para transferências externas, consulte [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) e [transferências de números de telefone externos – detalhes técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para formatação de números.</span><span class="sxs-lookup"><span data-stu-id="95d73-213">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="95d73-214">Quando você tiver selecionado as opções de tempo limite de chamada, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="95d73-214">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="95d73-215">Clientes com suporte</span><span class="sxs-lookup"><span data-stu-id="95d73-215">Supported clients</span></span>

<span data-ttu-id="95d73-216">Os clientes a seguir têm suporte para agentes de chamada em uma fila de chamada:</span><span class="sxs-lookup"><span data-stu-id="95d73-216">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="95d73-217">Cliente de área de trabalho do Skype for Business 2016 (versões 32-bit e 64-bit)</span><span class="sxs-lookup"><span data-stu-id="95d73-217">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="95d73-218">Cliente de área de trabalho do Lync 2013 (versões 32-bit e 64-bit)</span><span class="sxs-lookup"><span data-stu-id="95d73-218">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="95d73-219">Todos os modelos de telefone IP com suporte para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="95d73-219">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="95d73-220">Confira [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="95d73-220">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="95d73-221">Cliente Skype for Business para Mac (versão 16.8.196 e posterior)</span><span class="sxs-lookup"><span data-stu-id="95d73-221">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="95d73-222">Cliente Skype for Business para Android (versão 6.16.0.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="95d73-222">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="95d73-223">Cliente Skype for Business para iPhone (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="95d73-223">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="95d73-224">Cliente Skype for Business para iPad (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="95d73-224">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="95d73-225">Cliente Microsoft Teams para Windows (versões 32-bit e 64-bit)</span><span class="sxs-lookup"><span data-stu-id="95d73-225">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="95d73-226">Cliente Microsoft Teams para Mac</span><span class="sxs-lookup"><span data-stu-id="95d73-226">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="95d73-227">Microsoft Teams infraestrutura [de área de trabalho virtualizada](/microsoftteams/teams-for-vdi) (Windows área de trabalho virtual, Citrix e VMware)</span><span class="sxs-lookup"><span data-stu-id="95d73-227">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="95d73-228">Aplicativo Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="95d73-228">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="95d73-229">Aplicativo Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="95d73-229">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="95d73-230">As filas de chamadas que recebem um número de roteamento direto não têm suporte para clientes Skype for Business, clientes Lync ou para Telefones IP do Skype for Business como agentes.</span><span class="sxs-lookup"><span data-stu-id="95d73-230">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="95d73-231">Cmdlets de fila de chamada</span><span class="sxs-lookup"><span data-stu-id="95d73-231">Call queue cmdlets</span></span>

<span data-ttu-id="95d73-232">Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="95d73-232">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="95d73-233">Veja aqui os cmdlets usados para administrar uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="95d73-233">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="95d73-234">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="95d73-234">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="95d73-235">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="95d73-235">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="95d73-236">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="95d73-236">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="95d73-237">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="95d73-237">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="95d73-238">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="95d73-238">Related topics</span></span>

[<span data-ttu-id="95d73-239">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="95d73-239">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="95d73-240">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="95d73-240">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="95d73-241">Disponibilidade de Audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="95d73-241">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="95d73-242">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="95d73-242">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="95d73-243">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95d73-243">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
