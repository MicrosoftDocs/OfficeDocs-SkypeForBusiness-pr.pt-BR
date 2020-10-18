---
title: 'Lync Server 2013: usando log avançado para transações sintéticas'
description: 'Lync Server 2013: usando log avançado de transações sintéticas.'
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
ms.openlocfilehash: 5fd984386985bced64265ebedfd57c56a84a4443
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580297"
---
# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="02569-103">Usando o registro avançado de transações sintéticas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02569-103">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02569-104">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="02569-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="02569-105">As transações sintéticas (introduzidas no Microsoft Lync Server 2010) permitem que os administradores verifiquem se os usuários podem concluir com êxito as tarefas comuns, como fazer logon no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado na rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="02569-105">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="02569-106">Esses testes (que são empacotados como um conjunto de cmdlets do Windows PowerShell do Lync Server) podem ser conduzidos manualmente por um administrador ou podem ser executados automaticamente por um aplicativo como o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="02569-106">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="02569-107">No Lync Server 2010, as transações sintéticas são extremamente úteis para ajudar os administradores a identificar problemas com o sistema.</span><span class="sxs-lookup"><span data-stu-id="02569-107">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="02569-108">Por exemplo, o cmdlet **Test-CsRegistration** pode alertar os administradores no fato de que alguns usuários estavam tendo dificuldade para registrar-se no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02569-108">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="02569-109">No entanto, as transações sintéticas eram um pouco menos úteis para ajudar os administradores a determinar por que esses usuários estavam tendo dificuldade para se registrar no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02569-109">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="02569-110">Isso se deve ao fato de que as transações sintéticas não forneceram informações detalhadas de registro em log que podem ajudar os administradores a solucionar problemas com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02569-110">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="02569-111">Na melhor das hipóteses, a saída detalhada de uma transação sintética oferecia informações passo a passo que poderiam habilitar um administrador a fazer um palpite fundamentado sobre onde era provável que tivesse ocorrido o problema.</span><span class="sxs-lookup"><span data-stu-id="02569-111">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="02569-112">No Microsoft Lync Server 2013, as transações sintéticas foram rearquitetadas para fornecer log avançado.</span><span class="sxs-lookup"><span data-stu-id="02569-112">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="02569-113">"Registro avançado em log" significa que, para cada atividade assumida por uma transação sintética, informações como estas serão registradas:</span><span class="sxs-lookup"><span data-stu-id="02569-113">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="02569-114">A hora em que a atividade foi iniciada</span><span class="sxs-lookup"><span data-stu-id="02569-114">The time that the activity started</span></span>

  - <span data-ttu-id="02569-115">A hora em que a atividade foi concluída</span><span class="sxs-lookup"><span data-stu-id="02569-115">The time that the activity finished</span></span>

  - <span data-ttu-id="02569-116">A ação que foi executada (por exemplo, criar, ingressar ou sair de uma conferência; fazer logon no Lync Server; enviar uma mensagem instantânea; e assim por diante)</span><span class="sxs-lookup"><span data-stu-id="02569-116">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="02569-117">Mensagens informativas, detalhadas, de advertência ou de erro geradas quando a atividade foi executada</span><span class="sxs-lookup"><span data-stu-id="02569-117">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="02569-118">Mensagens de registro de SIP</span><span class="sxs-lookup"><span data-stu-id="02569-118">SIP registration messages</span></span>

  - <span data-ttu-id="02569-119">Registros de exceção ou códigos de diagnóstico gerados quando a atividade foi executada</span><span class="sxs-lookup"><span data-stu-id="02569-119">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="02569-120">O resultado líquido da execução da atividade</span><span class="sxs-lookup"><span data-stu-id="02569-120">The net result of running the activity</span></span>

<span data-ttu-id="02569-121">Essas informações são geradas automaticamente sempre que uma transação sintética é executada.</span><span class="sxs-lookup"><span data-stu-id="02569-121">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="02569-122">No entanto, as informações não são exibidas automaticamente ou salvas em um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="02569-122">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="02569-123">Em vez disso, os administradores que executam manualmente uma transação sintética podem usar o parâmetro OutLoggerVariable para especificar uma variável do Windows PowerShell na qual as informações serão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="02569-123">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="02569-124">A partir daqui, os administradores podem usar um par de métodos que permitem a gravação e/ou exibição do log avançado em formato XML ou HTML.</span><span class="sxs-lookup"><span data-stu-id="02569-124">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="02569-125">Por exemplo, os administradores do Lync Server 2010 podem executar o cmdlet **Test-CsRegistration** usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="02569-125">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="02569-126">Os administradores têm a opção de incluir o parâmetro OutLoggerVariable seguido pelo nome de uma variável à escolha deles:</span><span class="sxs-lookup"><span data-stu-id="02569-126">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="02569-p105">Não use o caractere $ como prefixo do nome da variável. Use um nome de variável como RegistrationTest e não $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="02569-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="02569-129">O comando precedente produz um conteúdo semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="02569-129">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="02569-p106">No entanto, informações muito mais detalhadas do que a mensagem de erro mostrada acima estão disponíveis para essa falha. Para acessar essas informações em formato HTML, use um comando semelhante a este para salvar as informações armazenadas na variável RegistrationTest em um arquivo HTML:</span><span class="sxs-lookup"><span data-stu-id="02569-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="02569-132">Como alternativa, é possível usar o método ToXML() para salvar os dados em um arquivo XML:</span><span class="sxs-lookup"><span data-stu-id="02569-132">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="02569-133">Esses arquivos podem ser exibidos usando o Internet Explorer, o Visual Studio ou qualquer outro aplicativo capaz de abrir arquivos HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="02569-133">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="02569-134">As transações sintéticas executadas de dentro do System Center Operations Manager gerarão automaticamente esses arquivos de log para falhas.</span><span class="sxs-lookup"><span data-stu-id="02569-134">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="02569-135">No entanto, esses logs não serão gerados se a execução falhar antes que o Windows PowerShell possa carregar e executar a transação sintética.</span><span class="sxs-lookup"><span data-stu-id="02569-135">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="02569-136">Por padrão, o Lync Server 2013 salva arquivos de log em uma pasta que não é compartilhada.</span><span class="sxs-lookup"><span data-stu-id="02569-136">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="02569-137">Para tornar esses logs prontamente acessíveis, você deve compartilhar esta pasta (por exemplo, \\ \\ ATL-Watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="02569-137">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

