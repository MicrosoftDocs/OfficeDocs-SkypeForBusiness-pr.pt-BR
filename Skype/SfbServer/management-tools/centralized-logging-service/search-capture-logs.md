---
title: Pesquisar logs de captura criados para o Serviço de Registro em Log no Skype for Business Server 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Resumo: Saiba como pesquisar e ler logs de captura Centralized Logging Service no Skype for Business Server 2015.'
ms.openlocfilehash: b1f049260eff7524e5a728852b3dcd99526d8742
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895884"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Pesquisar logs de captura criados para o Serviço de Registro em Log no Skype for Business Server 2015
 
**Resumo:** Saiba como pesquisar e ler logs de captura Centralized Logging Service no Skype for Business Server 2015.
  
Os recursos de pesquisa em the Centralized Logging Service serão útil e poderoso pelos seguintes motivos: 
  
- Sua pesquisa e os resultados correspondentes são executados em um único computador, em um escopo de pool, site ou global, com base no critério que você definir.
    
- Suas pesquisas podem ser iniciadas de forma ampla e reduzidas para um critério mais definido como hora, componente ou computador. Pesquise nos logs mesmos e não é necessário executar novamente uma sessão de log quando os critérios de pesquisa é alterado.
    
- Os resultados da sua pesquisa são reunidos de todos os computadores e pools no escopo, coletados e agregados em um único arquivo de resultados que representa todos os resultados do critério de pesquisa (limitado para cenários em execução e os dados capturados pelos cenários). Você usa ferramentas conhecidas, como o **Snooper** ou o **Bloco de notas**, para ler o arquivo de resultados e rastrear mensagens pela sua implantação.
    
O CLSAgent em cada computador cria os logs com base no cenário ou cenários (dois cenários por computador podem estar funcionando em um determinado momento). Os logs e seu índice e arquivos de cache associados são gerenciados pelo CLSAgent. Ao definir e executar uma pesquisa, o comando de pesquisa instrui o CLSAgent sobre qual informação deve ser recuperada. O CLSAgent executa a consulta nos arquivos de log, arquivos de cache e arquivos de índice e coloca-os na ordem de tempo delta, entrada mais antiga primeiro e continuando para a última entrada mais recente. O CLSController agrega (combina) os logs e os coloca na ordem de tempo delta, da entrada mais antiga para a entrada mais recente.
  
Após cada pesquisa, o cmdlet **Sync-CsClsLogging** é executado e descarrega o cache usado pelas pesquisas (não deve ser confundido com os arquivos de cache mantidos pelo CLSAgent). Descarregar o cache ajuda a garantir que há um log limpo e um armazenamento de captura de arquivo de rastreamento no CLSController para a próxima operação de pesquisa.
  
Para obter o máximo benefício do the Centralized Logging Service, você precisa de uma boa compreensão de como configurar a pesquisa para que retorne apenas as mensagens de rastreamento dos logs do computador e o pool que são relevantes para o problema que você estiver pesquisando. problemas
  
Para executar as funções de pesquisa Centralized Logging Service usando o Skype do Shell de gerenciamento do servidor de negócios, você deve ser um membro do CsAdministrator ou os grupos de segurança CsServerAdministrator acesso baseado em função (RBAC) de controle ou uma função RBAC personalizada que contém qualquer um desses dois grupos. Para retornar uma lista de todas as funções RBAC que tenha sido atribuído a este cmdlet para (incluindo qualquer funções de RBAC personalizadas que você criou a mesmo), execute o seguinte comando do Skype para Business Server Management Shell ou o prompt do Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por exemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

O lembrete deste tópico se concentra em como definir uma pesquisa para otimizar sua resolução de problemas.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Para executar uma pesquisa básica usando o serviço de registro em log centralizados

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Verifique se você tem o cenário AlwaysOn em execução na sua implantação no escopo global e digite o seguinte no prompt de comando:
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Por padrão, o Search-CsClsLogging envia os resultados da pesquisa para o console. Se você deseja salvar os resultados da pesquisa em um arquivo, use - OutputFilePath _ \<caminho totalmente qualificado do arquivo de cadeia de caracteres\>_. Para definir o parâmetro - OutputFilePath, fornecer um caminho e um nome de arquivo como parte do parâmetro em um formato de cadeia de caracteres entre aspas (por exemplo; C:\LogFiles\SearchOutput.txt). Neste exemplo, é necessário garantir que o diretório C:\LogFiles existe e que você tem permissões para arquivos de Leitura e Gravação (permissão NTFS Modificar) na pasta. O resultado é anexado, não substituído. Se você precisa separar arquivos, defina um nome de arquivo diferente para cada pesquisa. 
  
