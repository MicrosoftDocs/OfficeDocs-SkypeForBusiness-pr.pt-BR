---
title: Logs de captura de pesquisa criados pelo Serviço de Log Centralizado Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Resumo: saiba como pesquisar e ler logs de captura do Serviço de Log Centralizado Skype for Business Server 2015.'
ms.openlocfilehash: 2168bdc0a72df6efe4bf9d9f178a2ee9c120aa6a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385551"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Logs de captura de pesquisa criados pelo Serviço de Log Centralizado Skype for Business Server 2015
 
**Resumo:** Saiba como pesquisar e ler logs de captura do Serviço de Log Centralizado Skype for Business Server 2015.
  
Os recursos de pesquisa no Serviço de Log Centralizado são úteis e avançados pelos seguintes motivos: 
  
- Sua pesquisa e seus resultados são executados em um único computador, em um escopo de grupo, site ou global, com base no critério que você definir.
    
- Suas pesquisas podem ser iniciadas de forma ampla e reduzidas para um critério mais definido como hora, componente ou computador. Você pesquisa os mesmos logs e não precisa executar uma sessão de registro em log novamente quando os critérios de pesquisa mudarem.
    
- Os resultados da sua pesquisa são reunidos de todos os computadores e pools no escopo, coletados e agregados em um único arquivo de resultados que representa todos os resultados do critério de pesquisa (limitado para cenários em execução e os dados capturados pelos cenários). Você usa ferramentas familiares como o **Snooper** ou o **Bloco de notas** para ler o arquivo de resultados e rastrear mensagens pela sua implantação.
    
O CLSAgent em cada computador cria os logs com base no cenário ou cenários (dois cenários por computador podem estar funcionando em um determinado momento). Os logs e seu índice e arquivos de cache associados são gerenciados pelo CLSAgent. Ao definir e executar uma pesquisa, o comando de pesquisa instrui o CLSAgent sobre qual informação deve ser recuperada. O CLSAgent executa a consulta nos arquivos de log, arquivos de cache e arquivos de índice e coloca-os na ordem de tempo delta, entrada mais antiga primeiro e continuando para a última entrada mais recente. O CLSController agrega (combina) os logs e os coloca na ordem de tempo delta, entrada mais antiga primeiro e continuando para a última entrada mais recente.
  
Após cada pesquisa, o cmdlet **Sync-CsClsLogging** é executado e descarrega o cache usado pelas pesquisas (não deve ser confundido com os arquivos de cache mantidos pelo CLSAgent). Descarregar o cache ajuda a garantir que há um log limpo e um armazenamento de captura de arquivo de rastreamento no CLSController para a próxima operação de pesquisa.
  
Para obter o maior benefício do Serviço de Registro Em Log Centralizado, você precisa ter uma boa compreensão de como configurar a pesquisa para retornar apenas mensagens de rastreamento do computador e logs de pool relevantes para o problema que você está pesquisando. issues
  
Para executar as funções de pesquisa do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server, você deve ser membro dos grupos de segurança CsAdministrator ou CsServerAdministrator de controle de acesso baseado em função (RBAC) ou uma função RBAC personalizada que contenha um desses dois grupos. Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído (incluindo quaisquer funções RBAC personalizadas que você mesmo tenha criado), execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server ou no prompt Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por exemplo:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

O lembrete deste tópico se focaliza em como definir uma pesquisa para otimizar sua resolução de problemas.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Para executar uma pesquisa básica usando o Serviço de Registro Em Log Centralizado

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
2. Certifique-se de ter o cenário AlwaysOn em execução na sua implantação no escopo global e digite o seguinte no prompt de comando:
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Por padrão, o Search-CsClsLogging envia os resultados da pesquisa para o console. Se você quiser salvar os resultados da pesquisa em um arquivo, use -OutputFilePath  _\<string fully qualified file path\>_. Para definir o parâmetro -OutputFilePath, fornece um caminho e um nome de arquivo como parte do parâmetro em um formato de cadeia de caracteres entre aspas (por exemplo, C:\LogFiles\SearchOutput.txt). Neste exemplo, você deve garantir que o diretório C:\LogFiles exista e que você possui permissões para arquivos de Leitura e Gravação (permissão NTFS Modificar) na pasta. O resultado é anexado e não é substituído. Se você precisa separar arquivos, defina um nome de arquivo diferente para cada pesquisa. 
  
