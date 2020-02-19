---
title: Usando a pesquisa nos logs de captura criados pelo serviço de registro em log centralizado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ca895f455d8da3f6e8edd2e80aacc8a082d147
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="9a640-102">Usando a pesquisa nos logs de captura criados pelo serviço de registro em log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a640-102">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a640-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9a640-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9a640-104">Os recursos de pesquisa do serviço de registro em log centralizado são úteis e eficientes pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="9a640-104">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="9a640-105">Sua pesquisa e seus resultados são executados em um único computador, em um escopo de grupo, site ou global, com base no critério que você definir.</span><span class="sxs-lookup"><span data-stu-id="9a640-105">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="9a640-p101">Suas pesquisas podem ser iniciadas de forma ampla e reduzidas para um critério mais definido como hora, componente ou computador. Você pesquisa nos mesmos registros e não precisa executar uma sessão de registro em log novamente quando o critério de pesquisa mudar.</span><span class="sxs-lookup"><span data-stu-id="9a640-p101">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer. You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="9a640-p102">Os resultados da sua pesquisa são reunidos de todos os computadores e pools no escopo, coletados e agregados em um único arquivo de resultados que representa todos os resultados do critério de pesquisa (limitado para cenários em execução e os dados capturados pelos cenários). Você usa ferramentas familiares como o **Snooper** ou o **Bloco de notas** para ler o arquivo de resultados e rastrear mensagens pela sua implantação.</span><span class="sxs-lookup"><span data-stu-id="9a640-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="9a640-p103">O CLSAgent em cada computador cria os logs com base no cenário ou cenários (dois cenários por computador podem estar funcionando em um determinado momento). Os logs e seu índice e arquivos de cache associados são gerenciados pelo CLSAgent. Ao definir e executar uma pesquisa, o comando de pesquisa instrui o CLSAgent sobre qual informação deve ser recuperada. O CLSAgent executa a consulta nos arquivos de log, arquivos de cache e arquivos de índice e coloca-os na ordem de tempo delta, entrada mais antiga primeiro e continuando para a última entrada mais recente. O CLSController agrega (combina) os logs e os coloca na ordem de tempo delta, entrada mais antiga primeiro e continuando para a última entrada mais recente.</span><span class="sxs-lookup"><span data-stu-id="9a640-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="9a640-116">Após cada pesquisa, o cmdlet **Sync-CsClsLogging** é executado e descarrega o cache usado pelas pesquisas (não deve ser confundido com os arquivos de cache mantidos pelo CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="9a640-116">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="9a640-117">Descarregar o cache ajuda a garantir que há um log limpo e um armazenamento de captura de arquivo de rastreamento no CLSController para a próxima operação de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9a640-117">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="9a640-118">Para aproveitar ao máximo o serviço de registro em log centralizado, você precisa de uma boa compreensão de como configurar a pesquisa para retornar apenas mensagens de rastreamento dos logs de computador e pool que são relevantes para o problema que você está pesquisando.</span><span class="sxs-lookup"><span data-stu-id="9a640-118">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="9a640-119">problemas</span><span class="sxs-lookup"><span data-stu-id="9a640-119">issues</span></span>

<span data-ttu-id="9a640-120">Para executar as funções de pesquisa do serviço de registro em log centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro dos grupos de segurança do controle de acesso baseado em função do CsAdministrator ou do CsServerAdministrator, ou uma função RBAC personalizada que contenha um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="9a640-120">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="9a640-121">Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou sozinho), execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a640-121">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="9a640-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9a640-122">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="9a640-123">O lembrete deste tópico se focaliza em como definir uma pesquisa para otimizar sua resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="9a640-123">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="9a640-124">Para executar uma pesquisa básica usando o serviço de registro em log centralizado</span><span class="sxs-lookup"><span data-stu-id="9a640-124">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="9a640-125">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9a640-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9a640-126">Certifique-se de ter o cenário AlwaysOn em execução na sua implantação no escopo global e digite o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="9a640-126">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9a640-127">Por padrão, o Search-CsClsLogging envia os resultados da pesquisa para o console.</span><span class="sxs-lookup"><span data-stu-id="9a640-127">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="9a640-128">Se você deseja salvar os resultados da pesquisa em um arquivo, use – caminho &lt;&gt;de arquivo totalmente qualificado de cadeia de caracteres OutputFilePath.</span><span class="sxs-lookup"><span data-stu-id="9a640-128">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="9a640-129">Para definir o parâmetro –OutputFilePath, ofereça um caminho e um nome de arquivo como parte do parâmetro em um formato de sequência entre aspas (por exemplo; C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="9a640-129">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="9a640-130">Neste exemplo, você deve garantir que o diretório C:\LogFiles exista e que você possui permissões para arquivos de Leitura e Gravação (permissão NTFS Modificar) na pasta.</span><span class="sxs-lookup"><span data-stu-id="9a640-130">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="9a640-131">O resultado é anexado e não é substituído.</span><span class="sxs-lookup"><span data-stu-id="9a640-131">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="9a640-132">Se você precisa separar arquivos, defina um nome de arquivo diferente para cada pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9a640-132">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="9a640-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9a640-133">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="9a640-134">Para executar uma pesquisa básica em um pool ou computador usando o serviço de registro em log centralizado</span><span class="sxs-lookup"><span data-stu-id="9a640-134">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="9a640-135">Para limiar a pesquisa para um pool ou computador específico, use o parâmetro –Computers com o computador definido por um nome totalmente qualificado do computador, entre aspas e separado por vírgulas, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="9a640-135">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="9a640-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9a640-136">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="9a640-137">Para pesquisar mais de um computador, digite vários nomes do computador entre aspas e separados por vírgulas, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9a640-137">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="9a640-138">Se você precisa pesquisar todo um pool ao invés de um único computador, altere o parâmetro –Computers para –Pools, remova o nome do computador e substitua com o pool ou pools entre aspas separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="9a640-138">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="9a640-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9a640-139">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="9a640-140">Ao usar os comandos de pesquisa, os pools podem ser qualquer pool em sua implantação, como pools de front-ends, pools de borda, pools de servidores de chat persistentes ou outros definidos como um pool em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="9a640-140">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="9a640-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9a640-141">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="9a640-142">Para executar uma pesquisa usando parâmetros de tempo</span><span class="sxs-lookup"><span data-stu-id="9a640-142">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="9a640-143">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9a640-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9a640-p108">Por padrão, o horário inicial para o parâmetro de tempo específico da pesquisa é 30 minutos antes da hora que você iniciar a pesquisa. Em outras palavras, se você iniciar sua pesquisa às 16:00 horas, irá pesquisar os registros dos computadores e pools que você definir de 15:30 horas as 16:00 horas. Se você precisa pesquisar 60 minutos ou 3 horas antes da hora atual, use o parâmetro –StartTime e defina a sequência de data e hora para indicar a hora que você deseja que a pesquisa inicie.</span><span class="sxs-lookup"><span data-stu-id="9a640-p108">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search. In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM. If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="9a640-147">Por exemplo, usando –StartTime e –EndTime para definir um intervalo de data e hora, é possível definir uma pesquisa entre 8 e 9 horas no dia 20/11/2012 em seu pool.</span><span class="sxs-lookup"><span data-stu-id="9a640-147">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="9a640-148">Você pode definir o caminho de saída para gravar os resultados em um arquivo denominado c\\: logfile. txt da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9a640-148">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9a640-149">A cadeia de hora e data que você especifica pode ser "data hora" ou "data de hora.</span><span class="sxs-lookup"><span data-stu-id="9a640-149">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="9a640-150">"O comando analisará a cadeia de caracteres e usará os valores apropriados para data e hora.</span><span class="sxs-lookup"><span data-stu-id="9a640-150">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="9a640-p111">Se você deseja recuperar os logs começando às 11:00 horas em 20/11/2012, você define –StartTime. O intervalo de hora padrão para a pesquisa é de 30 minutos, a não ser que você defina um –EndTime específico. A pesquisa resultante retornará logs do computador ou pools definidos de 11:00 horas a 11:30 horas.</span><span class="sxs-lookup"><span data-stu-id="9a640-p111">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime. The default time range for the search is 30 minutes unless you define a specific –EndTime. The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="9a640-154">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9a640-154">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="9a640-p112">Para conduzir uma pesquisa dos logs dentro de um período de tempo específico, defina –StartTime e –EndTime. Você precisa de logs de 13:00 horas às 14:45 horas no computador edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="9a640-p112">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime. You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="9a640-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9a640-157">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="9a640-158">Para executar uma pesquisa avançada usando outro critério e opções correspondentes</span><span class="sxs-lookup"><span data-stu-id="9a640-158">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="9a640-159">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9a640-159">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9a640-160">Para executar um comando para coletar rastreamentos de componentes específicos, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9a640-160">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="9a640-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9a640-161">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="9a640-162">A pesquisa resultante retorna todas as entradas de log com componentes de rastreamento para SIPStack, S4 e UserServices em todos os computadores e pools na sua implantação pelos últimos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="9a640-162">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="9a640-163">Para limitar a pesquisa com os mesmos componentes para apenas o seu pool de front-ends chamado pool01.contoso.net, digite:</span><span class="sxs-lookup"><span data-stu-id="9a640-163">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="9a640-p113">A lógica de pesquisa padrão para comando com vários parâmetros é usar o OR lógico com cada um dos parâmetros definidos. É possível alterar este comportamento especificando o parâmetro **–MatchAll**. Para fazer isso, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9a640-p113">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters. You can change this behavior by specifying the **–MatchAll** parameter. To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="9a640-p114">Se seus cenários estão definidos para ser executado constantemente, como AlwaysOn, ou se definiu logs do cenário de longa execução podem sair da máquina local em um compartilhamento de arquivos. Você define o compartilhamento de arquivos usando o parâmetro CacheFileNetworkFolder usando New-CsClsConfiguration para criar uma nova configuração ou modificar uma configuração existente com Set-CsClsConfiguration. Se você não deseja que a pesquisa inclua o compartilhamento de arquivos no conjunto de logs para pesquisar, use o parâmetro SkipNetworkLogs como a seguir:</span><span class="sxs-lookup"><span data-stu-id="9a640-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

