---
title: 'Lync Server 2013: verificando logs de eventos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1506f94f0a049a6bb4fdd90875dae50548b5f516
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="959d0-102">Verificar logs de eventos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="959d0-102">Checking event logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="959d0-103">_**Tópico da última modificação:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="959d0-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="959d0-104">Você pode usar o [Visualizador de eventos do Windows](http://go.microsoft.com/fwlink/p/?linkid=314067) para exibir logs de eventos e obter informações sobre falhas de serviço, erros de replicação no AD DS e avisos sobre recursos do sistema, como memória virtual e espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="959d0-104">You can use [Windows Event Viewer](http://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="959d0-105">O Visualizador de eventos está incluído no Windows Server 2008 e no 2012.</span><span class="sxs-lookup"><span data-stu-id="959d0-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="959d0-106">Na ferramenta de log do Lync Server 2013, quando você terminar a sessão de depuração, clique em **analisar arquivos de log** para ver os arquivos de log usando a ferramenta de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="959d0-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="959d0-107">O Visualizador de eventos mantém registros sobre eventos de aplicativo, segurança e sistema no computador.</span><span class="sxs-lookup"><span data-stu-id="959d0-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="959d0-108">O Lync Server 2013 e o Windows reportam avisos e condições de erro para os logs de eventos.</span><span class="sxs-lookup"><span data-stu-id="959d0-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="959d0-109">Portanto, examine os logs de eventos diariamente.</span><span class="sxs-lookup"><span data-stu-id="959d0-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="959d0-110">Use o Visualizador de eventos para:</span><span class="sxs-lookup"><span data-stu-id="959d0-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="959d0-111">Exibir e gerenciar logs de eventos.</span><span class="sxs-lookup"><span data-stu-id="959d0-111">View and manage event logs.</span></span>

  - <span data-ttu-id="959d0-112">Obter informações sobre hardware, software e problemas do sistema que devem ser resolvidos.</span><span class="sxs-lookup"><span data-stu-id="959d0-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="959d0-113">Identifique tendências que exigem uma ação futura.</span><span class="sxs-lookup"><span data-stu-id="959d0-113">Identify trends that require future action.</span></span>

