---
title: Criar uma fila de chamada no Microsoft Teams - tutorial de pequenas empresas
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
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
description: Saiba como configurar filas de chamada para pequenas empresas em Microsoft 365 Business Voice.
ms.openlocfilehash: be6c53855a6d32f8348f02b18ac3074388dafc88
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739663"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="3fdac-103">Criar uma fila de chamada - tutorial de pequenas empresas</span><span class="sxs-lookup"><span data-stu-id="3fdac-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="3fdac-104">As filas de chamadas fornecem um método de roteamento de chamadas para as pessoas da organização que podem ajudar com um problema ou pergunta específica.</span><span class="sxs-lookup"><span data-stu-id="3fdac-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="3fdac-105">As chamadas são distribuídas uma por vez para as pessoas na fila (que são conhecidas como *agentes*).</span><span class="sxs-lookup"><span data-stu-id="3fdac-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="3fdac-106">As filas de chamada fornecem:</span><span class="sxs-lookup"><span data-stu-id="3fdac-106">Call queues provide:</span></span>

- <span data-ttu-id="3fdac-107">Uma mensagem de saudação.</span><span class="sxs-lookup"><span data-stu-id="3fdac-107">A greeting message.</span></span>

- <span data-ttu-id="3fdac-108">Música enquanto as pessoas estão em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="3fdac-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="3fdac-109">Roteamento de chamadas, na ordem *Primeiro a Entrar, Primeiro a Sair* (PEPS), para os agentes.</span><span class="sxs-lookup"><span data-stu-id="3fdac-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="3fdac-110">Opções de administração para estouro da fila e tempo limite.</span><span class="sxs-lookup"><span data-stu-id="3fdac-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="video-demonstration"></a><span data-ttu-id="3fdac-111">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="3fdac-111">Video demonstration</span></span>

<span data-ttu-id="3fdac-112">Este vídeo demonstra como criar uma fila de chamada em Teams.</span><span class="sxs-lookup"><span data-stu-id="3fdac-112">This video demonstrates how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="3fdac-113">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="3fdac-113">Before you begin</span></span>

