---
title: Criar uma fila de chamadas no Microsoft Teams-tutorial para empresas de pequeno porte
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
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
description: Saiba como configurar filas de chamadas com o Microsoft 365 Business Voice.
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909598"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="fff10-103">Criar uma fila de chamadas-tutorial para empresas de pequeno porte</span><span class="sxs-lookup"><span data-stu-id="fff10-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="fff10-104">As filas de chamadas fornecem um método de roteamento de chamadores para as pessoas em sua organização que podem ajudá-lo com um problema ou uma pergunta específica.</span><span class="sxs-lookup"><span data-stu-id="fff10-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="fff10-105">As chamadas são distribuídas uma de cada vez para as pessoas na fila (que são conhecidas como *agentes*).</span><span class="sxs-lookup"><span data-stu-id="fff10-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="fff10-106">As filas de chamadas fornecem:</span><span class="sxs-lookup"><span data-stu-id="fff10-106">Call queues provide:</span></span>

- <span data-ttu-id="fff10-107">Uma mensagem de saudação.</span><span class="sxs-lookup"><span data-stu-id="fff10-107">A greeting message.</span></span>

- <span data-ttu-id="fff10-108">Música enquanto as pessoas estão aguardando em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="fff10-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="fff10-109">Roteamento de chamadas em *primeiro lugar, em primeiro lugar* (FIFO) para agentes.</span><span class="sxs-lookup"><span data-stu-id="fff10-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="fff10-110">Opções de manipulação para estouro de fila e tempo limite.</span><span class="sxs-lookup"><span data-stu-id="fff10-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="fff10-111">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="fff10-111">Before you begin</span></span>

