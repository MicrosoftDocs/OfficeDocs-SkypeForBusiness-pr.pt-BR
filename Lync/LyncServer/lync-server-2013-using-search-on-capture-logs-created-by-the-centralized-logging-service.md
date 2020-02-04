---
title: Usar a pesquisa em logs de captura criados pelo serviço de log centralizado
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
ms.openlocfilehash: edfc176934479aef04d6850a8ebbae3b38a553a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a>Usar a pesquisa em logs de captura criados pelo serviço de log centralizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Os recursos de pesquisa do serviço de log centralizado são úteis e eficientes pelos seguintes motivos:

  - Sua pesquisa e os resultados correspondentes são executados em um único computador, em um escopo de pool, site ou global, com base no critério que você definir.

  - Suas pesquisas podem ser iniciadas de forma ampla e reduzidas para um critério mais definido como hora, componente ou computador. Você pesquisa nos mesmos registros e não precisa executar uma sessão de registro em log novamente quando o critério de pesquisa mudar.

  - Os resultados da sua pesquisa são reunidos de todos os computadores e pools no escopo, coletados e agregados em um único arquivo de resultados que representa todos os resultados do critério de pesquisa (limitado para cenários em execução e os dados capturados pelos cenários). Você usa ferramentas conhecidas, como o **Snooper** ou o **Bloco de notas**, para ler o arquivo de resultados e rastrear mensagens pela sua implantação.

O CLSAgent em cada computador cria os logs com base no cenário ou cenários (dois cenários por computador podem estar funcionando em um determinado momento). Os logs e seu índice e arquivos de cache associados são gerenciados pelo CLSAgent. Ao definir e executar uma pesquisa, o comando de pesquisa instrui o CLSAgent sobre qual informação deve ser recuperada. O CLSAgent executa a consulta nos arquivos de log, arquivos de cache e arquivos de índice e coloca-os na ordem de tempo delta, entrada mais antiga primeiro e continuando para a última entrada mais recente. O CLSController agrega (combina) os logs e os coloca na ordem de tempo delta, da entrada mais antiga para a entrada mais recente.

Após cada pesquisa, o cmdlet **Sync-CsClsLogging** é executado e descarrega o cache usado pelas pesquisas (não deve ser confundido com os arquivos de cache mantidos pelo CLSAgent). Descarregar o cache ajuda a garantir que há um log limpo e um armazenamento de captura de arquivo de rastreamento no CLSController para a próxima operação de pesquisa.

Para aproveitar ao máximo o serviço de registro centralizado, você precisa de uma boa compreensão de como configurar a pesquisa para retornar apenas mensagens de rastreamento do computador e dos logs de pool que sejam relevantes para o problema que você está pesquisando. problemas

Para executar as funções de pesquisa de serviço de log centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro do grupo de segurança CsAdministrator ou do controle de acesso baseado em função do CsServerAdministrator (RBAC) ou uma função RBAC personalizada que contém qualquer um desses dois grupos. Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por exemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

O lembrete deste tópico se concentra em como definir uma pesquisa para otimizar sua resolução de problemas.

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Para executar uma pesquisa básica usando o serviço de log centralizado

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Verifique se você tem o cenário AlwaysOn em execução na sua implantação no escopo global e digite o seguinte no prompt de comando:
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > Por padrão, o Search-CsClsLogging envia os resultados da pesquisa para o console. Se você quiser salvar os resultados da pesquisa em um arquivo, use – caminho &lt;&gt;de arquivo totalmente qualificado de cadeia de caracteres OutputFilePath. Para definir o parâmetro –OutputFilePath, ofereça um caminho e um nome de arquivo como parte do parâmetro em um formato de sequência entre aspas (por exemplo: C:\LogFiles\SearchOutput.txt). Neste exemplo, é necessário garantir que o diretório C:\LogFiles existe e que você tem permissões para arquivos de Leitura e Gravação (permissão NTFS Modificar) na pasta. O resultado é anexado, não substituído. Se você precisa separar arquivos, defina um nome de arquivo diferente para cada pesquisa.

    
    </div>
    
    Por exemplo:
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Para executar uma pesquisa básica em um pool ou computador usando o serviço de log centralizado

