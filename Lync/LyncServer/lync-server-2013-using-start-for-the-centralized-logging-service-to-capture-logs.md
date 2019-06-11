---
title: Usar Start para o serviço de log centralizado para capturar logs
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5033b4a8dfd8121e2f0b5926623a55358188935e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Usar o Start para o serviço de log centralizado para capturar logs no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Para capturar logs de rastreamento usando o serviço de log centralizado, você emite um comando para começar a fazer logon em um ou mais computadores e pools. Você também pode emitir parâmetros que definem quais computadores ou grupos, quais cenários devem ser executados (por exemplo, o AlwaysOn, outro cenário predefinido ou um cenário que você criou), quais componentes do Lync Server (por exemplo, S4, SipStack) devem ser rastreados.

Para capturar informação certa, é necessário usar o cenário correto para coletar informação relevante ao problema. No serviço de log centralizado, um cenário é o conceito de ativar o registro em log com base em uma coleção de componentes do servidor, níveis de log e sinalizadores, que é muito mais eficiente e útil do que ter que definir esses elementos em uma base por servidor. Você define e especifica um cenário para executar e o cenário é executado consistentemente em todos os servidores e pools no escopo da infraestrutura.

O cenário padrão é chamado de **AlwaysOn**. O objetivo do AlwaysOn é executar o cenários constantemente, conforme o nome do cenário implica. O cenário AlwaysOn coleta informações de nível informativo (observe que o nível de log informativo inclui Fatal, Erro e Aviso, além das mensagens informativas) para boa parte da maioria dos componentes de servidor comum. AlwaysOn coleta informações antes, durante e após o problema ocorrer. Isso difere drasticamente do comportamento típico das ferramentas de log anteriores, como o OCSLogger. É possível executar OCSLogger após o problema ocorrer, dificultando seus esforços para resolução de problemas, pois os dados que você tem são reativos, não proativos. Se AlwaysOn não tem a informação que você está procurando a fim de indicar o componente do problema e um curso de ação para corrigi-lo (o que provavelmente não leva em conta a amplitude e profundidade dos provedores em AlwaysOn), ele indicará um nível adequado de informação para determinar o que mais deve ser feito, como criar um novo cenário, juntar outras informações, realizar uma busca diferente para coletar informações mais detalhadas, e assim por diante.

O serviço de log centralizado oferece duas maneiras de emitir comandos. Vários tópicos se concentraram de acordo com o uso do Windows PowerShell por meio do Shell de gerenciamento do Lync Server. A capacidade de usar diversas configurações e comandos complexos favorece o Windows PowerShell para o uso centralizado do serviço de registro em log. Como o Windows PowerShell por meio do Shell de gerenciamento do Lync Server é quase onipresente para todas as funções no Lync Server, somente os comandos do Windows PowerShell são discutidos.

<div>


> [!NOTE]
> Se você decidir usar o conjunto de comandos limitado disponível na linha de comando, poderá obter ajuda com o CLSController. exe digitando <CODE>ClsController.exe</CODE>. Por padrão, o <STRONG>ClsController. exe</STRONG> está instalado no diretório C:\Arquivos de Programas\microsoft Lync Server 2013 \ ClsAgent.



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Para executar Start-CsClsLogging com o Windows PowerShell usando comandos básicos

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Inicie um cenário de log com o serviço de log centralizado digitando o seguinte:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Por exemplo, para iniciar o cenário **AlwaysOn**, digite:
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > O cenário AlwaysOn não tem uma duração padrão. Este cenário será executado até que o pare precisamente com o cmdlet <STRONG>Stop-CsClsLogging</STRONG>. Para detalhes, consulte <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>. Para todos os outros cenários, a duração padrão é 4 horas.

    
    </div>

3.  Pressione Enter para executar o comando.
    
    <div>
    

    > [!NOTE]
    > Pode levar algum tempo (30 a 60 segundos) para que os comandos sejam executados e recebam o status dos computadores em sua implantação.

    
    </div>
    
    ![Executando Start-CsClsLogging.] (images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Executando Start-CsClsLogging.")

4.  Para iniciar outro cenários, use o cmdlet **Start-CsClsLogging** com o nome do cenário adicional para executar o seguinte (por exemplo, o cenário **Autenticação**):
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > É possível ter um total de dois cenários sendo executados em qualquer computador a qualquer momento. Se o comando for de escopo global, todos os computadores em sua implantação executarão o(s) cenário(s). Para iniciar um terceiro cenário, você deve parar o log no escopo de computador, pool, site ou global em que você queira executar o novo cenário. Caso tenho iniciado um escopo global, é possível parar o log em um ou ambos cenários em um ou mais computadores e pools. Para obter detalhes sobre como gerenciar quais cenários estão em execução, consulte <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">usando parar para o serviço de log centralizado no Lync Server 2013</A> e <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">parar-CsClsLogging</A>.

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Para executar Start-CsClsLogging com o Windows PowerShell usando comandos avançados

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Estão disponíveis parâmetros adicionais para gerenciar os comandos de log. É possível usar –Duration para ajustar o tempo em que o cenário será executado. É possível também definir –Computers, uma lista de nomes de domínios completamente qualificados de computadores (FQDNs) separados por vírgula, ou –Pools, uma lista separada por vírgula de FQDNs para pools que você quer executar o log.
    
    Você inicia uma sessão de log para o cenário *UserReplicator* no pool "pool01.contoso.net". Você também define duração da sessão de log em 8 horas. Para isso, digite:
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    O execução com sucesso deste cenário devolve um resultado como o seguinte:
    
    ![Executando Start-CsClsLogging.] (images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Executando Start-CsClsLogging.")
    
    Observe que, neste exemplo, o cenário AlwaysOn é executado e o cenário UserReplicator também está sendo executado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Visão geral do serviço de log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

