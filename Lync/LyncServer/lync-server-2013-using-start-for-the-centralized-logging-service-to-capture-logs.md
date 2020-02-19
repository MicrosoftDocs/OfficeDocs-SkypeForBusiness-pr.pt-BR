---
title: Usando iniciar para o serviço de registro em log centralizado para capturar logs
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ef2900d66796ec261e7abd9c8c6d910eb6c0e81
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="d862f-102">Usando iniciar para o serviço de registro em log centralizado para capturar logs no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d862f-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d862f-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d862f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d862f-104">Para capturar logs de rastreamento usando o serviço de registro em log centralizado, emita um comando para começar a fazer logon em um ou mais computadores e pools.</span><span class="sxs-lookup"><span data-stu-id="d862f-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="d862f-105">Você também emite parâmetros que definem quais computadores ou pools, quais cenários serão executados (por exemplo, AlwaysOn, outro cenário predefinido ou um cenário que você tenha criado), quais componentes do Lync Server (por exemplo, S4, SipStack) devem ser rastreados.</span><span class="sxs-lookup"><span data-stu-id="d862f-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="d862f-106">Para capturar as informações corretas, você precisa ter certeza de que usa o cenário certo para coletar informações relevantes para o problema.</span><span class="sxs-lookup"><span data-stu-id="d862f-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="d862f-107">No serviço de registro em log centralizado, um cenário é o conceito de ativar o registro em log com base em uma coleção de componentes de servidor, níveis de log e sinalizadores, que é muito mais eficiente e útil do que ter de definir esses elementos em uma base por servidor.</span><span class="sxs-lookup"><span data-stu-id="d862f-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="d862f-108">Você define e especifica um cenário a ser executado e o cenário é executado de forma consistente em todos os servidores e pools no escopo da infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="d862f-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="d862f-p103">O cenário padrão é chamado de **AlwaysOn**. O objetivo do AlwaysOn é executar o cenários constantemente, conforme o nome do cenário implica. O cenário AlwaysOn coleta informações de nível informativo (obeserve que o nível de log informativo inclui Fatal, Erro e Aviso, além das mensagens informativas) para boa parte da maioria dos componentes de servidor comum. AlwaysOn coleta informções antes, durante e após o problema ocorrer. Isso difere drasticamente do comportamento típico das ferramentas de log anteriores, tais como OCSLogger. É possível executar OCSLogger após o problema ocorrer, tornando seus eforços para resolução de problemas mais dificil, pois os dados que você possui são reativos e não proativos. Se AlwaysOn não possui a informação que você está procurando a fim de indicar o componente do problema e um curso de ação para corrigi-lo (o que provavelmente não fornece a amplitude e profundidade dos provedores em AlwaysOn), ele indicará um nível adequado de informação para determinar o que mais dee ser feito, como criar um novo cenário, juntar outras informações, realizar uma busca diferente para coletar informações mais detalhadas, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d862f-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="d862f-116">O serviço de registro centralizado fornece duas maneiras de emitir comandos.</span><span class="sxs-lookup"><span data-stu-id="d862f-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="d862f-117">Vários tópicos têm ênfase detalhada no uso do Windows PowerShell por meio do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d862f-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="d862f-118">A capacidade de usar várias configurações e comandos complexos favorece o Windows PowerShell para o uso de serviço de registro em log centralizado.</span><span class="sxs-lookup"><span data-stu-id="d862f-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="d862f-119">Como o Windows PowerShell através do Shell de gerenciamento do Lync Server é praticamente onipresente para todas as funções no Lync Server, somente os comandos do Windows PowerShell são discutidos.</span><span class="sxs-lookup"><span data-stu-id="d862f-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d862f-120">Se você decidir usar o conjunto de comandos limitado disponível na linha de comando, poderá obter ajuda com o CLSController. exe digitando <CODE>ClsController.exe</CODE>.</span><span class="sxs-lookup"><span data-stu-id="d862f-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="d862f-121">Por padrão, o <STRONG>ClsController. exe</STRONG> é instalado no diretório C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent.</span><span class="sxs-lookup"><span data-stu-id="d862f-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="d862f-122">Para executar Start-CsClsLogging com o Windows PowerShell usando comandos básicos</span><span class="sxs-lookup"><span data-stu-id="d862f-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="d862f-123">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d862f-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d862f-124">Inicie um cenário de registro em log com o serviço de registro em log centralizado digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d862f-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="d862f-125">Por exemplo, para iniciar o cenário **AlwaysOn**, digite:</span><span class="sxs-lookup"><span data-stu-id="d862f-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d862f-126">O cenário The AlwaysOn não possui uma duração padrão.</span><span class="sxs-lookup"><span data-stu-id="d862f-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="d862f-127">Este cenário será executado até que o pare precisamente com o cmdlet <STRONG>Stop-CsClsLogging</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d862f-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="d862f-128">Para detalhes, consulte <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="d862f-128">For details, see <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="d862f-129">Para todos os outros cenários, a duração padrão é 4 horas.</span><span class="sxs-lookup"><span data-stu-id="d862f-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="d862f-130">Pressione Enter para executar o comenando.</span><span class="sxs-lookup"><span data-stu-id="d862f-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d862f-131">Pode levar algum tempo (30 a 60 segundos) para que os os comandos sejam executados e que recebam o status de volta dos computadores em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d862f-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="d862f-132">![Executando Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Executando Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="d862f-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="d862f-133">Para iniciar outro cenários, use o cmdlet **Start-CsClsLogging** com o nome do cenário adicional para executar o seguinte (por exemplo, o cenário **Autenticação**):</span><span class="sxs-lookup"><span data-stu-id="d862f-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d862f-134">É possível ter um total de dois cenários sendo executados em qualquer computador a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="d862f-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="d862f-135">Se o comando é global no escopo, todos os computadores em sua implantação executarão o cenário ou cenários.</span><span class="sxs-lookup"><span data-stu-id="d862f-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="d862f-136">Para iniciar um terceiro cenário, você deve parar o log no computador, pool, site ou escopo global em que você queira executar o novo cenario.</span><span class="sxs-lookup"><span data-stu-id="d862f-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="d862f-137">Caso tenho iniciado um escopo global, é possível parar o log em um ou ambos cenários em um ou mais computadores e pools.</span><span class="sxs-lookup"><span data-stu-id="d862f-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="d862f-138">Para obter detalhes sobre o gerenciamento de cenários que estão sendo executados, consulte <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">usando parar para o serviço de registro em log centralizado no Lync Server 2013</A> e <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">parar-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="d862f-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="d862f-139">Para executar Start-CsClsLogging com o Windows PowerShell usando comandos avançados</span><span class="sxs-lookup"><span data-stu-id="d862f-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="d862f-140">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d862f-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d862f-141">Parâmetros adicionais estão disponíveis para gerenciar os comandos de log.</span><span class="sxs-lookup"><span data-stu-id="d862f-141">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="d862f-142">É possível usar  –Duração para ajustar o tempo em que o cenário será executado.</span><span class="sxs-lookup"><span data-stu-id="d862f-142">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="d862f-143">Também é possível definir –Computadores, uma lista de nomes de domínios completamente qualificados de computadores (FQDNs) separados por vírgula, ou –Pools, uma lista separada por vírgula de FQDNs para pools que você queira executar o log.</span><span class="sxs-lookup"><span data-stu-id="d862f-143">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="d862f-144">Você inicia uma sessão de registro em log para o cenário *Userreplicator* no pool "pool01.contoso.net".</span><span class="sxs-lookup"><span data-stu-id="d862f-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="d862f-145">Você também define a duração da sessão de log em 8 horas.</span><span class="sxs-lookup"><span data-stu-id="d862f-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="d862f-146">Para isso, digite:</span><span class="sxs-lookup"><span data-stu-id="d862f-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="d862f-147">O execução com sucesso deste cenário devolve um resultado como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d862f-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="d862f-148">![Executando Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Executando Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="d862f-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="d862f-149">Observe que neste exemplo, o cenário AlwaysOn é executado e o cenário UserReplicator também está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="d862f-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d862f-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="d862f-150">See Also</span></span>


[<span data-ttu-id="d862f-151">Visão geral do serviço de registro em log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d862f-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

