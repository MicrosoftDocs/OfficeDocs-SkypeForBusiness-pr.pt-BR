---
title: Pesquisar logs de captura criados para o Serviço de Registro em Log no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Resumo: saiba como Pesquisar e ler logs de captura de serviço de log centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: 81bf539c6a06c52354db23bbeea97fb9525cbbd5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274370"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="28c73-103">Pesquisar logs de captura criados para o Serviço de Registro em Log no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="28c73-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="28c73-104">**Resumo:** Saiba como Pesquisar e ler logs de captura de serviço de log centralizado no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="28c73-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="28c73-105">Os recursos de pesquisa do serviço de log centralizado são úteis e eficientes pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="28c73-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="28c73-106">Sua pesquisa e os resultados correspondentes são executados em um único computador, em um escopo de pool, site ou global, com base no critério que você definir.</span><span class="sxs-lookup"><span data-stu-id="28c73-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="28c73-107">Suas pesquisas podem ser iniciadas de forma ampla e reduzidas para um critério mais definido como hora, componente ou computador.</span><span class="sxs-lookup"><span data-stu-id="28c73-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="28c73-108">Você pesquisa nos mesmos logs e não precisa executar uma sessão de log novamente quando os critérios de pesquisa são alterados.</span><span class="sxs-lookup"><span data-stu-id="28c73-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="28c73-p102">Os resultados da sua pesquisa são reunidos de todos os computadores e pools no escopo, coletados e agregados em um único arquivo de resultados que representa todos os resultados do critério de pesquisa (limitado para cenários em execução e os dados capturados pelos cenários). Você usa ferramentas conhecidas, como o **Snooper** ou o **Bloco de notas**, para ler o arquivo de resultados e rastrear mensagens pela sua implantação.</span><span class="sxs-lookup"><span data-stu-id="28c73-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="28c73-p103">O CLSAgent em cada computador cria os logs com base no cenário ou cenários (dois cenários por computador podem estar funcionando em um determinado momento). Os logs e seu índice e arquivos de cache associados são gerenciados pelo CLSAgent. Ao definir e executar uma pesquisa, o comando de pesquisa instrui o CLSAgent sobre qual informação deve ser recuperada. O CLSAgent executa a consulta nos arquivos de log, arquivos de cache e arquivos de índice e coloca-os na ordem de tempo delta, entrada mais antiga primeiro e continuando para a última entrada mais recente. O CLSController agrega (combina) os logs e os coloca na ordem de tempo delta, da entrada mais antiga para a entrada mais recente.</span><span class="sxs-lookup"><span data-stu-id="28c73-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="28c73-117">Após cada pesquisa, o cmdlet **Sync-CsClsLogging** é executado e descarrega o cache usado pelas pesquisas (não deve ser confundido com os arquivos de cache mantidos pelo CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="28c73-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="28c73-118">Descarregar o cache ajuda a garantir que há um log limpo e um armazenamento de captura de arquivo de rastreamento no CLSController para a próxima operação de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="28c73-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="28c73-119">Para aproveitar ao máximo o serviço de registro centralizado, você precisa de uma boa compreensão de como configurar a pesquisa para retornar apenas mensagens de rastreamento do computador e dos logs de pool que sejam relevantes para o problema que você está pesquisando.</span><span class="sxs-lookup"><span data-stu-id="28c73-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="28c73-120">problemas</span><span class="sxs-lookup"><span data-stu-id="28c73-120">issues</span></span>
  
