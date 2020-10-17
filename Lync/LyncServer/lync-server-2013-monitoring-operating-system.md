---
title: 'Lync Server 2013: monitorando o sistema operacional'
description: 'Lync Server 2013: monitorando o sistema operacional.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9454b91a5f55467f93b41752686b4b0d727d935
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548057"
---
# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="55fbb-103">Monitorando o sistema operacional no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55fbb-103">Monitoring operating system in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55fbb-104">_**Última modificação do tópico:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="55fbb-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="55fbb-105">Você deve monitorar o desempenho de todos os servidores e componentes no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55fbb-105">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="55fbb-106">Obviamente, um dos componentes mais importantes é o próprio sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="55fbb-106">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="55fbb-107">O Lync Server 2013 suporta edições x64 do:</span><span class="sxs-lookup"><span data-stu-id="55fbb-107">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="55fbb-108">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="55fbb-108">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="55fbb-109">Windows Server 2012 e Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="55fbb-109">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="55fbb-110">A maneira mais transparente de monitorar um sistema operacional é usar o pacote de gerenciamento do sistema operacional Windows Server.</span><span class="sxs-lookup"><span data-stu-id="55fbb-110">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="55fbb-111">Ele fornece os princípios básicos de monitoramento, como desempenho, integridade e disponibilidade para computadores que executam o Windows Server 2012, o Windows Server 2012 R2 e o Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="55fbb-111">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="55fbb-112">Ao detectar, alertar e responder automaticamente a eventos importantes e indicadores de desempenho, esses pacotes de gerenciamento reduzem os tempos de resolução de problemas e aumentam a disponibilidade e o desempenho geral dos sistemas que executam os sistemas operacionais Windows Server.</span><span class="sxs-lookup"><span data-stu-id="55fbb-112">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="55fbb-113">Além de pacotes de gerenciamento do Windows Server relevantes para o System Center Operations Manager, as seguintes ferramentas e recursos do sistema podem ser usados para monitorar a integridade do sistema operacional (dependendo da versão do sistema operacional).</span><span class="sxs-lookup"><span data-stu-id="55fbb-113">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="55fbb-114">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="55fbb-114">Windows Server 2008 R2</span></span>

<span data-ttu-id="55fbb-115">O Windows Server 2008 R2 inclui os seguintes recursos e ferramentas adicionais para ajudar os administradores com o monitoramento e o gerenciamento básicos do sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="55fbb-115">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="55fbb-116">O **Monitor de recursos do Windows** é uma poderosa ferramenta para entender como os recursos do sistema são usados por processos e serviços.</span><span class="sxs-lookup"><span data-stu-id="55fbb-116">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services.</span></span> <span data-ttu-id="55fbb-117">Além de monitorar o uso de recursos em tempo real, um monitor de recursos pode ajudar a analisar processos sem resposta, identificar quais aplicativos estão usando arquivos e controlar processos e serviços.</span><span class="sxs-lookup"><span data-stu-id="55fbb-117">In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="55fbb-118">O **componente de análise de confiabilidade** é um agente de caixa de entrada que fornece informações detalhadas sobre o uso e a confiabilidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="55fbb-118">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability.</span></span> <span data-ttu-id="55fbb-119">Essas informações são expostas por meio de uma interface WMI para torná-la disponível para consumo por sistemas de leitores portáteis.</span><span class="sxs-lookup"><span data-stu-id="55fbb-119">This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems.</span></span> <span data-ttu-id="55fbb-120">Ao expor o componente de análise de confiabilidade por meio de uma interface WMI, os desenvolvedores podem monitorar e analisar aplicativos, aumentando a confiabilidade e o desempenho.</span><span class="sxs-lookup"><span data-stu-id="55fbb-120">By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="55fbb-121">O **Windows Server 2008 R2** usa o componente de análise de confiabilidade interno para calcular um índice de confiabilidade, que fornece informações sobre a estabilidade e o uso geral do sistema ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="55fbb-121">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="55fbb-122">O componente de análise de confiabilidade também mantém o controle de qualquer alteração importante no sistema que provavelmente influenciará a estabilidade, como as atualizações do Windows e as instalações de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="55fbb-122">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="55fbb-123">Monitor de desempenho e confiabilidade do Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="55fbb-123">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="55fbb-124">O monitor de confiabilidade e desempenho do Windows é um snap-in do MMC que combina a funcionalidade de ferramentas autônomas anteriores, incluindo logs e alertas de desempenho, supervisor de desempenho do servidor e monitor do sistema.</span><span class="sxs-lookup"><span data-stu-id="55fbb-124">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor.</span></span> <span data-ttu-id="55fbb-125">Ele fornece uma interface gráfica para personalizar a coleta de dados de desempenho e as sessões de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="55fbb-125">It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="55fbb-126">Também inclui o monitor de confiabilidade, um snap-in do MMC que rastreia alterações no sistema e as compara às alterações na estabilidade do sistema e fornece uma exibição gráfica de sua relação.</span><span class="sxs-lookup"><span data-stu-id="55fbb-126">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="55fbb-127">Monitor de desempenho e confiabilidade do Windows</span><span class="sxs-lookup"><span data-stu-id="55fbb-127">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="55fbb-128">Enquanto o monitor de confiabilidade e desempenho do Windows combina funcionalidades de algumas ferramentas autônomas antigas, como logs e alertas de desempenho, e o monitor de sistema e o supervisor de desempenho do servidor, ele também fornece uma nova funcionalidade ao Windows Server 2008 e ao Windows Server 2008 R2, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="55fbb-128">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="55fbb-129">Conjuntos de coletores de dados</span><span class="sxs-lookup"><span data-stu-id="55fbb-129">Data Collector Sets</span></span>

  - <span data-ttu-id="55fbb-130">Exibição de recurso</span><span class="sxs-lookup"><span data-stu-id="55fbb-130">Resource View</span></span>

  - <span data-ttu-id="55fbb-131">Monitor de confiabilidade</span><span class="sxs-lookup"><span data-stu-id="55fbb-131">Reliability Monitor</span></span>

  - <span data-ttu-id="55fbb-132">Assistentes e modelos para a criação de logs</span><span class="sxs-lookup"><span data-stu-id="55fbb-132">Wizards and templates for creating logs</span></span>

