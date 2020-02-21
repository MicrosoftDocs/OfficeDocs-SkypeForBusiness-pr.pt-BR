---
title: 'Lync Server 2013: criar ou modificar uma fila'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b805553349e6958671bc024cb862b296b74fc697
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="10cdb-102">Criar ou modificar uma fila no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10cdb-102">Create or modify a queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10cdb-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="10cdb-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="10cdb-104">Use um dos seguintes procedimentos para criar ou modificar uma fila.</span><span class="sxs-lookup"><span data-stu-id="10cdb-104">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="10cdb-105">Para usar o painel de controle do Lync Server para criar ou modificar uma fila</span><span class="sxs-lookup"><span data-stu-id="10cdb-105">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="10cdb-106">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="10cdb-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10cdb-107">Se você for um dos Gerentes de grupo de resposta delegados para um fluxo de trabalho gerenciado, é possível criar ou modificar filas de grupo de resposta e atribuí-las aos fluxos de trabalho gerenciados.</span><span class="sxs-lookup"><span data-stu-id="10cdb-107">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="10cdb-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="10cdb-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="10cdb-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="10cdb-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="10cdb-110">Na barra de navegação esquerda, clique em **Grupos de Resposta** e clique em **Fila**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-110">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="10cdb-111">Na página **Fila**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="10cdb-111">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="10cdb-112">Para criar uma nova fila, clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-112">To create a new queue, click **New**.</span></span> <span data-ttu-id="10cdb-113">Em **Selecionar um serviço**, digite uma parte ou o nome inteiro do serviço do **ApplicationServer** onde deseja adicionar a fila no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="10cdb-113">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="10cdb-114">Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="10cdb-p103">Para modificar uma fila existente, digite uma parte ou o nome inteiro da fila no campo de pesquisa. Na lista resultante de filas, clique na fila que você deseja, em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="10cdb-117">Em **Nome**, digite um nome identificador para a fila.</span><span class="sxs-lookup"><span data-stu-id="10cdb-117">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="10cdb-118">Em **Descrição**, digite uma descrição para a fila.</span><span class="sxs-lookup"><span data-stu-id="10cdb-118">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="10cdb-p104">Em **Grupos**, especifique os grupos que você deseja atribuir à fila. Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="10cdb-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span>
    
      - <span data-ttu-id="10cdb-p105">Para adicionar um grupo à fila, clique em **Selecionar**. No campo de pesquisa **Selecionar grupos**, digite o parte ou o nome inteiro do grupo de agentes que você deseja atribuir à fila, clique no grupo de agentes desejado e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="10cdb-123">Para remover um grupo da fila, na lista de grupos de agentes, clique no grupo que você deseja remover e em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-123">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="10cdb-124">Para alterar a ordem em que os agentes são pesquisados, na lista de grupos de agentes, clique em um grupo e na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="10cdb-124">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="10cdb-p106">Quando o servidor pesquisa por um agente disponível para a fila, ele usa a ordem do grupo. Ou seja, o primeiro grupo da lista é pesquisado primeiro, seguido pelo segundo e assim sucessivamente.</span><span class="sxs-lookup"><span data-stu-id="10cdb-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="10cdb-127">Para especificar um período máximo de tempo para um chamador aguardar em espera antes que um agente responda à chamada, marque a caixa de seleção **Habilitar o tempo limite da fila** e, em seguida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="10cdb-127">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="10cdb-128">Em **Período de tempo limite (segundos)**, especifique o número máximo de segundos que um chamador aguarda antes de um agente responder à chamada.</span><span class="sxs-lookup"><span data-stu-id="10cdb-128">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="10cdb-129">Em **Ação de Chamada**, selecione a ação que ocorre quando o tempo limite de uma chamada se esgota da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="10cdb-129">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="10cdb-130">Para desconectar a chamada após o tempo limite, clique em **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-130">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="10cdb-131">Para encaminhar a chamada para caixa postal, clique em **encaminhar para caixa postal**e, em seguida, no campo **endereço SIP** , digite um endereço de caixa postal\<no\>@\<formato SIP:\> username DomainName (por exemplo, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="10cdb-131">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="10cdb-132">Para encaminhar a chamada para outro número de telefone, clique em **encaminhar para número de telefone**e, no campo **endereço SIP** , digite o número de telefone no\<formato\>@\<SIP: Number\> DomainName (por exemplo, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="10cdb-132">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="10cdb-133">Para encaminhar a chamada para outro usuário, clique em **encaminhar para endereço SIP**e, no campo **endereço SIP** , digite o URI para o usuário no formato SIP:\<username\>@\<DomainName\>.</span><span class="sxs-lookup"><span data-stu-id="10cdb-133">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="10cdb-134">Para encaminhar a chamada para outra fila de espera, clique em **Encaminhar para outra fila** e, em seguida, procure na fila a ser usada.</span><span class="sxs-lookup"><span data-stu-id="10cdb-134">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="10cdb-135">Para especificar um número máximo de chamadas que a fila de espera poderá conter, marque a caixa de seleção **Habilitar o estouro da fila** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="10cdb-135">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="10cdb-136">Em **Número máximo de chamadas**, selecione o número máximo de chamadas que a fila de espera conterá.</span><span class="sxs-lookup"><span data-stu-id="10cdb-136">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="10cdb-137">Em **Encaminhar a chamada**, selecione qual chamada será encaminhada quando a fila estiver cheia: **Chamada Mais Recente** ou **Chamada Mais Antiga**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-137">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="10cdb-138">Em **Ação de chamada**, selecione a ação que ocorre quando o limite de excedente é atingido da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="10cdb-138">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="10cdb-139">Para desconectar a chamada após o tempo limite, clique em **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-139">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="10cdb-140">Para encaminhar a chamada para caixa postal, clique em **encaminhar para caixa postal**e, em seguida, no campo **endereço SIP** , digite um endereço de caixa postal\<no\>@\<formato SIP:\> username DomainName (por exemplo, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="10cdb-140">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="10cdb-141">Para encaminhar a chamada para outro número de telefone, clique em **encaminhar para número de telefone**e, no campo **endereço SIP** , digite o número de telefone no\<formato\>@\<SIP: Number\> DomainName (por exemplo, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="10cdb-141">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="10cdb-142">Para encaminhar a chamada para outro usuário, clique em **encaminhar para endereço SIP**e, no campo **endereço SIP** , digite o URI para o usuário no formato SIP:\<username\>@\<DomainName\>.</span><span class="sxs-lookup"><span data-stu-id="10cdb-142">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="10cdb-143">Para encaminhar a chamada para outra fila de espera, clique em **Encaminhar para outra fila** e, em seguida, procure na fila a ser usada.</span><span class="sxs-lookup"><span data-stu-id="10cdb-143">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="10cdb-144">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="10cdb-145">Para usar o Windows PowerShell para criar ou modificar uma fila</span><span class="sxs-lookup"><span data-stu-id="10cdb-145">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="10cdb-146">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="10cdb-146">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10cdb-147">Se você for um dos Gerentes do grupo de resposta designado para um fluxo de trabalho gerenciado, será possível criar grupos de agentes e filas, bem como atribuir grupos de agentes a filas.</span><span class="sxs-lookup"><span data-stu-id="10cdb-147">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="10cdb-148">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="10cdb-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="10cdb-p107">Crie o prompt para que seja reproduzido quando o limite de tempo da fila é atingido e salve-o em um variável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="10cdb-p107">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="10cdb-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="10cdb-151">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10cdb-152">Para usar um arquivo de áudio no prompt, use o cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="10cdb-152">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="10cdb-153">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="10cdb-153">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="10cdb-p109">Defina a ação que será executada quando o limite de tempo da fila for atingido e salve-o em um variável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="10cdb-p109">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10cdb-156">Para obter detalhes sobre as ações possíveis e sua sintaxe, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="10cdb-156">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="10cdb-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="10cdb-157">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="10cdb-p110">Crie o prompt que será reproduzido quando o limite de excedente da fila for atingido e salve-o em uma variável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="10cdb-p110">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="10cdb-160">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="10cdb-160">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10cdb-161">Para usar um arquivo de áudio no prompt, use o cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="10cdb-161">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="10cdb-162">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="10cdb-162">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="10cdb-p112">Defina a ação que será executada quando o limite de excedente da fila for atingido e salve-o em uma variável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="10cdb-p112">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10cdb-165">Para obter detalhes sobre as ações possíveis e sua sintaxe, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="10cdb-165">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="10cdb-166">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="10cdb-166">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="10cdb-167">Recupere o nome do serviço do serviço de Grupo de resposta e atribua-o a uma variável.</span><span class="sxs-lookup"><span data-stu-id="10cdb-167">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="10cdb-168">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="10cdb-168">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="10cdb-169">Obtenha a identidade do grupo de agente que será atribuído à fila.</span><span class="sxs-lookup"><span data-stu-id="10cdb-169">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="10cdb-170">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="10cdb-170">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10cdb-171">Para obter detalhes sobre como criar o grupo de agentes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span><span class="sxs-lookup"><span data-stu-id="10cdb-171">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="10cdb-p115">Crie a fila. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="10cdb-p115">Create the queue. At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="10cdb-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="10cdb-174">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="10cdb-p116">Confirme se a fila foi criada. Execute:</span><span class="sxs-lookup"><span data-stu-id="10cdb-p116">Confirm that the queue is created. Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10cdb-177">Confira também</span><span class="sxs-lookup"><span data-stu-id="10cdb-177">See Also</span></span>


[<span data-ttu-id="10cdb-178">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="10cdb-178">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="10cdb-179">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="10cdb-179">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="10cdb-180">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="10cdb-180">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="10cdb-181">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="10cdb-181">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="10cdb-182">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="10cdb-182">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="10cdb-183">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="10cdb-183">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="10cdb-184">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="10cdb-184">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

