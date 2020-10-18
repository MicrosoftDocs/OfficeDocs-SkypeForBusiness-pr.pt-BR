---
title: Usando iniciar para o serviço de registro em log centralizado para capturar logs
description: Usando iniciar para o serviço de registro em log centralizado para capturar logs.
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
ms.openlocfilehash: 6321af0b12f3650d3b741e65968849332b53af45
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580217"
---
# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Usando iniciar para o serviço de registro em log centralizado para capturar logs no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Para capturar logs de rastreamento usando o serviço de registro em log centralizado, emita um comando para começar a fazer logon em um ou mais computadores e pools. Você também emite parâmetros que definem quais computadores ou pools, quais cenários serão executados (por exemplo, AlwaysOn, outro cenário predefinido ou um cenário que você tenha criado), quais componentes do Lync Server (por exemplo, S4, SipStack) devem ser rastreados.

Para capturar as informações corretas, você precisa ter certeza de que usa o cenário certo para coletar informações relevantes para o problema. No serviço de registro em log centralizado, um cenário é o conceito de ativar o registro em log com base em uma coleção de componentes de servidor, níveis de log e sinalizadores, que é muito mais eficiente e útil do que ter de definir esses elementos em uma base por servidor. Você define e especifica um cenário a ser executado e o cenário é executado de forma consistente em todos os servidores e pools no escopo da infraestrutura.

O cenário padrão é chamado de **AlwaysOn**. O objetivo do AlwaysOn é executar o cenários constantemente, conforme o nome do cenário implica. O cenário AlwaysOn coleta informações de nível informativo (obeserve que o nível de log informativo inclui Fatal, Erro e Aviso, além das mensagens informativas) para boa parte da maioria dos componentes de servidor comum. AlwaysOn coleta informções antes, durante e após o problema ocorrer. Isso difere drasticamente do comportamento típico das ferramentas de log anteriores, tais como OCSLogger. É possível executar OCSLogger após o problema ocorrer, tornando seus eforços para resolução de problemas mais dificil, pois os dados que você possui são reativos e não proativos. Se AlwaysOn não possui a informação que você está procurando a fim de indicar o componente do problema e um curso de ação para corrigi-lo (o que provavelmente não fornece a amplitude e profundidade dos provedores em AlwaysOn), ele indicará um nível adequado de informação para determinar o que mais dee ser feito, como criar um novo cenário, juntar outras informações, realizar uma busca diferente para coletar informações mais detalhadas, e assim por diante.

O serviço de registro centralizado fornece duas maneiras de emitir comandos. Vários tópicos têm ênfase detalhada no uso do Windows PowerShell por meio do Shell de gerenciamento do Lync Server. A capacidade de usar várias configurações e comandos complexos favorece o Windows PowerShell para o uso de serviço de registro em log centralizado. Como o Windows PowerShell através do Shell de gerenciamento do Lync Server é praticamente onipresente para todas as funções no Lync Server, somente os comandos do Windows PowerShell são discutidos.

<div>


> [!NOTE]
> Se você decidir usar o conjunto de comandos limitado disponível na linha de comando, poderá obter ajuda com CLSController.exe digitando <CODE>ClsController.exe</CODE> . Por padrão, o <STRONG>ClsController.exe</STRONG> é instalado no diretório C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent.



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Para executar o Start-CsClsLogging com o Windows PowerShell usando comandos básicos

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Inicie um cenário de registro em log com o serviço de registro em log centralizado digitando o seguinte:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Por exemplo, para iniciar o cenário **AlwaysOn**, digite:
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > O cenário The AlwaysOn não possui uma duração padrão. Este cenário será executado até que o pare precisamente com o cmdlet <STRONG>Stop-CsClsLogging</STRONG>. Para detalhes, consulte <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>. Para todos os outros cenários, a duração padrão é 4 horas.

    
    </div>

3.  Pressione Enter para executar o comenando.
    
    <div>
    

    > [!NOTE]
    > Pode levar algum tempo (30 a 60 segundos) para que os os comandos sejam executados e que recebam o status de volta dos computadores em sua implantação.

    
    </div>
    
    ![Executando Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Executando Start-CsClsLogging.")

4.  Para iniciar outro cenários, use o cmdlet **Start-CsClsLogging** com o nome do cenário adicional para executar o seguinte (por exemplo, o cenário **Autenticação**):
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > É possível ter um total de dois cenários sendo executados em qualquer computador a qualquer momento. Se o comando é global no escopo, todos os computadores em sua implantação executarão o cenário ou cenários. Para iniciar um terceiro cenário, você deve parar o log no computador, pool, site ou escopo global em que você queira executar o novo cenario. Caso tenho iniciado um escopo global, é possível parar o log em um ou ambos cenários em um ou mais computadores e pools. Para obter detalhes sobre o gerenciamento de cenários que estão sendo executados, consulte <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">usando parar para o serviço de registro em log centralizado no Lync Server 2013</A> e <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">parar-CsClsLogging</A>.

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Para executar o Start-CsClsLogging com o Windows PowerShell usando comandos avançados

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Parâmetros adicionais estão disponíveis para gerenciar os comandos de log. É possível usar  –Duração para ajustar o tempo em que o cenário será executado. Também é possível definir –Computadores, uma lista de nomes de domínios completamente qualificados de computadores (FQDNs) separados por vírgula, ou –Pools, uma lista separada por vírgula de FQDNs para pools que você queira executar o log.
    
    Você inicia uma sessão de registro em log para o cenário *Userreplicator* no pool "pool01.contoso.net". Você também define a duração da sessão de log em 8 horas. Para isso, digite:
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    O execução com sucesso deste cenário devolve um resultado como o seguinte:
    
    ![Executando Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Executando Start-CsClsLogging.")
    
    Observe que neste exemplo, o cenário AlwaysOn é executado e o cenário UserReplicator também está sendo executado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Visão geral do serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

