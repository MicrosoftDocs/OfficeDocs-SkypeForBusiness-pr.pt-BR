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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Resumo: saiba como Pesquisar e ler logs de captura de serviço de log centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: 234bcdcda4fbf4a0fa7cec364b9a8dbb7b757dc7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816570"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Pesquisar logs de captura criados para o Serviço de Registro em Log no Skype for Business Server 2015
 
**Resumo:** Saiba como Pesquisar e ler logs de captura de serviço de log centralizado no Skype for Business Server 2015.
  
Os recursos de pesquisa do serviço de log centralizado são úteis e eficientes pelos seguintes motivos: 
  
- Sua pesquisa e os resultados correspondentes são executados em um único computador, em um escopo de pool, site ou global, com base no critério que você definir.
    
- Suas pesquisas podem ser iniciadas de forma ampla e reduzidas para um critério mais definido como hora, componente ou computador. Você pesquisa nos mesmos logs e não precisa executar uma sessão de log novamente quando os critérios de pesquisa são alterados.
    
- Os resultados da sua pesquisa são reunidos de todos os computadores e pools no escopo, coletados e agregados em um único arquivo de resultados que representa todos os resultados do critério de pesquisa (limitado para cenários em execução e os dados capturados pelos cenários). Você usa ferramentas conhecidas, como o **Snooper** ou o **Bloco de notas**, para ler o arquivo de resultados e rastrear mensagens pela sua implantação.
    
O CLSAgent em cada computador cria os logs com base no cenário ou cenários (dois cenários por computador podem estar funcionando em um determinado momento). Os logs e seu índice e arquivos de cache associados são gerenciados pelo CLSAgent. Ao definir e executar uma pesquisa, o comando de pesquisa instrui o CLSAgent sobre qual informação deve ser recuperada. O CLSAgent executa a consulta nos arquivos de log, arquivos de cache e arquivos de índice e coloca-os na ordem de tempo delta, entrada mais antiga primeiro e continuando para a última entrada mais recente. O CLSController agrega (combina) os logs e os coloca na ordem de tempo delta, da entrada mais antiga para a entrada mais recente.
  
Após cada pesquisa, o cmdlet **Sync-CsClsLogging** é executado e descarrega o cache usado pelas pesquisas (não deve ser confundido com os arquivos de cache mantidos pelo CLSAgent). Descarregar o cache ajuda a garantir que há um log limpo e um armazenamento de captura de arquivo de rastreamento no CLSController para a próxima operação de pesquisa.
  
Para aproveitar ao máximo o serviço de registro centralizado, você precisa de uma boa compreensão de como configurar a pesquisa para retornar apenas mensagens de rastreamento do computador e dos logs de pool que sejam relevantes para o problema que você está pesquisando. problemas
  
Para executar as funções de pesquisa de serviço de log centralizado usando o Shell de gerenciamento do Skype for Business Server, você deve ser membro do grupo de segurança CsAdministrator ou do controle de acesso baseado em função do CsServerAdministrator (RBAC) ou uma função RBAC personalizada que contenha um desses dois grupos. Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no Shell de gerenciamento do Skype for Business Server ou no prompt do Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por exemplo:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

O lembrete deste tópico se concentra em como definir uma pesquisa para otimizar sua resolução de problemas.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Para executar uma pesquisa básica usando o serviço de log centralizado

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Verifique se você tem o cenário AlwaysOn em execução na sua implantação no escopo global e digite o seguinte no prompt de comando:
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Por padrão, o Search-CsClsLogging envia os resultados da pesquisa para o console. Se você quiser salvar os resultados da pesquisa em um arquivo, use o _ \<caminho\>de arquivo totalmente qualificado da cadeia de caracteres_OutputFilePath. Para definir o parâmetro-OutputFilePath, forneça um caminho e um nome de arquivo como parte do parâmetro em um formato de cadeia de caracteres entre aspas (por exemplo; C:\LogFiles\SearchOutput.txt). Neste exemplo, é necessário garantir que o diretório C:\LogFiles existe e que você tem permissões para arquivos de Leitura e Gravação (permissão NTFS Modificar) na pasta. O resultado é anexado, não substituído. Se você precisa separar arquivos, defina um nome de arquivo diferente para cada pesquisa. 
  
