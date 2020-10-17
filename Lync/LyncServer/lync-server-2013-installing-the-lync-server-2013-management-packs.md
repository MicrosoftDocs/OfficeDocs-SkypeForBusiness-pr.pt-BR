---
title: 'Lync Server 2013: instalando os pacotes de gerenciamento do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ff5b636c4cb2eaea2b3f7caa5681a26a8a59dc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534808"
---
# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="4bfdc-102">Instalando os pacotes de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bfdc-102">Installing the Lync Server 2013 management packs</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bfdc-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4bfdc-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4bfdc-104">Sozinho, o System Center Operations Manager tem a capacidade de monitorar apenas uma pequena parte do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="4bfdc-105">No entanto, você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento, software que determina quais itens o System Center Operations Manager pode monitorar, incluindo como esses itens devem ser monitorados e como os alertas devem ser acionados e relatados.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="4bfdc-106">O Microsoft Lync Server 2013 inclui dois pacotes de gerenciamento do System Center Operations Manager que oferecem os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="4bfdc-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="4bfdc-107">O pacote de gerenciamento de componente e usuário (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) acompanha os problemas do Lync Server registrados em logs de eventos, registrados por contadores de desempenho ou registrados nos bancos de dados de registro de detalhes de chamadas (CDR) ou da qualidade da experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="4bfdc-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="4bfdc-108">Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS (Short Message Service).</span><span class="sxs-lookup"><span data-stu-id="4bfdc-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="4bfdc-109">SMS é a tecnologia usada para enviar mensagens de texto de um dispositivo móvel para outro.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4bfdc-110">Para obter mais informações sobre como configurar a notificação do Operations Manager, consulte Configuring Notification na biblioteca do TechNet em <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A> .</span><span class="sxs-lookup"><span data-stu-id="4bfdc-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="4bfdc-111">O pacote de monitoramento ativo (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Lync Server, como fazer logon no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado na rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="4bfdc-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="4bfdc-112">Esses testes são conduzidos usando os cmdlets de transação sintéticas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="4bfdc-113">Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagem instantânea entre um par de usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="4bfdc-114">Um alerta será gerado em caso de falha nessa conversa de mensagens simulada.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="4bfdc-115">Os dois pacotes de gerenciamento incluídos no Lync Server 2013 incluem um grande número de aprimoramentos nos pacotes de gerenciamento usados com o Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="4bfdc-116">Por exemplo, o pacote de gerenciamento do componente do Lync Server 2013 não está limitado ao monitoramento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="4bfdc-117">Além de monitorar os logs de eventos e os contadores de desempenho do Lync Server, o pacote de gerenciamento de componente também pode rastrear o desempenho e emitir alertas para itens cruciais, como:</span><span class="sxs-lookup"><span data-stu-id="4bfdc-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="4bfdc-118">**Serviços de informações da Internet (IIS)**     Os alertas serão emitidos se o serviços de informações da Internet ficar offline.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="4bfdc-119">Isso é importante porque os serviços Web do Lync Server dependem do IIS.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="4bfdc-120">**Uso**     do processo Os alertas serão emitidos se os recursos do sistema (como memória disponível) começarem a ser executados em baixa.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="4bfdc-121">Esses alertas serão emitidos mesmo se o Lync Server não for responsável pelo alto uso do sistema.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="4bfdc-122">Eventos de falha do **computador**     Os alertas serão emitidos no caso de um problema de hardware ou software que ameaça a viabilidade de um servidor.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="4bfdc-123">Por exemplo, os administradores do Lync Server serão notificados se um servidor parece estar em perigo de ocorrer uma falha no disco rígido.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="4bfdc-124">Os novos pacotes de gerenciamento também dispõem de relatórios avançados.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="4bfdc-125">Os novos relatórios do Lync Server 2013 incluem:</span><span class="sxs-lookup"><span data-stu-id="4bfdc-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="4bfdc-126">**Relatório de disponibilidade de cenário de ponta a ponta**     Este relatório detalha a disponibilidade/tempo de atividade dos serviços principais do Lync Server, como registro ou presença.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="4bfdc-127">**Relatório**     de capacidade Usando informações de contador de desempenho, este relatório mostra tendências para componentes do sistema, como disponibilidade de memória e uso do processador.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="4bfdc-128">**Relatório**     de componente Este relatório lista os principais geradores de alerta agrupados pelo componente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="4bfdc-129">Além desses relatórios predefinidos, os pacotes de gerenciamento do Lync Server 2013 relatam automaticamente alertas para a confiabilidade da chamada (métricas medidas por registro de detalhes das chamadas) e Estados de QoE (métricas medidas por qualidade da experiência).</span><span class="sxs-lookup"><span data-stu-id="4bfdc-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="4bfdc-130">Se você tiver habilitado a gravação de detalhes da chamada, poderá revisar os alertas de confiabilidade de chamada ao concluir o seguinte procedimento no console do System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="4bfdc-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="4bfdc-131">Expanda **Monitoramento**, **Integridade do Microsoft Lync Server 2013**, **Confiabilidade de chamada e qualidade de mídia**, e clique em **Confiabilidade de chamada**.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="4bfdc-132">Para exibir os alertas de qualidade da experiência, conclua este procedimento no console do System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="4bfdc-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="4bfdc-133">Expanda **Monitoramento**, **Integridade do Microsoft Lync Server 2013**, **Confiabilidade de chamada e qualidade de mídia**, e, em seguida, expanda **Qualidade de mídia**.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="4bfdc-134">Os pacotes de gerenciamento do Lync Server 2013 agora usam a descoberta de nível de máquina em vez do mecanismo de descoberta central usado no Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="4bfdc-135">Isso significa que cada agente do System Center é basicamente descoberto e relata sua existência com o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="4bfdc-136">O uso da descoberta no nível da máquina simplifica a administração da infraestrutura do System Center e também permite diferentes versões dos pacotes de gerenciamento do Lync Server (por exemplo, pacotes de gerenciamento do Lync Server 2010 e pacotes de gerenciamento do Lync Server 2013) para coexistir.</span><span class="sxs-lookup"><span data-stu-id="4bfdc-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

