---
title: Criar uma fila de chamada no Microsoft Teams – tutorial para pequenas empresas
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
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="547be-103">Criar uma fila de chamada – tutorial para pequenas empresas</span><span class="sxs-lookup"><span data-stu-id="547be-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="547be-104">As filas de chamadas fornecem um método de roteamento de chamadores para pessoas em sua organização que podem ajudar com um problema ou pergunta específico.</span><span class="sxs-lookup"><span data-stu-id="547be-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="547be-105">As chamadas são distribuídas uma por vez para as pessoas na fila (que são conhecidas como *agentes).*</span><span class="sxs-lookup"><span data-stu-id="547be-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="547be-106">As filas de chamada fornecem:</span><span class="sxs-lookup"><span data-stu-id="547be-106">Call queues provide:</span></span>

- <span data-ttu-id="547be-107">Uma mensagem de saudação.</span><span class="sxs-lookup"><span data-stu-id="547be-107">A greeting message.</span></span>

- <span data-ttu-id="547be-108">Música enquanto as pessoas estão aguardando em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="547be-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="547be-109">Roteamento de chamadas *- na ordem First In, First Out* (FIFO) - para agentes.</span><span class="sxs-lookup"><span data-stu-id="547be-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="547be-110">Opções de manipulação para excesso de fila e tempo de tempo.</span><span class="sxs-lookup"><span data-stu-id="547be-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="547be-111">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="547be-111">Before you begin</span></span>