1.  Para limitar a pesquisa para um pool ou computador específico, use o parâmetro –Computers com o computador definido por um nome totalmente qualificado do computador, entre aspas e separado por vírgulas, como a seguir:
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    Por exemplo:
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  Para pesquisar mais de um computador, digite vários nomes do computador entre aspas e separados por vírgulas, como o seguinte:
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  Se você precisa pesquisar todo um pool ao invés de um único computador, altere o parâmetro –Computers para –Pools, remova o nome do computador e substitua com o pool ou pools entre aspas separados por vírgulas.
    
    Por exemplo:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Ao usar os comandos de pesquisa, os pools podem ser qualquer pool na sua implantação, como grupos de front-end, pools de borda, pools de servidores de chat persistentes ou outros definidos como um pool na sua implantação.
    
    Por exemplo:
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a>Para executar uma pesquisa usando parâmetros de tempo

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Por padrão, a hora de início dos parâmetros específicos do tempo de pesquisa é de 30 minutos antes da hora em que você iniciar a pesquisa. Em outras palavras, se você iniciar a pesquisa em 4:00:00 PM, a pesquisa pesquisará os logs dos computadores e pools que você definir do 3:30:00 PM até 4:00:00 PM. Se você precisa pesquisar 60 minutos ou 3 horas antes da hora atual, use o parâmetro –StartTime e defina a sequência de data e hora para indicar a hora que você deseja que a pesquisa inicie.
    
    Por exemplo, usando –StartTime e –EndTime para definir um intervalo de data e hora, é possível definir uma pesquisa entre 8 e 9 horas no dia 20/11/2012 em seu pool. Você pode definir o caminho de saída para gravar os resultados em um arquivo denominado c\\: logfile. txt da seguinte maneira:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > A sequência data e hora que você especificar pode ser “data hora” ou “hora data”. "O comando irá analisar a cadeia de caracteres e usar os valores apropriados para data e hora.

    
    </div>

3.  Se você deseja recuperar os logs começando às 11:00 horas em 20/11/2012, você define –StartTime. O intervalo de hora padrão para a pesquisa é de 30 minutos, a não ser que você defina um –EndTime específico. A pesquisa resultante retornará logs do computador ou pools definidos de 11:00 horas a 11:30 horas.
    
    Por exemplo:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Para conduzir uma pesquisa dos logs dentro de um período de tempo específico, defina –StartTime e –EndTime. Você precisa de logs de 13:00 horas às 14:45 horas no computador edge01.contoso.net.
    
    Por exemplo:
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Para executar uma pesquisa avançada usando outro critério e opções correspondentes

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Para executar um comando para coletar rastreamentos de componentes específicos, digite o seguinte:
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    Por exemplo:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    A pesquisa resultante retorna todas as entradas de log com componentes de rastreamento para SIPStack, S4 e UserServices em todos os computadores e pools na sua implantação pelos últimos 30 minutos.

3.  Para limitar a pesquisa com os mesmos componentes para apenas o pool de front-end chamado pool01.contoso.net, digite:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  A lógica de pesquisa padrão para comando com vários parâmetros é usar o OR lógico com cada um dos parâmetros definidos. É possível alterar este comportamento especificando o parâmetro **–MatchAll**. Para fazer isso, digite o seguinte:
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  Se seus cenários estão definidos para ser executado constantemente, como AlwaysOn, ou se definiu logs do cenário de longa execução podem sair da máquina local em um compartilhamento de arquivos. Você define o compartilhamento de arquivos usando o parâmetro CacheFileNetworkFolder usando New-CsClsConfiguration para criar uma nova configuração ou modificar uma configuração existente com Set-CsClsConfiguration. Se você não deseja que a pesquisa inclua o compartilhamento de arquivos no conjunto de logs para pesquisar, use o parâmetro SkipNetworkLogs como a seguir:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