<span data-ttu-id="959d0-114">Um servidor que esteja executando o Lync Server em um sistema operacional Windows Server registra eventos em quatro tipos de logs:</span><span class="sxs-lookup"><span data-stu-id="959d0-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="959d0-115">**Registros de aplicativos**   o log do aplicativo contém eventos registrados por aplicativos ou programas.</span><span class="sxs-lookup"><span data-stu-id="959d0-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="959d0-116">Os desenvolvedores determinam quais eventos registrar.</span><span class="sxs-lookup"><span data-stu-id="959d0-116">Developers determine which events to log.</span></span> <span data-ttu-id="959d0-117">Por exemplo, um programa de banco de dados pode gravar um erro de arquivo no log do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="959d0-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="959d0-118">A maioria dos eventos relacionados ao Lync Server 2013 aparecem no log do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="959d0-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="959d0-119">**Logs de segurança**   o log de segurança registra eventos como, por exemplo, tentativas de logon válidas e não válidas, além de eventos relacionados ao uso de recursos, como criar, abrir ou excluir arquivos ou outros objetos.</span><span class="sxs-lookup"><span data-stu-id="959d0-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="959d0-120">Por exemplo, se a auditoria de logon estiver habilitada, as tentativas de fazer logon no sistema serão gravadas no log de segurança.</span><span class="sxs-lookup"><span data-stu-id="959d0-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="959d0-121">**Registros do sistema**   o log do sistema contém eventos registrados pelos componentes de sistema do Windows.</span><span class="sxs-lookup"><span data-stu-id="959d0-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="959d0-122">Por exemplo, a falha de um driver ou outro componente do sistema a ser carregado durante a inicialização é gravada no log do sistema.</span><span class="sxs-lookup"><span data-stu-id="959d0-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="959d0-123">Os tipos de eventos registrados pelos componentes do sistema são predeterminados pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="959d0-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="959d0-124">**Lync Server 2013**   a ferramenta de log registra eventos significativos relacionados a autenticação, conexões e ações do usuário.</span><span class="sxs-lookup"><span data-stu-id="959d0-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="959d0-125">Depois de habilitar o log de diagnóstico, você pode exibir as entradas do log no Visualizador de eventos.</span><span class="sxs-lookup"><span data-stu-id="959d0-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="959d0-126">Não recomendamos que você use as configurações de registro em log máximo, a menos que seja instruído a fazer isso pelos serviços de suporte ao cliente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="959d0-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="959d0-127">O registro em log máximo esvazia recursos significativos e pode dar muitos "falsos positivos", ou seja, erros que são registrados apenas no máximo de logs, mas são realmente esperados e não são uma causa da preocupação.</span><span class="sxs-lookup"><span data-stu-id="959d0-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="959d0-128">Também recomendamos que você não habilite o log de diagnóstico permanentemente.</span><span class="sxs-lookup"><span data-stu-id="959d0-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="959d0-129">Use-o somente durante a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="959d0-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="959d0-130">Em cada log de visualizador de eventos, o Lync Server 2013 registra eventos informativos, de aviso e de erro.</span><span class="sxs-lookup"><span data-stu-id="959d0-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="959d0-131">Monitore esses logs de perto para controlar os tipos de transações que estão sendo conduzidos nos servidores do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="959d0-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="959d0-132">Você deve arquivar periodicamente os logs ou usar a substituição automática para evitar ficar sem espaço.</span><span class="sxs-lookup"><span data-stu-id="959d0-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="959d0-133">Como os arquivos de log podem ocupar uma quantidade finita de espaço, aumente o tamanho do log (por exemplo, para 50 MB) e defina-o para substituir para que o servidor do Lync 2013 possa continuar a gravar novos eventos.</span><span class="sxs-lookup"><span data-stu-id="959d0-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="959d0-134">Você também pode automatizar a administração do log de eventos usando as seguintes ferramentas e tecnologias:</span><span class="sxs-lookup"><span data-stu-id="959d0-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="959d0-135">O System Center Operations Manager monitora a integridade e o uso dos servidores do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="959d0-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="959d0-136">O pacote de gerenciamento do Lync Server 2013 para Operations Manager estende o Operations Manager fornecendo monitoramento especializado para servidores que executam o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="959d0-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="959d0-137">O pacote de gerenciamento do Lync Server 2013 para Operations Manager monitora a edição Standard e Enterprise do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="959d0-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="959d0-138">Esta versão também incorpora o pacote de gerenciamento de qualidade da experiência (QoE) que anteriormente era um pacote de gerenciamento separado.</span><span class="sxs-lookup"><span data-stu-id="959d0-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="959d0-139">Os tipos monitorados são entradas do log de eventos, contadores de desempenho e monitoramento de estado de QoE.</span><span class="sxs-lookup"><span data-stu-id="959d0-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="959d0-140">Esta versão do pacote de gerenciamento só monitora o Lync Server 2013 e o 2010 e não pode ser usada para monitorar o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="959d0-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="959d0-141">O pacote de gerenciamento fornece os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="959d0-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="959d0-142">Alertas que indicam serviço que afeta eventos</span><span class="sxs-lookup"><span data-stu-id="959d0-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="959d0-143">Alertas que indicam configuração e outros problemas de impacto não relacionado ao serviço</span><span class="sxs-lookup"><span data-stu-id="959d0-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="959d0-144">Monitoramento de estado dos serviços do Lync Server</span><span class="sxs-lookup"><span data-stu-id="959d0-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="959d0-145">Conhecimento do produto: causa e resolução de problemas identificados</span><span class="sxs-lookup"><span data-stu-id="959d0-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="959d0-146">Para obter mais informações sobre o pacote de gerenciamento do Lync Server 2013, consulte Monitorando o [Lync server 2013 com o System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span><span class="sxs-lookup"><span data-stu-id="959d0-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="959d0-147">**Event Comb**   a ferramenta Event Comb coleta eventos específicos dos logs de eventos de vários computadores em um local central.</span><span class="sxs-lookup"><span data-stu-id="959d0-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="959d0-148">Ele permite que você relate apenas as identificações de evento ou fontes de evento que ele especifica.</span><span class="sxs-lookup"><span data-stu-id="959d0-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="959d0-149">Para obter mais informações sobre o Event Comb, consulte o site de [ferramentas de gerenciamento e bloqueio de conta](http://go.microsoft.com/fwlink/?linkid=35607) .</span><span class="sxs-lookup"><span data-stu-id="959d0-149">For more information about Event Comb, see the [Account Lockout and Management Tools](http://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="959d0-150">**Gatilhos de evento**   no Windows Server 2012 você pode "anexar uma tarefa a este evento" dentro do Visualizador de eventos do Windows, onde um administrador pode executar um programa, enviar uma mensagem de email ou exibir uma mensagem na tela.</span><span class="sxs-lookup"><span data-stu-id="959d0-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="959d0-151">Para obter mais informações sobre esse recurso, consulte o tópico sobre o Windows Server 2008 R2 [executar uma tarefa em resposta a um determinado evento](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span><span class="sxs-lookup"><span data-stu-id="959d0-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span></span> <span data-ttu-id="959d0-152">Você também pode usar ferramentas de linha de comando, como ' EventTrigger. exe ', para criar e consultar logs de eventos e associar programas a determinados eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="959d0-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="959d0-153">Usando Eventtriggers. exe, você pode criar gatilhos de eventos que executam programas quando ocorrem eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="959d0-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="959d0-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="959d0-154">See Also</span></span>


[<span data-ttu-id="959d0-155">Visualizador de eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="959d0-155">Windows Event Viewer</span></span>](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

