---
title: 'Lync Server 2013: verificando logs de eventos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a15fb690dc213dbe22377b988f82dd59d6eb8a03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="aa7e2-102">Verificar logs de eventos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa7e2-102">Checking event logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa7e2-103">_**Última modificação do tópico:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="aa7e2-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="aa7e2-104">Você pode usar o [Visualizador de eventos do Windows](http://go.microsoft.com/fwlink/p/?linkid=314067) para exibir logs de eventos e obter informações sobre falhas de serviço, erros de replicação no AD DS e avisos sobre recursos do sistema, como memória virtual e espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-104">You can use [Windows Event Viewer](http://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="aa7e2-105">O Visualizador de eventos está incluído no Windows Server 2008 e 2012.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="aa7e2-106">Na ferramenta de log do Lync Server 2013, quando você finaliza a sessão de depuração, clique em **analisar arquivos de log** para exibir os arquivos de log usando a ferramenta Snooper.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="aa7e2-107">O Visualizador de eventos mantém logs sobre eventos de aplicativo, segurança e sistema no computador.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="aa7e2-108">O Lync Server 2013 e os avisos de relatório do Windows e as condições de erro para os logs de eventos.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="aa7e2-109">Portanto, revise os logs de eventos diariamente.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="aa7e2-110">Use o Visualizador de eventos para:</span><span class="sxs-lookup"><span data-stu-id="aa7e2-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="aa7e2-111">Exibir e gerenciar logs de eventos.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-111">View and manage event logs.</span></span>

  - <span data-ttu-id="aa7e2-112">Obter informações sobre problemas de hardware, software e sistema que devem ser resolvidos.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="aa7e2-113">Identificar tendências que exigem ação futura.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-113">Identify trends that require future action.</span></span>

