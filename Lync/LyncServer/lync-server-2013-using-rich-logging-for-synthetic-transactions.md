---
title: 'Lync Server 2013: usando o log rico para transações sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 455d7bcdc14dd4d701d749407759cead0834906f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Usar o log avançado de transações sintéticas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Transações sintéticas (introduzidas no Microsoft Lync Server 2010) fornecem uma maneira para os administradores verificarem se os usuários podem concluir com êxito tarefas comuns, como fazer logon no sistema, trocar mensagens de chat ou fazer chamadas para um telefone localizado na rede telefônica pública comutada (PSTN). Esses testes (que são empacotados como um conjunto de cmdlets do Windows PowerShell do Lync Server) podem ser conduzidos manualmente por um administrador ou podem ser executados automaticamente por um aplicativo como o System Center Operations Manager.

No Lync Server 2010, as transações sintéticas comprovadamente são extremamente úteis para ajudar os administradores a identificar problemas com o sistema. Por exemplo, o cmdlet **Test-CsRegistration** pode alertar os administradores sobre o fato de que alguns usuários estavam tendo dificuldade para registrar-se no Lync Server. No entanto, as transações sintéticas eram um pouco menos úteis em ajudar administradores a determinar por que esses usuários estavam tendo dificuldades para se registrar no Lync Server. Isso se deve ao fato de que as transações sintéticas não forneceram informações detalhadas sobre o registro em log que podem ajudar os administradores a solucionar problemas com o Lync Server. Na melhor das hipóteses, a saída detalhada de uma transação sintética forneceu informações passo a passo que podem permitir que um administrador faça um palpite informativo sobre onde ocorreu um problema.

No Microsoft Lync Server 2013, as transações sintéticas foram reprojetadas para fornecer registro em log rico. "Log rico" significa que, para cada atividade que uma transação sintética é realizada, as informações como esta serão gravadas:

  - A hora de início da atividade

  - O tempo em que a atividade terminou

  - A ação realizada (por exemplo, criar, ingressar ou sair de uma conferência; fazer logon no Lync Server; enviar uma mensagem instantânea; e assim por diante)

  - Mensagens informativas, detalhadas, de advertência ou de erro geradas quando a atividade foi executada

  - Mensagens de registro do SIP

  - Registros de exceção ou códigos de diagnóstico gerados quando a atividade foi executada

  - O resultado líquido da execução da atividade

Essas informações são geradas automaticamente toda vez que uma transação sintética é executada. No entanto, as informações não são automaticamente exibidas ou salvas em um arquivo de log. Em vez disso, os administradores que estão executando manualmente uma transação sintética podem usar o parâmetro OutLoggerVariable para especificar uma variável do Windows PowerShell na qual as informações serão armazenadas. De lá, os administradores podem usar um par de métodos que permitem salvar e/ou exibir o log sofisticado em formato XML ou HTML.

Por exemplo, os administradores do Lync Server 2010 podem executar o cmdlet **Test-CsRegistration** usando um comando semelhante ao seguinte:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Os administradores têm a opção de incluir o parâmetro OutLoggerVariable seguido por um nome de variável de sua escolha:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> Não preceda o nome da variável com o caractere $. Use um nome de variável como RegistrationTest e não $RegistrationTest.

O comando anterior gera um conteúdo semelhante ao seguinte:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

No entanto, informações muito mais detalhadas estão disponíveis para essa falha do que apenas a mensagem de erro mostrada acima. Para acessar essas informações em formato HTML, use um comando semelhante a isso para salvar as informações armazenadas na variável RegistrationTest em um arquivo HTML:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

Como alternativa, é possível usar o método ToXML() para salvar os dados em um arquivo XML:

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Esses arquivos podem ser exibidos usando o Internet Explorer, o Visual Studio ou qualquer outro aplicativo capaz de abrir arquivos HTML/XML.

As transações sintéticas executadas dentro do System Center Operations Manager gerarão automaticamente esses arquivos de log para falhas. No entanto, esses logs não serão gerados se a execução falhar antes que o Windows PowerShell seja capaz de carregar e executar a transação sintética.

> [!IMPORTANT]  
> Por padrão, o Lync Server 2013 salva arquivos de log em uma pasta que não seja compartilhada. Para tornar esses logs prontamente acessíveis, você deve compartilhar essa pasta (por exemplo \\ \\, ATL-Watcher-001. litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

