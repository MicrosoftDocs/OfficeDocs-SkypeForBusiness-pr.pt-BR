---
title: 'Lync Server 2013: usando log avançado para transações sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fd1cfd26e1b5d56a6043e13d348e73e3c2b108
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Usando o registro avançado de transações sintéticas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

As transações sintéticas (introduzidas no Microsoft Lync Server 2010) permitem que os administradores verifiquem se os usuários podem concluir com êxito as tarefas comuns, como fazer logon no sistema, trocar mensagens instantâneas ou fazer chamadas a um telefone localizado na rede telefônica pública comutada (PSTN). Esses testes (que são empacotados como um conjunto de cmdlets do Windows PowerShell do Lync Server) podem ser conduzidos manualmente por um administrador ou podem ser executados automaticamente por um aplicativo como o System Center Operations Manager.

No Lync Server 2010, as transações sintéticas são extremamente úteis para ajudar os administradores a identificar problemas com o sistema. Por exemplo, o cmdlet **Test-CsRegistration** pode alertar os administradores no fato de que alguns usuários estavam tendo dificuldade para registrar-se no Lync Server. No entanto, as transações sintéticas eram um pouco menos úteis para ajudar os administradores a determinar por que esses usuários estavam tendo dificuldade para se registrar no Lync Server. Isso se deve ao fato de que as transações sintéticas não forneceram informações detalhadas de registro em log que podem ajudar os administradores a solucionar problemas com o Lync Server. Na melhor das hipóteses, a saída detalhada de uma transação sintética oferecia informações passo a passo que poderiam habilitar um administrador a fazer um palpite fundamentado sobre onde era provável que tivesse ocorrido o problema.

No Microsoft Lync Server 2013, as transações sintéticas foram rearquitetadas para fornecer log avançado. "Registro avançado em log" significa que, para cada atividade assumida por uma transação sintética, informações como estas serão registradas:

  - A hora em que a atividade foi iniciada

  - A hora em que a atividade foi concluída

  - A ação que foi executada (por exemplo, criar, ingressar ou sair de uma conferência; fazer logon no Lync Server; enviar uma mensagem instantânea; e assim por diante)

  - Mensagens informativas, detalhadas, de advertência ou de erro geradas quando a atividade foi executada

  - Mensagens de registro de SIP

  - Registros de exceção ou códigos de diagnóstico gerados quando a atividade foi executada

  - O resultado líquido da execução da atividade

Essas informações são geradas automaticamente sempre que uma transação sintética é executada. No entanto, as informações não são exibidas automaticamente ou salvas em um arquivo de log. Em vez disso, os administradores que executam manualmente uma transação sintética podem usar o parâmetro OutLoggerVariable para especificar uma variável do Windows PowerShell na qual as informações serão armazenadas. A partir daqui, os administradores podem usar um par de métodos que permitem a gravação e/ou exibição do log avançado em formato XML ou HTML.

Por exemplo, os administradores do Lync Server 2010 podem executar o cmdlet **Test-CsRegistration** usando um comando semelhante ao seguinte:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Os administradores têm a opção de incluir o parâmetro OutLoggerVariable seguido pelo nome de uma variável à escolha deles:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> Não use o caractere $ como prefixo do nome da variável. Use um nome de variável como RegistrationTest e não $RegistrationTest.

O comando precedente produz um conteúdo semelhante ao seguinte:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

No entanto, informações muito mais detalhadas do que a mensagem de erro mostrada acima estão disponíveis para essa falha. Para acessar essas informações em formato HTML, use um comando semelhante a este para salvar as informações armazenadas na variável RegistrationTest em um arquivo HTML:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

Como alternativa, é possível usar o método ToXML() para salvar os dados em um arquivo XML:

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Esses arquivos podem ser exibidos usando o Internet Explorer, o Visual Studio ou qualquer outro aplicativo capaz de abrir arquivos HTML/XML.

As transações sintéticas executadas de dentro do System Center Operations Manager gerarão automaticamente esses arquivos de log para falhas. No entanto, esses logs não serão gerados se a execução falhar antes que o Windows PowerShell possa carregar e executar a transação sintética.

> [!IMPORTANT]  
> Por padrão, o Lync Server 2013 salva arquivos de log em uma pasta que não é compartilhada. Para tornar esses logs prontamente acessíveis, você deve compartilhar esta pasta (por exemplo \\ \\, ATL-Watcher-001. litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