<span data-ttu-id="547be-112">Obter algumas [licenças do Sistema de Telefonia – Usuário Virtual,](../teams-add-on-licensing/virtual-user.md) caso ainda não as tenha.</span><span class="sxs-lookup"><span data-stu-id="547be-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="547be-113">Obter uma para cada fila de chamada e o atendimento automático que você planeja configurar.</span><span class="sxs-lookup"><span data-stu-id="547be-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="547be-114">Essas licenças são gratuitas, portanto, sugerimos receber algumas extra caso você decida fazer alterações na configuração no futuro.</span><span class="sxs-lookup"><span data-stu-id="547be-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="547be-115">Como os agentes em uma fila de chamadas podem discar para retornar uma chamada de cliente, considere configurar a ID de chamadas para seus agentes de chamada para seu número de telefone principal ou o número de um atender automático apropriado.</span><span class="sxs-lookup"><span data-stu-id="547be-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="547be-116">Consulte [Gerenciar políticas de ID de chamada no Microsoft Teams](../caller-id-policies.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="547be-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="547be-117">Siga estas etapas para configurar sua fila de chamada</span><span class="sxs-lookup"><span data-stu-id="547be-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="547be-118">Etapa 1 <br> Criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="547be-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="547be-119">Ao criar uma fila de chamada, você pode adicionar usuários individuais à fila ou usar um grupo de segurança existente, grupo do Microsoft 365 ou equipe do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="547be-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="547be-120">Recomendamos usar uma equipe.</span><span class="sxs-lookup"><span data-stu-id="547be-120">We recommend using a team.</span></span> <span data-ttu-id="547be-121">Isso permite que os membros da fila conversem entre si, compartilhem ideias e criem documentos ou outros recursos para ajudá-los a ajudar seus clientes.</span><span class="sxs-lookup"><span data-stu-id="547be-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="547be-122">Uma equipe também fornece uma caixa de correio de voz para que os chamadores deixem uma mensagem após o expediente ou se a fila atingir sua capacidade máxima.</span><span class="sxs-lookup"><span data-stu-id="547be-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="547be-123">Para criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="547be-123">To create a team</span></span>

1. <span data-ttu-id="547be-124">Primeiro, clique **em Equipes** no lado  esquerdo do aplicativo e, em seguida, clique em Ingressar ou criar uma equipe na parte inferior da sua lista de equipes.</span><span class="sxs-lookup"><span data-stu-id="547be-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="547be-125">Em **seguida, clique em Criar** equipe (primeiro cartão, canto superior esquerdo).</span><span class="sxs-lookup"><span data-stu-id="547be-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="547be-126">Escolha **Criar uma equipe do zero.**</span><span class="sxs-lookup"><span data-stu-id="547be-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="547be-127">Em seguida, escolha se deseja uma equipe pública ou privada.</span><span class="sxs-lookup"><span data-stu-id="547be-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="547be-128">Recomendamos **o Private** para sua fila de chamada para evitar que as pessoas se tornem parte da fila involundendo-se na equipe.</span><span class="sxs-lookup"><span data-stu-id="547be-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="547be-129">Nomeia sua equipe e adicione uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="547be-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="547be-130">Quando terminar, clique em **Criar.**</span><span class="sxs-lookup"><span data-stu-id="547be-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="547be-131">Digite os nomes das pessoas que você deseja ter na fila de chamada e clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="547be-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="547be-132">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="547be-132">Click **Close**.</span></span> <span data-ttu-id="547be-133">As pessoas que você adicionar a uma equipe receberão um email para que saibam que agora são membros da sua equipe e que a equipe será a mesma na lista de equipes.</span><span class="sxs-lookup"><span data-stu-id="547be-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="547be-134">Etapa 2 - Contas de recursos ></span><span class="sxs-lookup"><span data-stu-id="547be-134">Step 2 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="547be-135">Etapa 2 <br> Contas de recursos</span><span class="sxs-lookup"><span data-stu-id="547be-135">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="547be-136">Cada fila de chamada que você criar requer uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="547be-136">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="547be-137">Isso é semelhante a uma conta de usuário, exceto que a conta está associada a um atendimento automático ou fila de chamada em vez de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="547be-137">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="547be-138">Nesta etapa, criaremos a conta, atribuiremos a ela uma licença do *Microsoft 365 Phone System – Usuário Virtual* e a usaremos para começar a criar a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="547be-138">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="547be-139">Criar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="547be-139">Create a resource account</span></span>

<span data-ttu-id="547be-140">Você pode criar uma conta de recurso no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="547be-140">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="547be-141">No Centro de administração do Teams, expanda **as configurações de** toda a organização e clique em **Contas de recursos.**</span><span class="sxs-lookup"><span data-stu-id="547be-141">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="547be-142">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="547be-142">Click **Add**.</span></span>

3. <span data-ttu-id="547be-143">No painel **Adicionar conta de recurso,** preencha **o nome** de exibição, nome de usuário e escolha **Fila** de chamada para o tipo de conta **recurso.** </span><span class="sxs-lookup"><span data-stu-id="547be-143">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![Captura de tela da interface do usuário adicionar conta de recurso](../media/resource-account-add-cq.png)

4. <span data-ttu-id="547be-145">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="547be-145">Click **Save**.</span></span>

<span data-ttu-id="547be-146">A nova conta aparecerá na lista de contas.</span><span class="sxs-lookup"><span data-stu-id="547be-146">The new account will appear in the list of accounts.</span></span>

![Captura de tela de uma lista de contas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="547be-148">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="547be-148">Assign a license</span></span>

<span data-ttu-id="547be-149">Você deve atribuir uma *licença do Microsoft 365 Phone System – Usuário Virtual* à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="547be-149">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="547be-150">No Centro de administração do Microsoft 365, clique na conta de recurso à qual você deseja atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="547be-150">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="547be-151">Na guia **Licenças e Aplicativos,** em **Licenças,** selecione **Microsoft 365 Phone System - Usuário Virtual.**</span><span class="sxs-lookup"><span data-stu-id="547be-151">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="547be-152">Clique **em Salvar alterações.**</span><span class="sxs-lookup"><span data-stu-id="547be-152">Click **Save changes**.</span></span>

    ![Captura de tela da interface do usuário de atribuição de licenças no Centro de administração do Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="547be-154">Criar uma fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="547be-154">Create a call queue</span></span>

<span data-ttu-id="547be-155">Em seguida, vamos começar a criar uma nova fila de chamada e atribuir a conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="547be-155">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="547be-156">No Centro de administração do Teams, **expanda o Voice,** clique em **Filas de chamadas** e, em seguida, clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="547be-156">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="547be-157">Digite um nome para a fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="547be-157">Type a name for the call queue.</span></span> <span data-ttu-id="547be-158">Os agentes verão esse nome quando receberem uma chamada recebida da fila.</span><span class="sxs-lookup"><span data-stu-id="547be-158">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="547be-159">Clique **em Adicionar contas,** procure a conta de recurso que você deseja usar com essa fila de chamada, clique em Adicionar **e,** em seguida, clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="547be-159">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="547be-160">Escolha um idioma.</span><span class="sxs-lookup"><span data-stu-id="547be-160">Choose a language.</span></span> <span data-ttu-id="547be-161">Esse idioma será usado para avisos de voz gerados pelo sistema e transcrição da caixa postal (se você habilita-los).</span><span class="sxs-lookup"><span data-stu-id="547be-161">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Captura de tela das configurações de conta de recurso e idioma](../media/call-queue-name-language.png)

4. <span data-ttu-id="547be-163">Especifique se você deseja reproduzir uma saudação para os chamadores quando eles chegam na fila.</span><span class="sxs-lookup"><span data-stu-id="547be-163">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="547be-164">Você deve carregar um arquivo MP3, WAV ou WMA contendo a saudação que deseja reproduzir.</span><span class="sxs-lookup"><span data-stu-id="547be-164">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="547be-165">O Teams fornece músicas padrão para os chamadores enquanto eles estão em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="547be-165">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="547be-166">Se você quiser reproduzir um arquivo de áudio específico, escolha **Reproduzir** um arquivo de áudio e carregue um arquivo MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="547be-166">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="547be-167">A gravação carregada não pode ter mais de 5 MB.</span><span class="sxs-lookup"><span data-stu-id="547be-167">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="547be-168">A música padrão fornecida nas filas de chamada do Teams está livre de royalties a pagar pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="547be-168">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="547be-169">Etapa 3 - Agentes de chamada ></span><span class="sxs-lookup"><span data-stu-id="547be-169">Step 3 - Call agents ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="547be-170">Etapa 3 <br> Agentes de chamada</span><span class="sxs-lookup"><span data-stu-id="547be-170">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="547be-171">Para adicionar agentes à fila de chamada, adicionaremos a equipe que criamos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="547be-171">To add agents to the call queue, we'll add the team that we created earlier.</span></span>

1. <span data-ttu-id="547be-172">Clique **em Adicionar grupos.**</span><span class="sxs-lookup"><span data-stu-id="547be-172">Click **Add groups**.</span></span>
2. <span data-ttu-id="547be-173">Digite o nome da equipe que você criou.</span><span class="sxs-lookup"><span data-stu-id="547be-173">Type the name of the team that you created.</span></span>
3. <span data-ttu-id="547be-174">Clique **em Adicionar** e, em seguida, clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="547be-174">Click **Add**, and then click **Add**.</span></span>

    ![Captura de tela das configurações de usuários e grupos para filas de chamada](../media/call-queue-users-groups-smb.png)

<span data-ttu-id="547be-176">Você pode adicionar até 20 agentes individualmente e até 200 agentes por meio de grupos ou equipes.</span><span class="sxs-lookup"><span data-stu-id="547be-176">You can add up to 20 agents individually and up to 200 agents via groups or teams.</span></span>

> [!NOTE]
> <span data-ttu-id="547be-177">Quando novos usuários são adicionados à equipe, pode levar até oito horas para que a primeira chamada chegue.</span><span class="sxs-lookup"><span data-stu-id="547be-177">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="547be-178">Etapa 4 - Contas de recursos ></span><span class="sxs-lookup"><span data-stu-id="547be-178">Step 4 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="547be-179">Etapa 4 <br> Roteamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="547be-179">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="547be-180">Escolha o método de roteamento de chamadas que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="547be-180">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="547be-181">Definir **o modo de conferência** como **Automático.**</span><span class="sxs-lookup"><span data-stu-id="547be-181">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="547be-182">Escolha o **método de roteamento** que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="547be-182">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="547be-183">Isso determina a ordem em que os agentes recebem chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="547be-183">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="547be-184">Recomendamos **roteamento em série** ou Round **robin.**</span><span class="sxs-lookup"><span data-stu-id="547be-184">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="547be-185">Escolha uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="547be-185">Choose from these options:</span></span>

    - <span data-ttu-id="547be-186">**O roteamento** do attendant toca em todos os agentes na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="547be-186">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="547be-187">O primeiro agente de chamada a atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="547be-187">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="547be-188">**O roteamento** de série toca em todos os agentes de chamada, um por um.</span><span class="sxs-lookup"><span data-stu-id="547be-188">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="547be-189">Se um agente descartar ou não atender uma chamada, a chamada tocará no próximo agente e tentará todos os agentes até que ela seja escolhida ou a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="547be-189">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="547be-190">**A round robin** equilibra o roteamento de chamadas de entrada para que cada agente de chamada obtém o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="547be-190">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="547be-191">Isso pode ser desejável em um ambiente de vendas de entrada para garantir a oportunidade igual entre todos os agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="547be-191">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="547be-192">**O tempo ocioso** mais longo encaminha cada chamada para o agente que ficou ocioso por mais tempo.</span><span class="sxs-lookup"><span data-stu-id="547be-192">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="547be-193">(Os agentes cujo estado de presença está fora por mais de 10 minutos não são incluídos.)</span><span class="sxs-lookup"><span data-stu-id="547be-193">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Captura de tela das configurações do modo de conferência e do método de roteamento](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="547be-195">Ativar **o roteamento baseado em** presença.</span><span class="sxs-lookup"><span data-stu-id="547be-195">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="547be-196">Isso faz chamadas para agentes cujo status de presença **está Disponível.**</span><span class="sxs-lookup"><span data-stu-id="547be-196">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="547be-197">Escolha se você deseja permitir que os agentes optem por não fazer chamadas.</span><span class="sxs-lookup"><span data-stu-id="547be-197">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="547be-198">De definir **um horário de alerta** do Agente para especificar por quanto tempo o telefone de um agente tocará antes que a fila redirecione a chamada para o próximo agente.</span><span class="sxs-lookup"><span data-stu-id="547be-198">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Captura de tela das configurações de roteamento, de opção e de tempo de alerta](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="547be-200">Etapa 5 - Chamada excedente ></span><span class="sxs-lookup"><span data-stu-id="547be-200">Step 5 - Call overflow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="547be-201">Etapa 5 <br> Estouro de chamada</span><span class="sxs-lookup"><span data-stu-id="547be-201">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="547be-202">Escolha como você deseja lidar com chamadas que excedem o máximo na fila.</span><span class="sxs-lookup"><span data-stu-id="547be-202">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="547be-203">De definir **o número máximo de chamadas na fila.**</span><span class="sxs-lookup"><span data-stu-id="547be-203">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="547be-204">Escolha o que você deseja fazer quando o número máximo de chamadas for atingido.</span><span class="sxs-lookup"><span data-stu-id="547be-204">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="547be-205">Você pode desconectar a chamada ou redirecioná-la.</span><span class="sxs-lookup"><span data-stu-id="547be-205">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="547be-206">Recomendamos que você redirecione a chamada para um dos seguintes destinos:</span><span class="sxs-lookup"><span data-stu-id="547be-206">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="547be-207">**Pessoa na organização** - uma pessoa em sua organização que pode receber chamadas de voz</span><span class="sxs-lookup"><span data-stu-id="547be-207">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="547be-208">**Aplicativo de voz** – um atendimento automático ou outra fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="547be-208">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="547be-209">(Escolha a conta de recurso associada ao atendimento automático ou fila de chamada ao escolher este destino.)</span><span class="sxs-lookup"><span data-stu-id="547be-209">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="547be-210">**Número de telefone externo** – qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="547be-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="547be-211">Use este formato: +[código do país][código de área][número de telefone]</span><span class="sxs-lookup"><span data-stu-id="547be-211">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="547be-212">**Caixa** postal : você pode usar a caixa de correio de voz da equipe que você criou.</span><span class="sxs-lookup"><span data-stu-id="547be-212">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de tela das configurações de estouro de chamada](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="547be-214">Etapa 6 - Tempo de tempo de ></span><span class="sxs-lookup"><span data-stu-id="547be-214">Step 6 - Call timeout ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="547be-215">Etapa 6 <br> Tempo de tempo de chamada</span><span class="sxs-lookup"><span data-stu-id="547be-215">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="547be-216">Escolha o que você deseja que aconteça quando as chamadas estão aguardando muito tempo na fila.</span><span class="sxs-lookup"><span data-stu-id="547be-216">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="547be-217">Definir o **Tempo Limite da Chamada: tempo máximo de espera.**</span><span class="sxs-lookup"><span data-stu-id="547be-217">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="547be-218">Escolha o que você deseja fazer quando uma chamada estiver com o tempo de saída. Você pode desconectar a chamada ou redirecioná-la.</span><span class="sxs-lookup"><span data-stu-id="547be-218">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="547be-219">Recomendamos que você redirecione a chamada para um dos seguintes destinos:</span><span class="sxs-lookup"><span data-stu-id="547be-219">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="547be-220">**Pessoa na organização** - uma pessoa em sua organização que pode receber chamadas de voz</span><span class="sxs-lookup"><span data-stu-id="547be-220">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="547be-221">**Aplicativo de voz** – um atendimento automático ou outra fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="547be-221">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="547be-222">(Escolha a conta de recurso associada ao atendimento automático ou fila de chamada ao escolher este destino.)</span><span class="sxs-lookup"><span data-stu-id="547be-222">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="547be-223">**Número de telefone externo** – qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="547be-223">**External phone number** - any phone number.</span></span> <span data-ttu-id="547be-224">Use este formato: +[código do país][código de área][número de telefone]</span><span class="sxs-lookup"><span data-stu-id="547be-224">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="547be-225">**Caixa** postal : você pode usar a caixa de correio de voz da equipe que você criou.</span><span class="sxs-lookup"><span data-stu-id="547be-225">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de tela das configurações de tempo de tempo de chamada](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="547be-227">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="547be-227">Click **Save**.</span></span>

<span data-ttu-id="547be-228">Isso conclui a configuração da fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="547be-228">This completes the setup of your call queue.</span></span> <span data-ttu-id="547be-229">Em seguida, talvez você queira [configurar um assistente automático.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="547be-229">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