<span data-ttu-id="3fdac-114">Obter algumas [Sistema de Telefonia - Licenças](../teams-add-on-licensing/virtual-user.md) de usuário virtual se você ainda não as tiver.</span><span class="sxs-lookup"><span data-stu-id="3fdac-114">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="3fdac-115">Obter uma para cada fila de chamada e o atendimento automático que você planeja configurar.</span><span class="sxs-lookup"><span data-stu-id="3fdac-115">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="3fdac-116">Essas licenças são gratuitas, portanto, sugerimos obter alguns extras caso você decida fazer alterações em sua instalação no futuro.</span><span class="sxs-lookup"><span data-stu-id="3fdac-116">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="3fdac-117">Como os agentes em uma fila de chamadas podem discar para retornar uma chamada de cliente, considere definir a ID do chamador para seus agentes de chamada para o número de telefone principal ou o número de um atendimento automático apropriado.</span><span class="sxs-lookup"><span data-stu-id="3fdac-117">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="3fdac-118">Para mais informações, confira [Gerenciar políticas de identificação de chamadas no Microsoft Teams](../caller-id-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3fdac-118">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="3fdac-119">Siga estas etapas para configurar sua fila de chamada</span><span class="sxs-lookup"><span data-stu-id="3fdac-119">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="3fdac-120">Etapa 1 <br> Criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="3fdac-120">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="3fdac-121">Ao criar uma fila de chamada, você pode adicionar usuários individuais à fila ou usar um grupo de segurança existente, Microsoft 365 grupo ou Microsoft Teams equipe.</span><span class="sxs-lookup"><span data-stu-id="3fdac-121">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="3fdac-122">Recomendamos [o uso de um canal de equipe](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span><span class="sxs-lookup"><span data-stu-id="3fdac-122">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="3fdac-123">Isso permite que os membros da fila conversem uns com os outros, compartilhem ideias e criem documentos ou outros recursos para ajudá-los a ajudar seus clientes.</span><span class="sxs-lookup"><span data-stu-id="3fdac-123">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="3fdac-124">Uma equipe também fornece uma caixa de correio de voz para os chamadores deixarem uma mensagem após o horário ou se a fila atingir sua capacidade máxima.</span><span class="sxs-lookup"><span data-stu-id="3fdac-124">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="3fdac-125">Para criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="3fdac-125">To create a team</span></span>

1. <span data-ttu-id="3fdac-126">Primeiro, clique **Teams** lado esquerdo do aplicativo e  clique em Ingressar ou criar uma equipe na parte inferior da lista de equipes.</span><span class="sxs-lookup"><span data-stu-id="3fdac-126">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="3fdac-127">Em **seguida, clique em** Criar equipe (primeiro cartão, canto superior esquerdo).</span><span class="sxs-lookup"><span data-stu-id="3fdac-127">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="3fdac-128">Escolha **Criar uma equipe do zero**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-128">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="3fdac-129">Em seguida, escolha se deseja uma equipe pública ou privada.</span><span class="sxs-lookup"><span data-stu-id="3fdac-129">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="3fdac-130">Recomendamos **o Private** para sua fila de chamada para evitar que as pessoas se tornem parte da fila involundendo-se à equipe.</span><span class="sxs-lookup"><span data-stu-id="3fdac-130">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="3fdac-131">Nomeia sua equipe e adicione uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="3fdac-131">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="3fdac-132">Quando terminar, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-132">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="3fdac-133">Digite os nomes das pessoas que você deseja ter na fila de chamada e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-133">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="3fdac-134">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-134">Click **Close**.</span></span> <span data-ttu-id="3fdac-135">As pessoas que você adicionar a uma equipe receberão um email para que saibam que agora são membros da sua equipe e que a equipe será acionda na lista de equipes.</span><span class="sxs-lookup"><span data-stu-id="3fdac-135">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="3fdac-136">Em seguida, adicionaremos um canal a ser usado com a fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="3fdac-136">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="3fdac-137">Para adicionar um canal</span><span class="sxs-lookup"><span data-stu-id="3fdac-137">To add a channel</span></span>

1. <span data-ttu-id="3fdac-138">Em Teams, encontre a equipe que você acabou de criar, clique em **Mais opções** (...) e clique em **Adicionar canal**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-138">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="3fdac-139">Digite um nome e uma descrição para o canal e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-139">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3fdac-140">Etapa 2 - Contas de recursos ></span><span class="sxs-lookup"><span data-stu-id="3fdac-140">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="3fdac-141">Etapa 2 <br> Contas de recursos</span><span class="sxs-lookup"><span data-stu-id="3fdac-141">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="3fdac-142">Cada fila de chamada que você criar requer uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="3fdac-142">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="3fdac-143">Isso é semelhante a uma conta de usuário, exceto que a conta está associada a um atendimento automático ou fila de chamada em vez de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="3fdac-143">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="3fdac-144">Nesta etapa, criaremos a conta, atribuiremos uma Microsoft 365 Sistema de Telefonia *- Licença* de usuário virtual e a usaremos para começar a criar a fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="3fdac-144">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="3fdac-145">Criar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="3fdac-145">Create a resource account</span></span>

<span data-ttu-id="3fdac-146">Você pode criar uma conta de recurso no Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="3fdac-146">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="3fdac-147">No centro Teams de administração, expanda **as** configurações de toda a organização e clique em **Contas de recursos.**</span><span class="sxs-lookup"><span data-stu-id="3fdac-147">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="3fdac-148">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-148">Click **Add**.</span></span>

3. <span data-ttu-id="3fdac-149">No painel **Adicionar conta de** recurso, preencha **Nome** de exibição, Nome de **usuário** e escolha **Fila** de chamada para o tipo de conta **de recurso**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-149">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="3fdac-150">Os agentes verão o nome de exibição quando receberem uma chamada de entrada da fila.</span><span class="sxs-lookup"><span data-stu-id="3fdac-150">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![Captura de tela da interface do usuário adicionar conta de recurso](../media/resource-account-add-cq.png)

4. <span data-ttu-id="3fdac-152">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-152">Click **Save**.</span></span>

   <span data-ttu-id="3fdac-153">A nova conta aparecerá na lista de contas.</span><span class="sxs-lookup"><span data-stu-id="3fdac-153">The new account will appear in the list of accounts.</span></span>

   ![Captura de tela de uma lista de contas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="3fdac-155">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="3fdac-155">Assign a license</span></span>

<span data-ttu-id="3fdac-156">Você deve atribuir uma *Microsoft 365 Sistema de Telefonia - Licença de usuário virtual* à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="3fdac-156">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="3fdac-157">No centro Microsoft 365 de administração,  na lista Usuários ativos, clique na conta de recurso à qual você deseja atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="3fdac-157">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="3fdac-158">Na guia **Licenças e Aplicativos,** em **Licenças,** selecione **Microsoft 365 Sistema de Telefonia - Usuário Virtual**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-158">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="3fdac-159">Clique **em Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-159">Click **Save changes**.</span></span>

    ![Captura de tela da interface do usuário atribuir licenças no Microsoft 365 de administração](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="3fdac-161">Criar uma fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="3fdac-161">Create a call queue</span></span>

<span data-ttu-id="3fdac-162">Em seguida, vamos começar a criar uma nova fila de chamada e atribuir a conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="3fdac-162">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="3fdac-163">No centro Teams de administração, **expanda Voz,** clique em **Filas de chamadas** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-163">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="3fdac-164">Digite um nome para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3fdac-164">Type a name for the call queue.</span></span>

2. <span data-ttu-id="3fdac-165">Clique em **Adicionar contas**, procure a conta de recurso que você deseja usar com a fila de chamadas, clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-165">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="3fdac-166">(Opcional) Em **Atribuir ID** de chamada, clique em **Adicionar**, pesquisar as contas de recurso que você criou para o seu assistente automático, clique em Adicionar **e** clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-166">(Optional) Under **Assign calling ID**, click **Add**, search for the resource accounts that you created for your auto attendant, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="3fdac-167">Isso dará aos seus agentes de chamada a ID do chamador da sua linha principal quando eles chamarem.</span><span class="sxs-lookup"><span data-stu-id="3fdac-167">This will give your call agents the caller ID of your main line when they call out.</span></span>

    ![Captura de tela das configurações de ID de chamada](../media/call-queue-assign-calling-id.png)

3. <span data-ttu-id="3fdac-169">Escolha um idioma.</span><span class="sxs-lookup"><span data-stu-id="3fdac-169">Choose a language.</span></span> <span data-ttu-id="3fdac-170">Esse idioma será usado para comandos de voz gerados pelo sistema e para a transcrição da caixa postal (se habilitados).</span><span class="sxs-lookup"><span data-stu-id="3fdac-170">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Captura de tela das configurações da conta de recurso](../media/call-queue-name-language.png)

4. <span data-ttu-id="3fdac-172">Especifique se você deseja reproduzir uma saudação aos chamadores quando eles chegarem na fila.</span><span class="sxs-lookup"><span data-stu-id="3fdac-172">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="3fdac-173">Carregue um arquivo MP3, WAV ou WMA contendo a saudação que deseja reproduzir.</span><span class="sxs-lookup"><span data-stu-id="3fdac-173">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="3fdac-174">O Teams fornece música padrão aos chamadores enquanto eles estão em espera em uma fila.</span><span class="sxs-lookup"><span data-stu-id="3fdac-174">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="3fdac-175">Se você quiser reproduzir um arquivo de áudio específico, escolha **Reproduzir um arquivo de áudio** e carregue um arquivo MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="3fdac-175">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3fdac-176">A gravação carregada não pode ser maior do que 5 MB.</span><span class="sxs-lookup"><span data-stu-id="3fdac-176">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="3fdac-177">A música padrão fornecida nas filas de chamadas do Teams é livre de royalties pagáveis pela organização.</span><span class="sxs-lookup"><span data-stu-id="3fdac-177">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="3fdac-178">Etapa 3 - Agentes de chamada ></span><span class="sxs-lookup"><span data-stu-id="3fdac-178">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="3fdac-179">Etapa 3 <br> Agentes de chamada</span><span class="sxs-lookup"><span data-stu-id="3fdac-179">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="3fdac-180">Para adicionar agentes à fila de chamada, vamos adicioná-los à equipe e ao canal que criamos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3fdac-180">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="3fdac-181">Selecione a **opção Escolher uma equipe** e clique em Adicionar um **canal**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-181">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="3fdac-182">Digite o nome da equipe que você criou, selecione-a e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-182">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="3fdac-183">Selecione o canal que você criou para a fila.</span><span class="sxs-lookup"><span data-stu-id="3fdac-183">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="3fdac-184">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-184">Click **Apply**.</span></span>

    ![Captura de tela das configurações de usuários e grupos para filas de chamada](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="3fdac-186">Quando novos usuários são adicionados à equipe, pode levar até oito horas para a primeira chamada chegar.</span><span class="sxs-lookup"><span data-stu-id="3fdac-186">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3fdac-187">Etapa 4 - Contas de recursos ></span><span class="sxs-lookup"><span data-stu-id="3fdac-187">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="3fdac-188">Etapa 4 <br> Roteamento de Chamadas</span><span class="sxs-lookup"><span data-stu-id="3fdac-188">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="3fdac-189">Escolha o método de roteamento de chamadas que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="3fdac-189">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="3fdac-190">Definir **o modo de conferência** como **Automático**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-190">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="3fdac-191">Escolha o **método routing** que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="3fdac-191">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="3fdac-192">Isso determina a ordem na qual os agentes recebem chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="3fdac-192">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="3fdac-193">Recomendamos **roteamento serial** ou  **round robin**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-193">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="3fdac-194">Escolha uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="3fdac-194">Choose from these options:</span></span>

    - <span data-ttu-id="3fdac-195">O **Roteamento de atendedor** chama todos os agentes na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="3fdac-195">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="3fdac-196">O primeiro agente de chamada que atender recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="3fdac-196">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="3fdac-197">**O roteamento** serial toca todos os agentes de chamada um por um.</span><span class="sxs-lookup"><span data-stu-id="3fdac-197">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="3fdac-198">Se um agente ignora ou não atende uma chamada, ela tocará para o próximo agente e tentará com todos os agentes até que seja atendida ou atinja o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="3fdac-198">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="3fdac-199">O **Round robin** equilibra o roteamento das chamadas de entrada para que cada agente de chamada receba o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="3fdac-199">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="3fdac-200">Isso pode ser desejável em um ambiente de vendas de entrada para garantir igualdade de oportunidades entre todos os agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="3fdac-200">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="3fdac-201">O **Ocioso por mais tempo** encaminha cada chamada para o agente que está ocioso há mais tempo.</span><span class="sxs-lookup"><span data-stu-id="3fdac-201">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="3fdac-202">(Agentes cujo estado de presença foi afastado por mais de 10 minutos não estão incluídos.)</span><span class="sxs-lookup"><span data-stu-id="3fdac-202">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Captura de tela das configurações de método de roteamento e modo de conferência](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="3fdac-204">Ativar **o roteamento baseado em** presença.</span><span class="sxs-lookup"><span data-stu-id="3fdac-204">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="3fdac-205">Isso encaminha chamadas para agentes cujo status de presença **está Disponível**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-205">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="3fdac-206">Escolha se deseja permitir que os agentes optem por não fazer chamadas.</span><span class="sxs-lookup"><span data-stu-id="3fdac-206">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="3fdac-207">De definir **um tempo de alerta do** Agente para especificar por quanto tempo o telefone de um agente tocará antes que a fila redirecione a chamada para o próximo agente.</span><span class="sxs-lookup"><span data-stu-id="3fdac-207">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Captura de tela das configurações de roteamento, recusa e tempo de alerta](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="3fdac-209">Etapa 5 - Estouro de chamada ></span><span class="sxs-lookup"><span data-stu-id="3fdac-209">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="3fdac-210">Etapa 5 <br> Estouro de chamada</span><span class="sxs-lookup"><span data-stu-id="3fdac-210">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="3fdac-211">Escolha como você deseja lidar com chamadas que excedem o máximo na fila.</span><span class="sxs-lookup"><span data-stu-id="3fdac-211">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="3fdac-212">De definir **as chamadas Máximas na fila**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-212">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="3fdac-213">Escolha o que você deseja fazer quando o número máximo de chamadas for atingido.</span><span class="sxs-lookup"><span data-stu-id="3fdac-213">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="3fdac-214">Você pode desconectar a chamada ou redirecioná-la.</span><span class="sxs-lookup"><span data-stu-id="3fdac-214">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="3fdac-215">Recomendamos redirecionar a chamada para um dos seguintes destinos:</span><span class="sxs-lookup"><span data-stu-id="3fdac-215">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="3fdac-216">**Pessoa na organização** - uma pessoa em sua organização que é capaz de receber chamadas de voz</span><span class="sxs-lookup"><span data-stu-id="3fdac-216">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="3fdac-217">**Aplicativo de voz** - um atendimento automático ou outra fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3fdac-217">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="3fdac-218">(Escolha a conta de recurso associada ao atendimento automático ou fila de chamada ao escolher esse destino.)</span><span class="sxs-lookup"><span data-stu-id="3fdac-218">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="3fdac-219">**Número de telefone externo** - qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="3fdac-219">**External phone number** - any phone number.</span></span> <span data-ttu-id="3fdac-220">Use este formato: +[código do país][código de área][número de telefone]</span><span class="sxs-lookup"><span data-stu-id="3fdac-220">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="3fdac-221">**Caixa** postal - você pode usar a caixa de correio de voz da equipe que você criou.</span><span class="sxs-lookup"><span data-stu-id="3fdac-221">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de tela das configurações de estouro de chamadas](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="3fdac-223">Etapa 6 - Tempo de ></span><span class="sxs-lookup"><span data-stu-id="3fdac-223">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="3fdac-224">Etapa 6 <br> Tempo de tempo de chamada</span><span class="sxs-lookup"><span data-stu-id="3fdac-224">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="3fdac-225">Escolha o que você deseja que aconteça quando as chamadas estão esperando na fila por muito tempo.</span><span class="sxs-lookup"><span data-stu-id="3fdac-225">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="3fdac-226">De definir **o tempo máximo de espera**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-226">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="3fdac-227">Escolha o que você deseja fazer quando uma chamada chegar ao tempo de saída. Você pode desconectar a chamada ou redirecioná-la.</span><span class="sxs-lookup"><span data-stu-id="3fdac-227">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="3fdac-228">Recomendamos redirecionar a chamada para um dos seguintes destinos:</span><span class="sxs-lookup"><span data-stu-id="3fdac-228">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="3fdac-229">**Pessoa na organização** - uma pessoa em sua organização que é capaz de receber chamadas de voz</span><span class="sxs-lookup"><span data-stu-id="3fdac-229">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="3fdac-230">**Aplicativo de voz** - um atendimento automático ou outra fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3fdac-230">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="3fdac-231">(Escolha a conta de recurso associada ao atendimento automático ou fila de chamada ao escolher esse destino.)</span><span class="sxs-lookup"><span data-stu-id="3fdac-231">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="3fdac-232">**Número de telefone externo** - qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="3fdac-232">**External phone number** - any phone number.</span></span> <span data-ttu-id="3fdac-233">Use este formato: +[código do país][código de área][número de telefone]</span><span class="sxs-lookup"><span data-stu-id="3fdac-233">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="3fdac-234">**Caixa** postal - você pode usar a caixa de correio de voz da equipe que você criou.</span><span class="sxs-lookup"><span data-stu-id="3fdac-234">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Captura de tela das configurações de tempo limite de chamada](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="3fdac-236">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3fdac-236">Click **Save**.</span></span>

<span data-ttu-id="3fdac-237">Isso conclui a instalação da fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="3fdac-237">This completes the setup of your call queue.</span></span> <span data-ttu-id="3fdac-238">Em seguida, talvez você [queira configurar um atendimento automático.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="3fdac-238">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