<span data-ttu-id="55fbb-133">**Conjunto de coletores de dados** agrupa coletores de dados em elementos reutilizáveis para uso com diferentes cenários de monitoramento de desempenho.</span><span class="sxs-lookup"><span data-stu-id="55fbb-133">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios.</span></span> <span data-ttu-id="55fbb-134">Após um grupo de coletores de dados ser armazenado como um conjunto de coletores de dados, operações como agendamento podem ser aplicadas ao conjunto inteiro por meio de uma única alteração de propriedade. O monitor de confiabilidade e desempenho do Windows inclui modelos de conjunto de coletores de dados padrão para ajudar os administradores do sistema a começar a coletar imediatamente os dados de desempenho específicos para uma função de servidor ou um cenário de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="55fbb-134">After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="55fbb-135">A home page do monitor de confiabilidade e desempenho do Windows é a nova tela do **modo de exibição de recursos** , que fornece uma visão geral gráfica em tempo real de uso de CPU, disco, rede e memória.</span><span class="sxs-lookup"><span data-stu-id="55fbb-135">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage.</span></span> <span data-ttu-id="55fbb-136">Ao expandir cada um desses elementos monitorados, os administradores do sistema podem identificar quais processos estão usando quais recursos.</span><span class="sxs-lookup"><span data-stu-id="55fbb-136">By expanding each of these monitored elements, system administrators can identify which processes are using which resources.</span></span> <span data-ttu-id="55fbb-137">Nas versões anteriores do Windows, esses dados em tempo real, específicos do processo, estavam disponíveis apenas na forma limitada no Gerenciador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="55fbb-137">In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="55fbb-138">O **Monitor de confiabilidade** calcula um índice de estabilidade do sistema que reflete se problemas inesperados reduziram a confiabilidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="55fbb-138">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system.</span></span> <span data-ttu-id="55fbb-139">Um gráfico do índice de estabilidade ao longo do tempo identifica rapidamente datas quando os problemas começaram a ocorrer.</span><span class="sxs-lookup"><span data-stu-id="55fbb-139">A graph of the Stability Index over time quickly identifies dates when issues began to occur.</span></span> <span data-ttu-id="55fbb-140">O relatório de estabilidade do sistema fornecido fornece detalhes para ajudar a solucionar problemas de causa da confiabilidade reduzida.</span><span class="sxs-lookup"><span data-stu-id="55fbb-140">The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability.</span></span> <span data-ttu-id="55fbb-141">Exibindo alterações no sistema (instalação ou remoção de aplicativos, atualizações no sistema operacional ou adição ou modificação de drivers) lado a lado com falhas (falhas de aplicativo, panes no sistema operacional ou falhas de hardware), uma estratégia para lidar com os problemas pode ser desenvolvida rapidamente.</span><span class="sxs-lookup"><span data-stu-id="55fbb-141">By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="55fbb-142">A adição de contadores a arquivos de log e agendamento de início, parada e duração podem ser realizadas por meio de uma **interface de assistente**.</span><span class="sxs-lookup"><span data-stu-id="55fbb-142">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**.</span></span> <span data-ttu-id="55fbb-143">Além disso, salvar essa configuração como um modelo permite que os administradores do sistema coletem o mesmo log em outros computadores sem repetir os processos de seleção e agendamento de coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="55fbb-143">In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes.</span></span> <span data-ttu-id="55fbb-144">Os recursos de logs e alertas de desempenho foram incorporados ao monitor de confiabilidade e desempenho do Windows para uso com qualquer conjunto de coletores de dados.</span><span class="sxs-lookup"><span data-stu-id="55fbb-144">Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