<span data-ttu-id="aa7e2-114">Um servidor que esteja executando o Lync Server em um sistema operacional Windows Server registra eventos em quatro tipos de logs:</span><span class="sxs-lookup"><span data-stu-id="aa7e2-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="aa7e2-115">**Logs de aplicativo**   o log de aplicativo contém eventos registrados por aplicativos ou programas.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="aa7e2-116">Os desenvolvedores determinam quais eventos registrar.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-116">Developers determine which events to log.</span></span> <span data-ttu-id="aa7e2-117">Por exemplo, um programa de banco de dados pode gravar um erro de arquivo no log de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="aa7e2-118">A maioria dos eventos relacionados ao Lync Server 2013 aparece no log de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="aa7e2-119">**Logs de segurança**   o log de segurança registra eventos como tentativas de logon válidas e não válidas, além de eventos relacionados ao uso de recursos, como criar, abrir ou excluir arquivos ou outros objetos.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="aa7e2-120">Por exemplo, se a auditoria de logon estiver habilitada, as tentativas de fazer logon no sistema são registradas no log de segurança.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="aa7e2-121">**Logs de sistema**   o log de sistema contém eventos registrados pelos componentes de sistema do Windows.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="aa7e2-122">Por exemplo, a falha de um driver ou de outro componente de sistema para carregar durante a inicialização é registrada no log do sistema.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="aa7e2-123">Os tipos de eventos registrados pelos componentes do sistema são pré-determinados pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="aa7e2-124">**Lync Server 2013**   a ferramenta de registro em log registra eventos significativos relacionados a autenticação, conexões e ações do usuário.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="aa7e2-125">Após habilitar o log de diagnóstico, você pode exibir as entradas de log no Visualizador de eventos.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa7e2-126">Não é recomendável usar as configurações de log máximo, a menos que você seja instruído a fazer isso por meio dos serviços de suporte ao cliente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="aa7e2-127">O registro em log máximo esvazia recursos significativos e pode dar muitos "falsos positivos", ou seja, erros que são registrados apenas no log máximo, mas são realmente esperados e não têm uma causa de preocupação.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="aa7e2-128">Recomendamos também que você não habilite o log de diagnóstico permanentemente.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="aa7e2-129">Use-o somente durante a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="aa7e2-130">Em cada log do Visualizador de eventos, o Lync Server 2013 registra informações sobre eventos, avisos e erros.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="aa7e2-131">Monitore esses logs em detalhes para controlar os tipos de transações sendo realizadas nos servidores do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="aa7e2-132">Você deve arquivar periodicamente os logs ou usar a substituição automática para evitar ficar sem espaço.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="aa7e2-133">Como os arquivos de log podem ocupar uma quantidade de espaço finita, aumente o tamanho do log (por exemplo, 50 MB) e defina-o para que seja substituído para que o servidor do Lync Server 2013 possa continuar a gravar novos eventos.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="aa7e2-134">Você também pode automatizar a administração de logs de eventos usando as seguintes ferramentas e tecnologias:</span><span class="sxs-lookup"><span data-stu-id="aa7e2-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="aa7e2-135">O System Center Operations Manager monitora a integridade e o uso de servidores do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="aa7e2-136">O pacote de gerenciamento do Lync Server 2013 para o Operations Manager estende o Operations Manager fornecendo monitoramento especializado para servidores que executam o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="aa7e2-137">O pacote de gerenciamento do Lync Server 2013 para o Operations Manager monitora a edição Standard e Enterprise do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="aa7e2-138">Este lançamento também incorpora o pacote de gerenciamento da qualidade da experiência (QoE) que era anteriormente um pacote de gerenciamento separado.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="aa7e2-139">Os tipos monitorados são entradas de log de eventos, contadores de desempenho e monitoramento de estado do QoE.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="aa7e2-140">Esta versão do pacote de gerenciamento monitora apenas o Lync Server 2013 e o 2010 e não pode ser usada para monitorar o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="aa7e2-141">O pacote de gerenciamento fornece os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="aa7e2-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="aa7e2-142">Alertas que indicam serviço que afeta eventos</span><span class="sxs-lookup"><span data-stu-id="aa7e2-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="aa7e2-143">Alertas indicando configuração e outros problemas de impacto que não são de serviço</span><span class="sxs-lookup"><span data-stu-id="aa7e2-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="aa7e2-144">Monitoramento de estado dos serviços do Lync Server</span><span class="sxs-lookup"><span data-stu-id="aa7e2-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="aa7e2-145">Conhecimento do produto: causa e resolução de problemas identificados</span><span class="sxs-lookup"><span data-stu-id="aa7e2-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="aa7e2-146">Para obter mais informações sobre o pacote de gerenciamento do Lync Server 2013, consulte [Monitoring Lync server 2013 com System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span><span class="sxs-lookup"><span data-stu-id="aa7e2-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="aa7e2-147">**Event Comb**   a ferramenta Event Comb coleta eventos específicos dos logs de eventos de vários computadores em um local central.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="aa7e2-148">Ele permite que você informe somente as IDs de evento ou as fontes de eventos que ele especifica.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="aa7e2-149">Para obter mais informações sobre o Event Comb, consulte o site de [ferramentas de gerenciamento e bloqueio de conta](http://go.microsoft.com/fwlink/?linkid=35607) .</span><span class="sxs-lookup"><span data-stu-id="aa7e2-149">For more information about Event Comb, see the [Account Lockout and Management Tools](http://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="aa7e2-150">**Disparadores de eventos**   no Windows Server 2012 você pode "anexar uma tarefa a este evento" dentro do Visualizador de eventos do Windows — onde um administrador pode executar um programa, enviar uma mensagem de email ou exibir uma mensagem na tela.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="aa7e2-151">Para obter mais informações sobre esse recurso, consulte o tópico Windows Server 2008 R2 [executar uma tarefa em resposta a um determinado evento](http://technet.microsoft.com/library/cc748900.aspx).</span><span class="sxs-lookup"><span data-stu-id="aa7e2-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](http://technet.microsoft.com/library/cc748900.aspx).</span></span> <span data-ttu-id="aa7e2-152">Você também pode usar ferramentas de linha de comando, como ' EventTrigger. exe ', para criar e consultar logs de eventos e associar programas a determinados eventos registrados.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="aa7e2-153">Usando Eventtriggers. exe, você pode criar disparadores de eventos que executam programas quando ocorrem eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="aa7e2-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="aa7e2-154">Confira Também</span><span class="sxs-lookup"><span data-stu-id="aa7e2-154">See Also</span></span>


[<span data-ttu-id="aa7e2-155">Visualizador de eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="aa7e2-155">Windows Event Viewer</span></span>](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