Por exemplo:
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Para executar uma pesquisa básica em um pool ou computador usando o serviço de log centralizado

1. Para limitar a pesquisa a um grupo ou computador específico, use o parâmetro-Computers com o computador definido por um nome totalmente qualificado do computador, entre aspas e separado por uma vírgula da seguinte maneira:
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

Por exemplo:
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Para pesquisar mais de um computador, digite vários nomes do computador entre aspas e separados por vírgulas, como o seguinte:
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. Se você precisar pesquisar um pool inteiro em vez de um único computador, altere o parâmetro-Computers para pools, remova o nome do computador e substitua-o pelo pool ou pools entre aspas separadas por vírgulas.
    
    Por exemplo:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Ao usar os comandos de pesquisa, os pools podem ser qualquer pool na sua implantação, como grupos de front-end, pools de borda, pools de servidores de chat persistentes ou outros definidos como um pool na sua implantação.
    
    Por exemplo:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Para executar uma pesquisa usando parâmetros de tempo

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Por padrão, o horário inicial para os parâmetros de tempo específico da pesquisa é 25 minutos antes da hora que você iniciar a pesquisa. Em outras palavras, se pesquisarmos às 16:00 horas, a hora de início da pesquisa exibirá 15:35 a 16:05. Se você precisar pesquisar 60 minutos ou 3 horas antes do tempo atual, use o parâmetro-StartTime e defina a cadeia de caracteres de data e hora para indicar o tempo que você deseja que a pesquisa comece. 
    
    Por exemplo, ao usar-StartTime e-EndTime para definir um intervalo de tempo e data, você pode definir uma pesquisa entre 8 AM e 9 no 11/20/2012 em seu pool. É possível definir o caminho de resultado para gravar os resultados em um arquivo chamado c:\logfile.txt como a seguir:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> A sequência data e hora que você especificar pode ser “data hora” ou “hora data”. "O comando analisará a cadeia de caracteres e usará os valores apropriados para data e hora e suas configurações de localidade e cultura no computador do qual você está executando o cmdlet. 
  
3. Se você quiser recuperar logs começando em 11:00:00 AM no 11/20/2012, defina-StartTime. O intervalo de tempo padrão para a pesquisa é de 30 minutos, a menos que você defina uma EndTime específica. A pesquisa resultante retornará logs do computador ou pools definidos de 11:00 horas a 11:30 horas.
    
Por exemplo:
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Para conduzir uma pesquisa de logs em um período específico de tempo, defina a-StartTime e uma-EndTime. Você precisa de logs de 13:00 horas às 14:45 horas no computador edge01.contoso.net. 
    
Por exemplo:
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Para executar uma pesquisa avançada usando outro critério e opções correspondentes

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Para executar um comando para coletar rastreamentos de componentes específicos, digite o seguinte:
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Por exemplo:
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

A pesquisa resultante retorna todas as entradas de log com componentes de rastreamento para SIPStack, S4 e UserServices em todos os computadores e pools na sua implantação pelos últimos 30 minutos.
    
3. Para limitar a pesquisa com os mesmos componentes para apenas o pool de front-end chamado pool01.contoso.net, digite:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. A lógica de pesquisa padrão para comando com vários parâmetros é usar o OR lógico com cada um dos parâmetros definidos. Você pode alterar esse comportamento especificando o parâmetro **-MatchAll** . Para fazer isso, digite o seguinte:
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. Se seus cenários estão definidos para ser executado constantemente, como AlwaysOn, ou se definiu logs do cenário de longa execução podem sair da máquina local em um compartilhamento de arquivos. Você define o compartilhamento de arquivos usando o parâmetro CacheFileNetworkFolder usando New-CsClsConfiguration para criar uma nova configuração ou modificar uma configuração existente com Set-CsClsConfiguration. Se você não deseja que a pesquisa inclua o compartilhamento de arquivos no conjunto de logs para pesquisar, use o parâmetro SkipNetworkLogs como a seguir:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Lendo registros de captura do Serviço de Registro em Log

