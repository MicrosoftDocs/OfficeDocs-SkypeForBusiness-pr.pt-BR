---
title: Criar ou modificar uma fila no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Crie ou modifique uma fila do Grupo de Resposta, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: b355cde0d8a99938538488152276a6c8eb4c6d4b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103577"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="18d68-103">Criar ou modificar uma fila no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="18d68-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="18d68-104">Crie ou modifique uma fila do Grupo de Resposta, no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="18d68-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="18d68-105">As filas retêm os chamadores até que um agente atenda à chamada.</span><span class="sxs-lookup"><span data-stu-id="18d68-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="18d68-106">Quando o aplicativo grupo de resposta pesquisa um agente disponível, ele pesquisa grupos de agentes na ordem em que você os lista.</span><span class="sxs-lookup"><span data-stu-id="18d68-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="18d68-107">Você pode selecionar os grupos de agentes que são atribuídos à fila e especificar o comportamento dela, como a limitação do número de chamadas que a fila pode reter e o período de tempo que uma chamada aguarda até que um agente a atenda.</span><span class="sxs-lookup"><span data-stu-id="18d68-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="18d68-108">Use um dos seguintes procedimentos para criar ou modificar uma fila.</span><span class="sxs-lookup"><span data-stu-id="18d68-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="18d68-109">Para usar o Painel de Controle do Skype for Business Server para criar ou modificar uma fila</span><span class="sxs-lookup"><span data-stu-id="18d68-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="18d68-110">Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinida que suportam o Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="18d68-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18d68-111">Se você for um dos Gerentes de grupo de resposta delegados para um fluxo de trabalho gerenciado, é possível criar ou modificar filas de grupo de resposta e atribuí-las aos fluxos de trabalho gerenciados.</span><span class="sxs-lookup"><span data-stu-id="18d68-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="18d68-112">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="18d68-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="18d68-113">Na barra de navegação esquerda, clique em **Grupos de Resposta** e clique em **Fila**.</span><span class="sxs-lookup"><span data-stu-id="18d68-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="18d68-114">Na página **Fila**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="18d68-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="18d68-115">Para criar uma nova fila, clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="18d68-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="18d68-116">Em **Selecionar um serviço**, digite uma parte ou o nome inteiro do serviço do **ApplicationServer** onde deseja adicionar a fila no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="18d68-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="18d68-117">Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="18d68-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="18d68-p103">Para modificar uma fila existente, digite uma parte ou o nome inteiro da fila no campo de pesquisa. Na lista resultante de filas, clique na fila que você deseja, em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="18d68-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="18d68-120">Em **Nome**, digite um nome identificador para a fila.</span><span class="sxs-lookup"><span data-stu-id="18d68-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="18d68-121">Em **Descrição**, digite uma descrição para a fila.</span><span class="sxs-lookup"><span data-stu-id="18d68-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="18d68-p104">Em **Grupos**, especifique os grupos que você deseja atribuir à fila. Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="18d68-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="18d68-p105">Para adicionar um grupo à fila, clique em **Selecionar**. No campo de pesquisa **Selecionar grupos**, digite o parte ou o nome inteiro do grupo de agentes que você deseja atribuir à fila, clique no grupo de agentes desejado e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="18d68-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="18d68-126">Para remover um grupo da fila, na lista de grupos de agentes, clique no grupo que você deseja remover e em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="18d68-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="18d68-127">Para alterar a ordem em que os agentes são pesquisados, na lista de grupos de agentes, clique em um grupo e na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="18d68-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="18d68-p106">Quando o servidor pesquisa por um agente disponível para a fila, ele usa a ordem do grupo. Ou seja, o primeiro grupo da lista é pesquisado primeiro, seguido pelo segundo e assim sucessivamente.</span><span class="sxs-lookup"><span data-stu-id="18d68-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="18d68-130">Para especificar um período máximo de tempo para um chamador aguardar em espera antes que um agente responda à chamada, marque a caixa de seleção **Habilitar o tempo limite da fila** e, em seguida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="18d68-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="18d68-131">a.</span><span class="sxs-lookup"><span data-stu-id="18d68-131">a.</span></span> <span data-ttu-id="18d68-132">Em **Período de tempo limite (segundos)**, especifique o número máximo de segundos que um chamador aguarda antes de um agente responder à chamada.</span><span class="sxs-lookup"><span data-stu-id="18d68-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="18d68-133">b.</span><span class="sxs-lookup"><span data-stu-id="18d68-133">b.</span></span> <span data-ttu-id="18d68-134">Em **Ação de Chamada**, selecione a ação que ocorre quando o tempo limite de uma chamada se esgota da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="18d68-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="18d68-135">Para desconectar a chamada após o tempo limite, clique em **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="18d68-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="18d68-136">Para encaminhar a chamada para a caixa postal, clique em Encaminhar para caixa postal e, em seguida, no campo endereço **SIP,** digite um endereço de caixa postal no formato sip: *\<username\>* @  *\<domainname\>* (por exemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="18d68-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="18d68-137">Para encaminhar a chamada para outro número de telefone, clique em Encaminhar para o número de telefone **e,** em seguida, no campo endereço **SIP,** digite o número de telefone no formato sip: *\<number\>* @  *\<domainname\>* (por exemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="18d68-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="18d68-138">Para encaminhar a chamada para outro usuário, clique em Encaminhar para endereço **SIP** e, em seguida, no campo endereço **SIP,** digite o URI do usuário no formato sip: _\<username\>_ @  _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="18d68-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="18d68-139">Para encaminhar a chamada para outra fila de espera, clique em **Encaminhar para outra fila** e, em seguida, procure na fila a ser usada.</span><span class="sxs-lookup"><span data-stu-id="18d68-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="18d68-140">Para especificar um número máximo de chamadas que a fila de espera poderá conter, marque a caixa de seleção **Habilitar o estouro da fila** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="18d68-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="18d68-141">a.</span><span class="sxs-lookup"><span data-stu-id="18d68-141">a.</span></span> <span data-ttu-id="18d68-142">Em **Número máximo de chamadas**, selecione o número máximo de chamadas que a fila de espera conterá.</span><span class="sxs-lookup"><span data-stu-id="18d68-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="18d68-143">b.</span><span class="sxs-lookup"><span data-stu-id="18d68-143">b.</span></span> <span data-ttu-id="18d68-144">Em **Encaminhar a chamada**, selecione qual chamada será encaminhada quando a fila estiver cheia: **Chamada Mais Recente** ou **Chamada Mais Antiga**.</span><span class="sxs-lookup"><span data-stu-id="18d68-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="18d68-145">c.</span><span class="sxs-lookup"><span data-stu-id="18d68-145">c.</span></span> <span data-ttu-id="18d68-146">Em **Ação de chamada**, selecione a ação que ocorre quando o limite de excedente é atingido da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="18d68-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="18d68-147">Para desconectar a chamada após o tempo limite, clique em **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="18d68-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="18d68-148">Para encaminhar a chamada para a caixa postal, clique em Encaminhar para caixa postal e, em seguida, no campo endereço **SIP,** digite um endereço de caixa postal no formato sip: *\<username\>* @  *\<domainname\>* (por exemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="18d68-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="18d68-149">Para encaminhar a chamada para outro número de telefone, clique em Encaminhar para o número de telefone **e,** em seguida, no campo endereço **SIP,** digite o número de telefone no formato sip: *\<number\>* @  *\<domainname\>* (por exemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="18d68-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="18d68-150">Para encaminhar a chamada para outro usuário, clique em Encaminhar para endereço **SIP** e, em seguida, no campo endereço **SIP,** digite o URI do usuário no formato sip: _\<username\>_ @  _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="18d68-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="18d68-151">Para encaminhar a chamada para outra fila de espera, clique em **Encaminhar para outra fila** e, em seguida, procure na fila a ser usada.</span><span class="sxs-lookup"><span data-stu-id="18d68-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="18d68-152">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="18d68-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="18d68-153">Para usar o Shell de Gerenciamento do Skype for Business Server para criar ou modificar uma fila</span><span class="sxs-lookup"><span data-stu-id="18d68-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="18d68-154">Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinida que suportam o Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="18d68-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18d68-155">Se você for um dos Gerentes do grupo de resposta designado para um fluxo de trabalho gerenciado, será possível criar grupos de agentes e filas, bem como atribuir grupos de agentes a filas.</span><span class="sxs-lookup"><span data-stu-id="18d68-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="18d68-156">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="18d68-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="18d68-p112">Crie o prompt para que seja reproduzido quando o limite de tempo da fila é atingido e salve-o em um variável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="18d68-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="18d68-159">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="18d68-159">For example:</span></span>
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="18d68-160">Para usar um arquivo de áudio no prompt, use o cmdlet **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="18d68-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="18d68-161">Para obter detalhes, [consulte Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="18d68-161">For details, see [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="18d68-p114">Defina a ação que será executada quando o limite de tempo da fila for atingido e salve-o em um variável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="18d68-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="18d68-164">Para obter detalhes sobre ações possíveis e sua sintaxe, consulte [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="18d68-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="18d68-165">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="18d68-165">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="18d68-p115">Crie o prompt que será reproduzido quando o limite de excedente da fila for atingido e salve-o em uma variável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="18d68-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="18d68-168">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="18d68-168">For example:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="18d68-169">Para usar um arquivo de áudio no prompt, use o cmdlet **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="18d68-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="18d68-170">Para obter detalhes, [consulte Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="18d68-170">For details, see [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="18d68-p117">Defina a ação que será executada quando o limite de excedente da fila for atingido e salve-o em uma variável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="18d68-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="18d68-173">Para obter detalhes sobre ações possíveis e sua sintaxe, consulte [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="18d68-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="18d68-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="18d68-174">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="18d68-175">Recupere o nome do serviço do serviço de Grupo de resposta e atribua-o a uma variável.</span><span class="sxs-lookup"><span data-stu-id="18d68-175">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="18d68-176">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="18d68-176">At the command line, run:</span></span>
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="18d68-177">Obtenha a identidade do grupo de agente que será atribuído à fila.</span><span class="sxs-lookup"><span data-stu-id="18d68-177">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="18d68-178">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="18d68-178">At the command line, run:</span></span>
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="18d68-179">Para obter detalhes sobre como criar o grupo de agentes, consulte [New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="18d68-179">For details about creating the agent group, see [New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="18d68-p120">Crie a fila. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="18d68-p120">Create the queue. At the command line, run:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="18d68-182">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="18d68-182">For example:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="18d68-p121">Confirme se a fila foi criada. Execute:</span><span class="sxs-lookup"><span data-stu-id="18d68-p121">Confirm that the queue is created. Run:</span></span>
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="18d68-185">Confira também</span><span class="sxs-lookup"><span data-stu-id="18d68-185">See also</span></span>

[<span data-ttu-id="18d68-186">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="18d68-186">New-CsRgsQueue</span></span>](/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="18d68-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="18d68-187">Set-CsRgsQueue</span></span>](/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="18d68-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="18d68-188">New-CsRgsPrompt</span></span>](/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="18d68-189">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="18d68-189">New-CsRgsCallAction</span></span>](/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="18d68-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="18d68-190">Get-CsRgsQueue</span></span>](/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="18d68-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="18d68-191">Import-CsRgsAudioFile</span></span>](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="18d68-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="18d68-192">Remove-CsRgsQueue</span></span>](/powershell/module/skype/remove-csrgsqueue?view=skype-ps)