Por exemplo:
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Para executar uma pesquisa básica em um pool ou computador usando o Serviço de Log Centralizado

1. Para limitar a pesquisa a um pool ou computador específico, use o parâmetro -Computers com o computador definido por um nome totalmente qualificado do computador, entre aspas e separado por uma vírgula da seguinte forma:
    
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

3. Se você precisar pesquisar um pool inteiro em vez de um único computador, altere o parâmetro -Computers para -Pools, remova o nome do computador e substitua-o pelo pool ou pools entre aspas separados por vírgulas.
    
    Por exemplo:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Ao usar os comandos de pesquisa, os pools podem ser qualquer pool em sua implantação, como pools de Front-End, pools de Borda, pools de Servidor de Chat Persistente ou outros que são definidos como um pool em sua implantação.
    
    Por exemplo:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Para executar uma pesquisa usando parâmetros de tempo

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
2. Por padrão, a hora de início dos parâmetros específicos de uma pesquisa é de 25 minutos antes de cinco minutos após o momento em que você inicia a pesquisa. Em outras palavras, se pesquisarmos às 16:00, o horário de início da pesquisa será das 15:35:00 às 16:00. Se você precisar pesquisar 60 minutos ou 3 horas antes da hora atual, use o parâmetro -StartTime e de definir a cadeia de caracteres de data e hora para indicar a hora que você deseja que a pesquisa inicie. 
    
    Por exemplo, usando -StartTime e -EndTime para definir um intervalo de data e hora, você pode definir uma pesquisa entre 8:00 e 9:00 em 20/11/2012 em seu pool. É possível definir o caminho de resultado para gravar os resultados em um arquivo chamado c:\logfile.txt como a seguir:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> A cadeia de caracteres de data e hora especificada pode ser "data" ou "data/hora". " O comando analisará a cadeia de caracteres e usará os valores apropriados para data e hora e suas configurações de localidade e cultura no computador de onde você está executando o cmdlet. 
  
3. Se você quiser recuperar logs a partir das 11:00:00 em 20/11/2012, defina -StartTime. O intervalo de tempo padrão para a pesquisa é de 30 minutos, a menos que você defina um -EndTime específico. A pesquisa resultante retornará logs do computador ou pools definidos de 11:00 horas a 11:30 horas.
    
Por exemplo:
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Para conduzir uma pesquisa de logs em um período específico de tempo, defina -StartTime e -EndTime. Você precisa de logs de 13:00 horas às 14:45 horas no computador edge01.contoso.net. 
    
Por exemplo:
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Para executar uma pesquisa avançada usando outro critério e opções correspondentes

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
2. Para executar um comando para coletar rastreamentos de componentes específicos, digite o seguinte:
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Por exemplo:
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

A pesquisa resultante retorna todas as entradas de log com componentes de rastreamento para SIPStack, S4 e UserServices em todos os computadores e pools na sua implantação pelos últimos 30 minutos.
    
3. Para limitar a pesquisa com os mesmos componentes apenas ao pool de Front-End chamado pool01.contoso.net, digite:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. A lógica de pesquisa padrão para comando com vários parâmetros é usar o OR lógico com cada um dos parâmetros definidos. Você pode alterar esse comportamento especificando o **parâmetro -MatchAll** . Para fazer isso, digite o seguinte:
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. Se seus cenários estão definidos para ser executado constantemente, como AlwaysOn, ou se definiu logs do cenário de longa execução podem sair da máquina local em um compartilhamento de arquivos. Você define o compartilhamento de arquivos usando o parâmetro CacheFileNetworkFolder usando New-CsClsConfiguration para criar uma nova configuração ou modificar uma configuração existente com Set-CsClsConfiguration. Se você não deseja que a pesquisa inclua o compartilhamento de arquivos no conjunto de logs para pesquisar, use o parâmetro SkipNetworkLogs como a seguir:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Ler logs de captura do Serviço de Registro Centralizado