Por exemplo:
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Para executar uma pesquisa básica em um pool ou computador usando o serviço de registro em log centralizados

1. Para limitar a pesquisa a um computador ou pool específico, use o - parâmetro de computadores com o computador definido por um nome totalmente qualificado do computador, entre aspas e separados por uma vírgula da seguinte maneira:
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

Por exemplo:
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Para pesquisar mais de um computador, digite vários nomes do computador entre aspas e separados por vírgulas, como o seguinte:
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. Se você precisar pesquisar um pool inteiro, em vez de um único computador, altere o - parâmetro de computadores para - Pools, remove o nome do computador e substitui-lo com o pool ou pools aspas separados por vírgulas.
    
    Por exemplo:
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Ao usar os comandos de pesquisa, pools podem ser qualquer pool na sua implantação, como pools de Front-End, pools de borda, pools do servidor de Chat persistente ou outros que estão definidos como um pool em sua implantação.
    
    Por exemplo:
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Para executar uma pesquisa usando parâmetros de tempo

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Por padrão, o horário inicial para os parâmetros de tempo específico da pesquisa é 25 minutos antes da hora que você iniciar a pesquisa. Em outras palavras, se pesquisarmos às 16:00 horas, a hora de início da pesquisa exibirá 15:35 a 16:05. Se você precisar pesquisar 60 minutos ou 3 horas antes do horário atual, use o parâmetro - StartTime e definir a sequência de data e hora para indicar o tempo que você deseja iniciar a pesquisa. 
    
    Por exemplo, usando - StartTime e EndTime do - para definir um intervalo de data e hora, você pode definir uma pesquisa entre 8: 00 e 9 AM em 20/11/2012 no seu pool. É possível definir o caminho de resultado para gravar os resultados em um arquivo chamado c:\logfile.txt como a seguir:
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> A sequência data e hora que você especificar pode ser “data hora” ou “hora data”. "O comando irá analisar a cadeia de caracteres e usar os valores apropriados para a data e hora e suas configurações de localidade e cultura na máquina que você estiver executando o cmdlet do. 
  
3. Se você deseja recuperar logs, começando à meia 11:00:00 AM em 20/11/2012, você define a StartTime. O intervalo de tempo padrão para a pesquisa é 30 minutos, a menos que você define um EndTime - específico. A pesquisa resultante retornará logs do computador ou pools definidos de 11:00 horas a 11:30 horas.
    
Por exemplo:
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Para conduzir uma pesquisa de logs de dentro de um período de tempo específico, defina uma - StartTime e um EndTime. Você precisa de logs de 13:00 horas às 14:45 horas no computador edge01.contoso.net. 
    
Por exemplo:
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Para executar uma pesquisa avançada usando outro critério e opções correspondentes

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Para executar um comando para coletar rastreamentos de componentes específicos, digite o seguinte:
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Por exemplo:
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

A pesquisa resultante retorna todas as entradas de log com componentes de rastreamento para SIPStack, S4 e UserServices em todos os computadores e pools na sua implantação pelos últimos 30 minutos.
    
3. Para limitar a pesquisa com os mesmos componentes para apenas seu pool de Front-End chamado pool01. contoso.NET, digite:
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. A lógica de pesquisa padrão para comando com vários parâmetros é usar o OR lógico com cada um dos parâmetros definidos. Você pode alterar esse comportamento, especificando o parâmetro **- MatchAll** . Para fazer isso, digite o seguinte:
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. Se seus cenários estão definidos para ser executado constantemente, como AlwaysOn, ou se definiu logs do cenário de longa execução podem sair da máquina local em um compartilhamento de arquivos. Você define o compartilhamento de arquivos usando o parâmetro CacheFileNetworkFolder usando New-CsClsConfiguration para criar uma nova configuração ou modificar uma configuração existente com Set-CsClsConfiguration. Se você não deseja que a pesquisa inclua o compartilhamento de arquivos no conjunto de logs para pesquisar, use o parâmetro SkipNetworkLogs como a seguir:
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Lendo registros de captura do Serviço de Registro em Log