<span data-ttu-id="fff10-112">Obtenha alguns [sistemas de telefonia-licenças de usuário virtual](../teams-add-on-licensing/virtual-user.md) se você ainda não tiver os mesmos.</span><span class="sxs-lookup"><span data-stu-id="fff10-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="fff10-113">Obtenha um para cada fila de chamadas e atendedor automático que você planeja configurar.</span><span class="sxs-lookup"><span data-stu-id="fff10-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="fff10-114">Essas licenças são gratuitas, portanto, sugerimos que você tenha alguns recursos adicionais para que você decida fazer alterações na sua configuração no futuro.</span><span class="sxs-lookup"><span data-stu-id="fff10-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="fff10-115">Como os agentes em uma fila de chamadas podem discar para devolver uma chamada de cliente, considere definir a identificação de chamadas para seus agentes de chamadas para o número de telefone principal ou o número de um atendedor automático apropriado.</span><span class="sxs-lookup"><span data-stu-id="fff10-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="fff10-116">Consulte [gerenciar políticas de identificação de chamadas no Microsoft Teams](../caller-id-policies.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="fff10-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="fff10-117">Siga estas etapas para configurar sua fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="fff10-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="fff10-118">Etapa 1 <br> criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="fff10-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="fff10-119">Ao criar uma fila de chamadas, você pode adicionar usuários individuais à fila ou usar um grupo de segurança existente, o grupo do Microsoft 365 ou a equipe do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fff10-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="fff10-120">Recomendamos o uso de uma equipe.</span><span class="sxs-lookup"><span data-stu-id="fff10-120">We recommend using a team.</span></span> <span data-ttu-id="fff10-121">Isso permite que os membros da fila conversem uns com os outros, Compartilhe ideias e criem documentos ou outros recursos para ajudá-los a ajudar seus clientes.</span><span class="sxs-lookup"><span data-stu-id="fff10-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="fff10-122">Uma equipe também fornece uma caixa de correio de voz para os chamadores deixarem uma mensagem após o expediente ou se a fila atingir sua capacidade máxima.</span><span class="sxs-lookup"><span data-stu-id="fff10-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="fff10-123">Para criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="fff10-123">To create a team</span></span>

1. <span data-ttu-id="fff10-124">Primeiro, clique em **equipes** no lado esquerdo do aplicativo e, em seguida, clique em **ingressar ou criar uma equipe** na parte inferior da sua lista de equipes.</span><span class="sxs-lookup"><span data-stu-id="fff10-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="fff10-125">Em seguida, clique em **criar equipe** (primeiro cartão, canto superior esquerdo).</span><span class="sxs-lookup"><span data-stu-id="fff10-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="fff10-126">Escolha **criar uma equipe a partir do zero**.</span><span class="sxs-lookup"><span data-stu-id="fff10-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="fff10-127">Em seguida, escolha se você deseja uma equipe pública ou particular.</span><span class="sxs-lookup"><span data-stu-id="fff10-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="fff10-128">Recomendamos **particular** para a sua fila de chamadas para evitar que pessoas se tornem não intencionalmente parte da fila ingressando na equipe.</span><span class="sxs-lookup"><span data-stu-id="fff10-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="fff10-129">Nomeie sua equipe e adicione uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="fff10-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="fff10-130">Quando tiver terminado, clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="fff10-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="fff10-131">Digite os nomes das pessoas que você deseja ter na fila de chamadas e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fff10-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="fff10-132">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="fff10-132">Click **Close**.</span></span> <span data-ttu-id="fff10-133">As pessoas que você adicionar a uma equipe receberão um email informando que eles são membros da sua equipe e a equipe será exibida na lista de equipes deles.</span><span class="sxs-lookup"><span data-stu-id="fff10-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fff10-134">Etapa 2-contas de recursos ></span><span class="sxs-lookup"><span data-stu-id="fff10-134">Step 2 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="fff10-135">Etapa 2 <br> contas de recursos</span><span class="sxs-lookup"><span data-stu-id="fff10-135">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="fff10-136">Cada fila de chamadas que você cria requer uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="fff10-136">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="fff10-137">Isso é semelhante a uma conta de usuário, exceto que a conta é associada a um atendedor automático ou fila de chamada em vez de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="fff10-137">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="fff10-138">Nesta etapa, criaremos a conta, atribuímos a ela um *sistema telefônico Microsoft 365-licença de usuário virtual* e, em seguida, use-a para começar a criar a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fff10-138">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="fff10-139">Criar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="fff10-139">Create a resource account</span></span>

<span data-ttu-id="fff10-140">Você pode criar uma conta de recurso no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fff10-140">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="fff10-141">No centro de administração do Teams, expanda **configurações de toda a organização** e clique em **contas de recursos**.</span><span class="sxs-lookup"><span data-stu-id="fff10-141">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="fff10-142">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fff10-142">Click **Add**.</span></span>

3. <span data-ttu-id="fff10-143">No painel **adicionar conta do recurso** , preencha o **nome para exibição**, o nome de **usuário** e escolha **fila de chamadas** para o tipo de **conta do recurso**.</span><span class="sxs-lookup"><span data-stu-id="fff10-143">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![Captura de tela da interface do usuário da conta adicionar recurso](../media/resource-account-add-cq.png)

4. <span data-ttu-id="fff10-145">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fff10-145">Click **Save**.</span></span>

<span data-ttu-id="fff10-146">A nova conta será exibida na lista de contas.</span><span class="sxs-lookup"><span data-stu-id="fff10-146">The new account will appear in the list of accounts.</span></span>

![Captura de tela de uma lista de contas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="fff10-148">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="fff10-148">Assign a license</span></span>

<span data-ttu-id="fff10-149">Você deve atribuir um *sistema telefônico Microsoft 365-licença de usuário virtual* para a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="fff10-149">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="fff10-150">No centro de administração do Microsoft 365, clique na conta de recurso à qual você deseja atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="fff10-150">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="fff10-151">Na guia **licenças e aplicativos** , em **licenças**, selecione **sistema telefônico Microsoft 365-usuário virtual**.</span><span class="sxs-lookup"><span data-stu-id="fff10-151">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="fff10-152">Clique em **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="fff10-152">Click **Save changes**.</span></span>

    ![Captura de tela da interface do usuário de atribuir licenças no centro de administração do Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="fff10-154">Criar uma fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="fff10-154">Create a call queue</span></span>

<span data-ttu-id="fff10-155">Em seguida, vamos começar a criar uma nova fila de chamadas e atribuir a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="fff10-155">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="fff10-156">No centro de administração do Teams, expanda **voz**, clique em **filas de chamadas** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fff10-156">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="fff10-157">Digite um nome para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fff10-157">Type a name for the call queue.</span></span> <span data-ttu-id="fff10-158">Os agentes verão esse nome quando receberem uma chamada de entrada da fila.</span><span class="sxs-lookup"><span data-stu-id="fff10-158">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="fff10-159">Clique em **Adicionar contas**, procure a conta de recurso que você deseja usar com esta fila de chamadas, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fff10-159">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="fff10-160">Escolha um idioma.</span><span class="sxs-lookup"><span data-stu-id="fff10-160">Choose a language.</span></span> <span data-ttu-id="fff10-161">Esse idioma será usado para solicitações de voz geradas pelo sistema e para a transcrição de correio de voz (se você habilitá-las).</span><span class="sxs-lookup"><span data-stu-id="fff10-161">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Captura de tela da conta do recurso e das configurações de idioma](../media/call-queue-name-language.png)

4. <span data-ttu-id="fff10-163">Especifique se deseja reproduzir uma saudação para os chamadores quando chegarem na fila.</span><span class="sxs-lookup"><span data-stu-id="fff10-163">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="fff10-164">Você deve carregar um arquivo MP3, WAV ou WMA contendo a saudação que deseja reproduzir.</span><span class="sxs-lookup"><span data-stu-id="fff10-164">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="fff10-165">O Teams oferece música padrão para chamadores enquanto estiverem em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="fff10-165">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="fff10-166">Se você quiser executar um arquivo de áudio específico, escolha **executar um arquivo de áudio** e carregar um arquivo MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="fff10-166">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="fff10-167">A gravação carregada não pode ter mais de 5 MB.</span><span class="sxs-lookup"><span data-stu-id="fff10-167">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="fff10-168">A música padrão fornecida nas filas de chamadas do teams é de graça dos royalties pagos por sua organização.</span><span class="sxs-lookup"><span data-stu-id="fff10-168">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="fff10-169">Etapa 3-agentes de chamada ></span><span class="sxs-lookup"><span data-stu-id="fff10-169">Step 3 - Call agents ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="fff10-170">Etapa 3 <br> agentes de chamada</span><span class="sxs-lookup"><span data-stu-id="fff10-170">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="fff10-171">Para adicionar agentes à fila de chamadas, adicionaremos a equipe que criamos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fff10-171">To add agents to the call queue, we'll add the team that we created earlier.</span></span>

1. <span data-ttu-id="fff10-172">Clique em **Adicionar grupos**.</span><span class="sxs-lookup"><span data-stu-id="fff10-172">Click **Add groups**.</span></span>
2. <span data-ttu-id="fff10-173">Digite o nome da equipe que você criou.</span><span class="sxs-lookup"><span data-stu-id="fff10-173">Type the name of the team that you created.</span></span>
3. <span data-ttu-id="fff10-174">Clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fff10-174">Click **Add**, and then click **Add**.</span></span>

    ![Captura de tela de configurações de usuários e grupos para filas de chamadas](../media/call-queue-users-groups-smb.png)

<span data-ttu-id="fff10-176">Você pode adicionar até 20 agentes individualmente e até 200 agentes via grupos ou equipes.</span><span class="sxs-lookup"><span data-stu-id="fff10-176">You can add up to 20 agents individually and up to 200 agents via groups or teams.</span></span>

> [!NOTE]
> <span data-ttu-id="fff10-177">Quando novos usuários são adicionados à equipe, pode levar até oito horas para que a primeira chamada seja recebida.</span><span class="sxs-lookup"><span data-stu-id="fff10-177">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fff10-178">Etapa 4-contas de recursos ></span><span class="sxs-lookup"><span data-stu-id="fff10-178">Step 4 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="fff10-179">Etapa 4 <br> encaminhamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="fff10-179">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="fff10-180">Escolha o método de roteamento de chamadas que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="fff10-180">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="fff10-181">Definir o **modo de conferência** como **automático**.</span><span class="sxs-lookup"><span data-stu-id="fff10-181">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="fff10-182">Escolha o **método de roteamento** que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="fff10-182">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="fff10-183">Isso determina a ordem em que os agentes recebem chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="fff10-183">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="fff10-184">Recomendamos **Roteamento serial** ou  **Round Robin**.</span><span class="sxs-lookup"><span data-stu-id="fff10-184">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="fff10-185">Escolha uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="fff10-185">Choose from these options:</span></span>

    - <span data-ttu-id="fff10-186">O **Roteamento do atendente** toca todos os agentes na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="fff10-186">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="fff10-187">O primeiro agente de chamadas para atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="fff10-187">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="fff10-188">O **Roteamento serial** toca todos os agentes de chamada um por um.</span><span class="sxs-lookup"><span data-stu-id="fff10-188">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="fff10-189">Se um agente ignorar ou não atender a chamada, a chamada tocará no próximo agente e experimentará todos os agentes até que ele seja retirado ou expirado.</span><span class="sxs-lookup"><span data-stu-id="fff10-189">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="fff10-190">A **repetição redonda** equilibra o roteamento de chamadas de entrada para que cada agente de chamadas obtenha o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="fff10-190">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="fff10-191">Isso pode ser desejável em um ambiente de vendas de entrada para garantir uma oportunidade igual entre todos os agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fff10-191">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="fff10-192">O mais **longo** é direcionado a cada chamada para o agente que esteve ocioso ao longo do tempo mais longo.</span><span class="sxs-lookup"><span data-stu-id="fff10-192">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="fff10-193">(Os agentes cujo estado de presença esteve ausente há mais de 10 minutos não são incluídos.)</span><span class="sxs-lookup"><span data-stu-id="fff10-193">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Captura de tela das configurações do modo de conferência e do método de roteamento](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="fff10-195">Ative o **roteamento baseado em presença** .</span><span class="sxs-lookup"><span data-stu-id="fff10-195">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="fff10-196">Isso roteia chamadas para agentes cujo status de presença está **disponível**.</span><span class="sxs-lookup"><span data-stu-id="fff10-196">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="fff10-197">Escolha se deseja permitir que os agentes recusem as chamadas.</span><span class="sxs-lookup"><span data-stu-id="fff10-197">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="fff10-198">Defina um **tempo de alerta do agente** para especificar por quanto tempo o telefone do agente tocará antes de a fila redirecionar a chamada para o próximo agente.</span><span class="sxs-lookup"><span data-stu-id="fff10-198">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Captura de tela das configurações de roteamento, cancelamento e tempo de alerta](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="fff10-200">Etapa 5-estouro na chamada ></span><span class="sxs-lookup"><span data-stu-id="fff10-200">Step 5 - Call overflow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="fff10-201">Etapa 5 <br> estouro de chamada</span><span class="sxs-lookup"><span data-stu-id="fff10-201">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="fff10-202">Escolha como você deseja manipular as chamadas que excederam o máximo na fila.</span><span class="sxs-lookup"><span data-stu-id="fff10-202">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="fff10-203">Defina o **número máximo de chamadas na fila**.</span><span class="sxs-lookup"><span data-stu-id="fff10-203">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="fff10-204">Escolha o que você deseja fazer quando o número máximo de chamadas for atingido.</span><span class="sxs-lookup"><span data-stu-id="fff10-204">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="fff10-205">Você pode desconectar a chamada ou redirecioná-la.</span><span class="sxs-lookup"><span data-stu-id="fff10-205">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="fff10-206">Recomendamos que você redirecione a chamada para um dos seguintes destinos:</span><span class="sxs-lookup"><span data-stu-id="fff10-206">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="fff10-207">**Pessoa na organização** -uma pessoa em sua organização que pode receber chamadas de voz</span><span class="sxs-lookup"><span data-stu-id="fff10-207">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="fff10-208">**Aplicativo de voz** -um atendedor automático ou outra fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fff10-208">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="fff10-209">(Escolha a conta de recurso associada ao atendedor automático ou à fila de chamadas ao escolher este destino.)</span><span class="sxs-lookup"><span data-stu-id="fff10-209">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="fff10-210">**Número de telefone externo** – qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="fff10-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="fff10-211">Use este formato: + [código do país] [código de área] [número de telefone]</span><span class="sxs-lookup"><span data-stu-id="fff10-211">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="fff10-212">Correio de **voz** -você pode usar a caixa de correio de voz da equipe que você criou.</span><span class="sxs-lookup"><span data-stu-id="fff10-212">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de tela das configurações de estouro de chamadas](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="fff10-214">Etapa 6-tempo limite de chamada ></span><span class="sxs-lookup"><span data-stu-id="fff10-214">Step 6 - Call timeout ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="fff10-215">Etapa 6 <br> tempo limite de chamada</span><span class="sxs-lookup"><span data-stu-id="fff10-215">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="fff10-216">Escolha o que você deseja que aconteça quando as chamadas estiverem aguardando na fila por muito tempo.</span><span class="sxs-lookup"><span data-stu-id="fff10-216">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="fff10-217">Definir o tempo **limite de chamada: tempo máximo de espera**.</span><span class="sxs-lookup"><span data-stu-id="fff10-217">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="fff10-218">Escolha o que você deseja fazer quando uma chamada expira. Você pode desconectar a chamada ou redirecioná-la.</span><span class="sxs-lookup"><span data-stu-id="fff10-218">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="fff10-219">Recomendamos que você redirecione a chamada para um dos seguintes destinos:</span><span class="sxs-lookup"><span data-stu-id="fff10-219">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="fff10-220">**Pessoa na organização** -uma pessoa em sua organização que pode receber chamadas de voz</span><span class="sxs-lookup"><span data-stu-id="fff10-220">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="fff10-221">**Aplicativo de voz** -um atendedor automático ou outra fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fff10-221">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="fff10-222">(Escolha a conta de recurso associada ao atendedor automático ou à fila de chamadas ao escolher este destino.)</span><span class="sxs-lookup"><span data-stu-id="fff10-222">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="fff10-223">**Número de telefone externo** – qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="fff10-223">**External phone number** - any phone number.</span></span> <span data-ttu-id="fff10-224">Use este formato: + [código do país] [código de área] [número de telefone]</span><span class="sxs-lookup"><span data-stu-id="fff10-224">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="fff10-225">Correio de **voz** -você pode usar a caixa de correio de voz da equipe que você criou.</span><span class="sxs-lookup"><span data-stu-id="fff10-225">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de tela das configurações de tempo limite de chamada](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="fff10-227">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fff10-227">Click **Save**.</span></span>

<span data-ttu-id="fff10-228">Isso conclui a configuração da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fff10-228">This completes the setup of your call queue.</span></span> <span data-ttu-id="fff10-229">Em seguida, talvez você queira [configurar um atendedor automático](create-a-phone-system-auto-attendant-smb.md).</span><span class="sxs-lookup"><span data-stu-id="fff10-229">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