Você percebe o benefício real do Serviço de Log Centralizado depois de executar a pesquisa e tem um arquivo que pode ser usado para rastrear um problema relatado. Existe um número de formas que você pode ler o arquivo. O arquivo de resultado está em um formato de texto padrão e você pode usar Notepad.exe ou qualquer outro programa que permitirá abrir e ler um arquivo de texto. Para arquivos maiores e problemas mais complexos, você pode usar uma ferramenta como Snooper.exe que foi projetada para ler e analisar a saída de log do Serviço de Registro Em Log Centralizado. O Snooper está incluído nas Ferramentas de Depuração que estão disponíveis como um download separado. Você pode baixar as Ferramentas de Depuração aqui: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257). Quando você instala as Ferramentas de Depuração, os atalhos e os itens de menu não são criados. Depois de instalar as Ferramentas de Depuração, abra o Windows Explorer, uma janela de linha de comando ou o Shell de Gerenciamento Skype for Business Server e vá para o diretório (local padrão) C:\Arquivos de Programas\Skype for Business Server 2015\Ferramentas de Depuração. Clique duas Snooper.exe ou digite Snooper.exe e pressione ENTER se estiver usando a linha de comando ou Skype for Business Server Shell de Gerenciamento.
  
> [!IMPORTANT]
> A intenção deste tópico não é detalhar e discutir técnicas de resolução de problemas. A resolução de problemas e os processos relacionados é um assunto complexo. Para obter detalhes sobre como solucionar problemas básicos e solucionar problemas de cargas de trabalho específicas, consulte o livro kit de recursos do Microsoft Lync Server 2010 em [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003). Os processos e procedimentos ainda se aplicam ao Skype for Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Para abrir um arquivo de log no Snooper

1. Para usar o Snooper e abrir arquivos de log, você precisará de acesso de leitura aos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um destes dois grupos. 
    
2. Após a instalação das Ferramentas de Depuração (LyncDebugTools.msi), altere o diretório para o local do Snooper.exe usando Windows Explorer ou da linha de comando. Por padrão, as ferramentas de depuração estão localizadas em C:\Arquivos de Programas\Skype for Business Server 2015\Ferramentas de Depuração. Clique duas vezes ou execute Snooper.exe.
    
3. Após o Snooper estar aberto, clique com o botão direito em **Arquivo**, clique em **Abrir arquivo**, encontre seus arquivos de log, selecione um arquivo na caixa de diálogo **Abrir** e clique em **Abrir**.
    
4. As mensagens **trace do arquivo** de log são exibidas na **guia** Rastreamento. Clique na **guia Mensagens** para exibir o conteúdo da mensagem dos rastreamentos coletados.
    
### <a name="to-display-a-call-flow-diagram"></a>Para exibir um fluxograma da chamada

1. Para usar o Snooper e abrir arquivos de log, você precisa de acesso de leitura dos arquivos de log. Para usar o Snooper e acessar os arquivos de log, você precisará ser um membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contém um destes dois grupos.
    
2. Abra um arquivo de log e clique na guia **Mensagens**, selecione uma conversa na exibição de mensagens ou selecione um componente de rastreamento na guia **Rastreamento**.
    
3. Clique em **Fluxo de chamadas**.
    
> [!NOTE]
> Se você clicar em uma mensagem ou rastreamento que não faz parte de um fluxo de chamada, o diagrama não aparecerá e uma mensagem de status aparecerá na parte inferior do Snooper informando "Essa mensagem não está qualificada para chamada". Escolha outra mensagem ou rastreamento e o fluxo de chamadas aparecerá se a mensagem ou o rastreamento faz parte de um fluxo de chamadas. 
  
4. Mova pelas Mensagens ou linhas de Rastreamento e observe se o fluxograma de chamada atualiza ou muda para exibir um novo diagrama.
    
5. Passe sobre os elementos para obter informações sobre mensagens de chamada, pontos de extremidade e outros componentes.
