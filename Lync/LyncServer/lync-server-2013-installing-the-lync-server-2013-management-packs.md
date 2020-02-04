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
ms.openlocfilehash: ffc102eccdbaa941e2691df88899c0cc01348838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="2fba6-102">Instalar os pacotes de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fba6-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fba6-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2fba6-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2fba6-104">Por si só, o System Center Operations Manager tem a capacidade de monitorar apenas uma pequena parte do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="2fba6-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="2fba6-105">No entanto, você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento, software que determina quais itens o System Center Operations Manager pode monitorar, incluindo como esses itens devem ser monitorados e como os alertas devem ser disparado e reportado.</span><span class="sxs-lookup"><span data-stu-id="2fba6-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="2fba6-106">O Microsoft Lync Server 2013 inclui dois pacotes de gerenciamento do System Center Operations Manager que fornecem os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="2fba6-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="2fba6-107">O componente e o pacote de gerenciamento de usuários (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) controla problemas do Lync Server gravados em logs de eventos, registrados por contadores de desempenho, ou registrados nos registros de detalhes de chamadas (CDR) ou na qualidade da experiência (QoE) bancos.</span><span class="sxs-lookup"><span data-stu-id="2fba6-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="2fba6-108">Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS (serviço de mensagens curtas).</span><span class="sxs-lookup"><span data-stu-id="2fba6-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="2fba6-109">SMS é a tecnologia usada para enviar mensagens de texto de um dispositivo móvel para outro.</span><span class="sxs-lookup"><span data-stu-id="2fba6-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2fba6-110">Para obter mais informações sobre como configurar a notificação do Operations Manager, consulte Configurando a notificação na biblioteca do TechNet em <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span><span class="sxs-lookup"><span data-stu-id="2fba6-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="2fba6-111">O pacote de monitoramento ativo (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Lync Server, como fazer logon no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado no telefone público comutado rede (PSTN).</span><span class="sxs-lookup"><span data-stu-id="2fba6-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="2fba6-112">Esses testes são conduzidos usando cmdlets de transação sintéticas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2fba6-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="2fba6-113">Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagens instantâneas entre um par de usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="2fba6-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="2fba6-114">Se essa conversa de mensagens simulada falhar, um alerta será gerado.</span><span class="sxs-lookup"><span data-stu-id="2fba6-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="2fba6-115">Os dois pacotes de gerenciamento incluídos no Lync Server 2013 incluem uma grande quantidade de aprimoramentos nos pacotes de gerenciamento usados com o Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2fba6-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="2fba6-116">Por exemplo, o pacote de gerenciamento do componente do Lync Server 2013 não está limitado ao monitoramento próprio do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2fba6-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="2fba6-117">Além de monitorar os logs de eventos e os contadores de desempenho do Lync Server, o pacote de gerenciamento de componentes também pode controlar o desempenho de itens cruciais e emitir alertas para itens cruciais, como:</span><span class="sxs-lookup"><span data-stu-id="2fba6-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="2fba6-118">**Os alertas dos serviços de informações da Internet (IIS)**   serão emitidos se os serviços de informações da Internet ficarão offline.</span><span class="sxs-lookup"><span data-stu-id="2fba6-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="2fba6-119">Isso é importante, pois os serviços Web do Lync Server dependem do IIS.</span><span class="sxs-lookup"><span data-stu-id="2fba6-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="2fba6-120">\*\*\*\*   Alertas de uso de processo serão emitidos se os recursos do sistema (como a memória disponível) começarem a ser baixados.</span><span class="sxs-lookup"><span data-stu-id="2fba6-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="2fba6-121">Esses alertas serão emitidos mesmo se o Lync Server não for responsável pelo alto uso do sistema.</span><span class="sxs-lookup"><span data-stu-id="2fba6-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="2fba6-122">\*\*\*\*   Os alertas de eventos de falha do computador serão emitidos em caso de um problema de hardware ou software que ameaça a viabilidade de um servidor.</span><span class="sxs-lookup"><span data-stu-id="2fba6-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="2fba6-123">Por exemplo, os administradores do Lync Server serão notificados se um servidor parecer estar em perigo de ocorrer uma falha no disco rígido.</span><span class="sxs-lookup"><span data-stu-id="2fba6-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="2fba6-124">Os novos pacotes de gerenciamento também apresentam relatórios avançados.</span><span class="sxs-lookup"><span data-stu-id="2fba6-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="2fba6-125">Os novos relatórios do Lync Server 2013 incluem:</span><span class="sxs-lookup"><span data-stu-id="2fba6-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="2fba6-126">**Relatório de disponibilidade do cenário de ponta a ponta**   este relatório detalha a disponibilidade/tempo de atividade dos serviços principais do Lync Server, como registro ou presença.</span><span class="sxs-lookup"><span data-stu-id="2fba6-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="2fba6-127">**Relatório de capacidade**   usando informações de contador de desempenho, esse relatório mostra tendências para componentes do sistema, como disponibilidade da memória e uso do processador.</span><span class="sxs-lookup"><span data-stu-id="2fba6-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="2fba6-128">**Relatório de componente**   este relatório lista os principais geradores de alertas agrupados pelo componente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2fba6-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="2fba6-129">Além desses relatórios predefinidos, os pacotes de gerenciamento do Lync Server 2013 automaticamente relatam alertas para a confiabilidade das chamadas (métricas medidas por gravação de detalhes de chamadas) e Estados de QoE (métricas medidas por qualidade de experiência).</span><span class="sxs-lookup"><span data-stu-id="2fba6-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="2fba6-130">Se você tiver habilitado a gravação de detalhes da chamada, poderá revisar os alertas de confiabilidade da chamada completando o procedimento a seguir no console do System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="2fba6-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="2fba6-131">Expanda **monitoramento**, expanda **integridade do Microsoft Lync Server 2013**, expanda a **confiabilidade da chamada e a qualidade da mídia**e clique em **chamar confiabilidade**.</span><span class="sxs-lookup"><span data-stu-id="2fba6-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="2fba6-132">Para ver os alertas de qualidade da experiência, conclua este procedimento no console do System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="2fba6-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="2fba6-133">Expanda **monitoramento**, expanda **integridade do Microsoft Lync Server 2013**, expanda a **confiabilidade da chamada e a qualidade da mídia**e expanda qualidade da **mídia**.</span><span class="sxs-lookup"><span data-stu-id="2fba6-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="2fba6-134">Os pacotes de gerenciamento do Lync Server 2013 agora usam a descoberta em nível de máquina em vez do mecanismo de descoberta central usado no Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2fba6-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="2fba6-135">Isso significa que cada agente do System Center essencialmente descobre e relata sua existência ao servidor central de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2fba6-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="2fba6-136">O uso da descoberta no nível da máquina simplifica a administração da infraestrutura do sistema central e também permite diferentes versões dos pacotes de gerenciamento do Lync Server (por exemplo, pacotes de gerenciamento do Lync Server 2010 e pacotes de gerenciamento do Lync Server 2013) para exist.</span><span class="sxs-lookup"><span data-stu-id="2fba6-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