Você obtenha os benefícios reais do the Centralized Logging Service, depois que você execute a pesquisa e você tiver um arquivo que você pode usar para rastrear um problema relatado. Há várias maneiras que você pode ler o arquivo. O arquivo de saída está em um formato de texto padrão e você pode usar Notepad.exe ou outros programas que permitirá que você abra e ler um arquivo de texto. Para arquivos maiores e problemas mais complexos, você poderia usar uma ferramenta como Snooper.exe destina-se para ler e analisar a saída de log do serviço de registro em log centralizado. Snooper está incluído com as ferramentas de depuração disponível como um download separado. Você pode baixar as ferramentas de depuração aqui: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257). Quando você instala as ferramentas de depuração, itens de menu e atalhos não são criadas. Depois de instalar as ferramentas de depuração, abra o Windows Explorer, uma janela de linha de comando ou Skype do Shell de gerenciamento do servidor de negócios e vá até o diretório (local padrão) C:\Program Files\Skype para ferramentas de 2015\Debugging Business Server. Clique duas vezes em Snooper.exe ou digite Snooper.exe e pressione ENTER, se você estiver usando a linha de comando ou Skype do Shell de gerenciamento do servidor de negócios.
  
> [!IMPORTANT]
> A intenção deste tópico não é detalhar e discutir técnicas de resolução de problemas. A resolução de problemas e os processos relacionados é um assunto complexo. Para obter detalhes sobre noções básicas de solução de problemas e Solucionando problemas de cargas de trabalho específicas, consulte o catálogo do Microsoft Lync Server 2010 Resource Kit em [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003). Os processos e procedimentos ainda se aplicam ao Skype para Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Para abrir um arquivo de log no Snooper

1. Para usar o Snooper e abrir arquivos de log, você precisará de acesso de leitura aos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um desses dois grupos. 
    
2. Após a instalação das ferramentas de depuração (LyncDebugTools.msi), mude o diretório para o local do Snooper.exe usando o Windows Explorer ou na linha de comando. Por padrão, as ferramentas de depuração estão localizadas em C:\Program Files\Skype para ferramentas de 2015\Debugging Business Server. Clique duas vezes ou execute Snooper.exe.
    
3. Após o Snooper estar aberto, clique com o botão direito em **Arquivo**, clique em **Abrir arquivo**, encontre seus arquivos de registro, selecione um arquivo na caixa de diálogo **Abrir** e clique em **Abrir**.
    
4. Mensagens de **rastreamento** do arquivo de log são exibidas no **rastreamento** na guia clique na guia **mensagens** para exibir o conteúdo da mensagem dos rastreamentos coletados.
    
### <a name="to-display-a-call-flow-diagram"></a>Para exibir um fluxograma da chamada

1. Para usar o Snooper e abrir arquivos de log, você precisa de acesso de leitura dos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você precisará ser um membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um destes dois grupos.
    
2. Abra um arquivo de log e clique na guia **Mensagens**, selecione uma conversa na exibição de mensagens ou selecione um componente de rastreamento na guia **Rastreamento**.
    
3. Clique em **Fluxo de chamadas**.
    
> [!NOTE]
> Se você clicar em uma mensagem ou de rastreamento que não faz parte de um fluxo de chamadas, o diagrama não aparecerá e uma mensagem de status aparece na parte inferior do Snooper informando "Esta mensagem não é qualificada para callfow". Escolha outra mensagem ou rastreamento e o fluxo de chamadas aparecerá se a mensagem ou o rastreamento faz parte de um fluxo de chamadas. 
  
4. Mova pelas Mensagens ou linhas de Rastreamento e observe se o fluxograma de chamada atualiza ou muda para exibir um novo diagrama.
    
5. Passe sobre os elementos para obter informações sobre mensagens de chamada, pontos de extremidade e outros componentes.