Você percebe o verdadeiro benefício do serviço de registro centralizado depois de executar a pesquisa e tem um arquivo que pode ser usado para rastrear um problema relatado. Há várias maneiras de ler o arquivo. O arquivo de saída está em um formato de texto padrão e você pode usar o notepad. exe ou qualquer outro programa que permita a abertura e leitura de um arquivo de texto. Para arquivos maiores e problemas mais complexos, você pode usar uma ferramenta como o Snooper. exe projetado para ler e analisar a saída de log do serviço de log centralizado. O Snooper está incluído nas ferramentas de depuração que estão disponíveis como um download separado. Você pode baixar as ferramentas de depuração aqui [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257):. Quando você instala as ferramentas de depuração, pequenos atalhos e itens de menu não são criados. Após instalar as ferramentas de depuração, abra o Windows Explorer, uma janela de linha de comando ou o Shell de gerenciamento do Skype for Business Server e acesse o diretório (local padrão) C:\Program Files\Skype for Business Server 2015 \ Debugging Tools. Clique duas vezes em Espionador. exe ou digite Snooper. exe e pressione ENTER se estiver usando a linha de comando ou o Shell de gerenciamento do Skype for Business Server.
  
> [!IMPORTANT]
> A intenção deste tópico não é detalhar e discutir técnicas de resolução de problemas. A resolução de problemas e os processos relacionados é um assunto complexo. Para obter detalhes sobre como solucionar problemas de noções básicas e solucionar problemas de cargas de trabalho específicas, consulte o [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)Microsoft Lync Server 2010 Resource Kit book. Os processos e procedimentos ainda se aplicam ao Skype for Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Para abrir um arquivo de log no Snooper

1. Para usar o Snooper e abrir arquivos de log, você precisará de acesso de leitura aos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um desses dois grupos. 
    
2. Após a instalação das ferramentas de depuração (LyncDebugTools.msi), mude o diretório para o local do Snooper.exe usando o Windows Explorer ou na linha de comando. Por padrão, as ferramentas de depuração estão localizadas em C:\Program Files\Skype for Business Server 2015 \ ferramentas de depuração. Clique duas vezes ou execute Snooper.exe.
    
3. Após o Snooper estar aberto, clique com o botão direito em **Arquivo**, clique em **Abrir arquivo**, encontre seus arquivos de registro, selecione um arquivo na caixa de diálogo **Abrir** e clique em **Abrir**.
    
4. As mensagens de **rastreamento** do arquivo de log são exibidas na guia **rastrear** . Clique na guia **mensagens** para exibir o conteúdo das mensagens dos rastreamentos coletados.
    
### <a name="to-display-a-call-flow-diagram"></a>Para exibir um fluxograma da chamada

1. Para usar o Snooper e abrir arquivos de log, você precisa de acesso de leitura dos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você precisará ser um membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um destes dois grupos.
    
2. Abra um arquivo de log e clique na guia **Mensagens**, selecione uma conversa na exibição de mensagens ou selecione um componente de rastreamento na guia **Rastreamento**.
    
3. Clique em **Fluxo de chamadas**.
    
> [!NOTE]
> Se você clicar em uma mensagem ou um rastreamento que não faz parte de um fluxo de chamadas, o diagrama não será exibido e uma mensagem de status será exibida na parte inferior da Snooper informando que "esta mensagem não está qualificada para callfow". Escolha outra mensagem ou rastreamento e o fluxo de chamadas aparecerá se a mensagem ou o rastreamento faz parte de um fluxo de chamadas. 
  
4. Mova pelas Mensagens ou linhas de Rastreamento e observe se o fluxograma de chamada atualiza ou muda para exibir um novo diagrama.
    
5. Passe sobre os elementos para obter informações sobre mensagens de chamada, pontos de extremidade e outros componentes.