<span data-ttu-id="28c73-121">Para executar as funções de pesquisa de serviço de log centralizado usando o Shell de gerenciamento do Skype for Business Server, você deve ser membro do grupo de segurança CsAdministrator ou do controle de acesso baseado em função do CsServerAdministrator (RBAC) ou uma função RBAC personalizada que contenha um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="28c73-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="28c73-122">Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no Shell de gerenciamento do Skype for Business Server ou no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="28c73-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="28c73-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="28c73-123">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="28c73-124">O lembrete deste tópico se concentra em como definir uma pesquisa para otimizar sua resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="28c73-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="28c73-125">Para executar uma pesquisa básica usando o serviço de log centralizado</span><span class="sxs-lookup"><span data-stu-id="28c73-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="28c73-126">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="28c73-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="28c73-127">Verifique se você tem o cenário AlwaysOn em execução na sua implantação no escopo global e digite o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="28c73-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="28c73-128">Por padrão, o Search-CsClsLogging envia os resultados da pesquisa para o console.</span><span class="sxs-lookup"><span data-stu-id="28c73-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="28c73-129">Se você quiser salvar os resultados da pesquisa em um arquivo, use o _ \<caminho\>de arquivo totalmente qualificado da cadeia de caracteres_OutputFilePath.</span><span class="sxs-lookup"><span data-stu-id="28c73-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="28c73-130">Para definir o parâmetro-OutputFilePath, forneça um caminho e um nome de arquivo como parte do parâmetro em um formato de cadeia de caracteres entre aspas (por exemplo; C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="28c73-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="28c73-131">Neste exemplo, é necessário garantir que o diretório C:\LogFiles existe e que você tem permissões para arquivos de Leitura e Gravação (permissão NTFS Modificar) na pasta.</span><span class="sxs-lookup"><span data-stu-id="28c73-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="28c73-132">O resultado é anexado, não substituído.</span><span class="sxs-lookup"><span data-stu-id="28c73-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="28c73-133">Se você precisa separar arquivos, defina um nome de arquivo diferente para cada pesquisa.</span><span class="sxs-lookup"><span data-stu-id="28c73-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="28c73-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="28c73-134">For example:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="28c73-135">Para executar uma pesquisa básica em um pool ou computador usando o serviço de log centralizado</span><span class="sxs-lookup"><span data-stu-id="28c73-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="28c73-136">Para limitar a pesquisa a um grupo ou computador específico, use o parâmetro-Computers com o computador definido por um nome totalmente qualificado do computador, entre aspas e separado por uma vírgula da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="28c73-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="28c73-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="28c73-137">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="28c73-138">Para pesquisar mais de um computador, digite vários nomes do computador entre aspas e separados por vírgulas, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="28c73-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="28c73-139">Se você precisar pesquisar um pool inteiro em vez de um único computador, altere o parâmetro-Computers para pools, remova o nome do computador e substitua-o pelo pool ou pools entre aspas separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="28c73-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="28c73-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="28c73-140">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="28c73-141">Ao usar os comandos de pesquisa, os pools podem ser qualquer pool na sua implantação, como grupos de front-end, pools de borda, pools de servidores de chat persistentes ou outros definidos como um pool na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="28c73-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="28c73-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="28c73-142">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="28c73-143">Para executar uma pesquisa usando parâmetros de tempo</span><span class="sxs-lookup"><span data-stu-id="28c73-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="28c73-144">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="28c73-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="28c73-145">Por padrão, o horário inicial para os parâmetros de tempo específico da pesquisa é 25 minutos antes da hora que você iniciar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="28c73-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="28c73-146">Em outras palavras, se pesquisarmos às 16:00 horas, a hora de início da pesquisa exibirá 15:35 a 16:05.</span><span class="sxs-lookup"><span data-stu-id="28c73-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="28c73-147">Se você precisar pesquisar 60 minutos ou 3 horas antes do tempo atual, use o parâmetro-StartTime e defina a cadeia de caracteres de data e hora para indicar o tempo que você deseja que a pesquisa comece.</span><span class="sxs-lookup"><span data-stu-id="28c73-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="28c73-148">Por exemplo, ao usar-StartTime e-EndTime para definir um intervalo de tempo e data, você pode definir uma pesquisa entre 8 AM e 9 no 11/20/2012 em seu pool.</span><span class="sxs-lookup"><span data-stu-id="28c73-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="28c73-149">É possível definir o caminho de resultado para gravar os resultados em um arquivo chamado c:\logfile.txt como a seguir:</span><span class="sxs-lookup"><span data-stu-id="28c73-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="28c73-150">A sequência data e hora que você especificar pode ser “data hora” ou “hora data”.</span><span class="sxs-lookup"><span data-stu-id="28c73-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="28c73-151">"O comando analisará a cadeia de caracteres e usará os valores apropriados para data e hora e suas configurações de localidade e cultura no computador do qual você está executando o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="28c73-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="28c73-152">Se você quiser recuperar logs começando em 11:00:00 AM no 11/20/2012, defina-StartTime.</span><span class="sxs-lookup"><span data-stu-id="28c73-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="28c73-153">O intervalo de tempo padrão para a pesquisa é de 30 minutos, a menos que você defina uma EndTime específica.</span><span class="sxs-lookup"><span data-stu-id="28c73-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="28c73-154">A pesquisa resultante retornará logs do computador ou pools definidos de 11:00 horas a 11:30 horas.</span><span class="sxs-lookup"><span data-stu-id="28c73-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="28c73-155">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="28c73-155">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="28c73-156">Para conduzir uma pesquisa de logs em um período específico de tempo, defina a-StartTime e uma-EndTime.</span><span class="sxs-lookup"><span data-stu-id="28c73-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="28c73-157">Você precisa de logs de 13:00 horas às 14:45 horas no computador edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="28c73-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="28c73-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="28c73-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="28c73-159">Para executar uma pesquisa avançada usando outro critério e opções correspondentes</span><span class="sxs-lookup"><span data-stu-id="28c73-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="28c73-160">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="28c73-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="28c73-161">Para executar um comando para coletar rastreamentos de componentes específicos, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="28c73-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="28c73-162">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="28c73-162">For example:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="28c73-163">A pesquisa resultante retorna todas as entradas de log com componentes de rastreamento para SIPStack, S4 e UserServices em todos os computadores e pools na sua implantação pelos últimos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="28c73-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="28c73-164">Para limitar a pesquisa com os mesmos componentes para apenas o pool de front-end chamado pool01.contoso.net, digite:</span><span class="sxs-lookup"><span data-stu-id="28c73-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="28c73-165">A lógica de pesquisa padrão para comando com vários parâmetros é usar o OR lógico com cada um dos parâmetros definidos.</span><span class="sxs-lookup"><span data-stu-id="28c73-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="28c73-166">Você pode alterar esse comportamento especificando o parâmetro **-MatchAll** .</span><span class="sxs-lookup"><span data-stu-id="28c73-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="28c73-167">Para fazer isso, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="28c73-167">To do this, type the following:</span></span>
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="28c73-p114">Se seus cenários estão definidos para ser executado constantemente, como AlwaysOn, ou se definiu logs do cenário de longa execução podem sair da máquina local em um compartilhamento de arquivos. Você define o compartilhamento de arquivos usando o parâmetro CacheFileNetworkFolder usando New-CsClsConfiguration para criar uma nova configuração ou modificar uma configuração existente com Set-CsClsConfiguration. Se você não deseja que a pesquisa inclua o compartilhamento de arquivos no conjunto de logs para pesquisar, use o parâmetro SkipNetworkLogs como a seguir:</span><span class="sxs-lookup"><span data-stu-id="28c73-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="28c73-171">Lendo registros de captura do Serviço de Registro em Log</span><span class="sxs-lookup"><span data-stu-id="28c73-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="28c73-172">Você percebe o verdadeiro benefício do serviço de registro centralizado depois de executar a pesquisa e tem um arquivo que pode ser usado para rastrear um problema relatado.</span><span class="sxs-lookup"><span data-stu-id="28c73-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="28c73-173">Há várias maneiras de ler o arquivo.</span><span class="sxs-lookup"><span data-stu-id="28c73-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="28c73-174">O arquivo de saída está em um formato de texto padrão e você pode usar o notepad. exe ou qualquer outro programa que permita a abertura e leitura de um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="28c73-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="28c73-175">Para arquivos maiores e problemas mais complexos, você pode usar uma ferramenta como o Snooper. exe projetado para ler e analisar a saída de log do serviço de log centralizado.</span><span class="sxs-lookup"><span data-stu-id="28c73-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="28c73-176">O Snooper está incluído nas ferramentas de depuração que estão disponíveis como um download separado.</span><span class="sxs-lookup"><span data-stu-id="28c73-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="28c73-177">Você pode baixar as ferramentas de depuração aqui [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257):.</span><span class="sxs-lookup"><span data-stu-id="28c73-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="28c73-178">Quando você instala as ferramentas de depuração, pequenos atalhos e itens de menu não são criados.</span><span class="sxs-lookup"><span data-stu-id="28c73-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="28c73-179">Após instalar as ferramentas de depuração, abra o Windows Explorer, uma janela de linha de comando ou o Shell de gerenciamento do Skype for Business Server e acesse o diretório (local padrão) C:\Program Files\Skype for Business Server 2015 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="28c73-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="28c73-180">Clique duas vezes em Espionador. exe ou digite Snooper. exe e pressione ENTER se estiver usando a linha de comando ou o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="28c73-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="28c73-181">A intenção deste tópico não é detalhar e discutir técnicas de resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="28c73-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="28c73-182">A resolução de problemas e os processos relacionados é um assunto complexo.</span><span class="sxs-lookup"><span data-stu-id="28c73-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="28c73-183">Para obter detalhes sobre como solucionar problemas de noções básicas e solucionar problemas de cargas de trabalho específicas, consulte o [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)Microsoft Lync Server 2010 Resource Kit book.</span><span class="sxs-lookup"><span data-stu-id="28c73-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="28c73-184">Os processos e procedimentos ainda se aplicam ao Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="28c73-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="28c73-185">Para abrir um arquivo de log no Snooper</span><span class="sxs-lookup"><span data-stu-id="28c73-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="28c73-p117">Para usar o Snooper e abrir arquivos de log, você precisará de acesso de leitura aos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="28c73-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="28c73-188">Após a instalação das ferramentas de depuração (LyncDebugTools.msi), mude o diretório para o local do Snooper.exe usando o Windows Explorer ou na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="28c73-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="28c73-189">Por padrão, as ferramentas de depuração estão localizadas em C:\Program Files\Skype for Business Server 2015 \ ferramentas de depuração.</span><span class="sxs-lookup"><span data-stu-id="28c73-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="28c73-190">Clique duas vezes ou execute Snooper.exe.</span><span class="sxs-lookup"><span data-stu-id="28c73-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="28c73-191">Após o Snooper estar aberto, clique com o botão direito em **Arquivo**, clique em **Abrir arquivo**, encontre seus arquivos de registro, selecione um arquivo na caixa de diálogo **Abrir** e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="28c73-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="28c73-192">As mensagens de **rastreamento** do arquivo de log são exibidas na guia **rastrear** . Clique na guia **mensagens** para exibir o conteúdo das mensagens dos rastreamentos coletados.</span><span class="sxs-lookup"><span data-stu-id="28c73-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="28c73-193">Para exibir um fluxograma da chamada</span><span class="sxs-lookup"><span data-stu-id="28c73-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="28c73-p119">Para usar o Snooper e abrir arquivos de log, você precisa de acesso de leitura dos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você precisará ser um membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um destes dois grupos.</span><span class="sxs-lookup"><span data-stu-id="28c73-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="28c73-196">Abra um arquivo de log e clique na guia **Mensagens**, selecione uma conversa na exibição de mensagens ou selecione um componente de rastreamento na guia **Rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="28c73-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="28c73-197">Clique em **Fluxo de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="28c73-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="28c73-198">Se você clicar em uma mensagem ou um rastreamento que não faz parte de um fluxo de chamadas, o diagrama não será exibido e uma mensagem de status será exibida na parte inferior da Snooper informando que "esta mensagem não está qualificada para callfow".</span><span class="sxs-lookup"><span data-stu-id="28c73-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="28c73-199">Escolha outra mensagem ou rastreamento e o fluxo de chamadas aparecerá se a mensagem ou o rastreamento faz parte de um fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="28c73-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="28c73-200">Mova pelas Mensagens ou linhas de Rastreamento e observe se o fluxograma de chamada atualiza ou muda para exibir um novo diagrama.</span><span class="sxs-lookup"><span data-stu-id="28c73-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="28c73-201">Passe sobre os elementos para obter informações sobre mensagens de chamada, pontos de extremidade e outros componentes.</span><span class="sxs-lookup"><span data-stu-id="28c73-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
