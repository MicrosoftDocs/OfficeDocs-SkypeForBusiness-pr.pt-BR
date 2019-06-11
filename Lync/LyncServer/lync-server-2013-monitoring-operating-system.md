---
title: 'Lync Server 2013: Monitorando o sistema operacional'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f8124afcf2d1acbde3518ff625d528d6e34a3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="edc9a-102">Monitorando o sistema operacional no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edc9a-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edc9a-103">_**Tópico da última modificação:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="edc9a-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="edc9a-104">Você deve monitorar o desempenho de todos os servidores e componentes no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="edc9a-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="edc9a-105">Obviamente, um dos componentes mais importantes é o próprio sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="edc9a-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="edc9a-106">O Lync Server 2013 oferece suporte às edições x64 do:</span><span class="sxs-lookup"><span data-stu-id="edc9a-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="edc9a-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="edc9a-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="edc9a-108">Windows Server 2012 e Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="edc9a-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="edc9a-109">A maneira mais transparente de monitorar um sistema operacional é usando o pacote de gerenciamento do sistema operacional do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="edc9a-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="edc9a-110">Ele fornece os princípios básicos de monitoramento, como desempenho, integridade e disponibilidade para computadores que executam o Windows Server 2012, o Windows Server 2012 R2 e o Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="edc9a-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="edc9a-111">Detectando, alertando e respondendo automaticamente a eventos importantes e indicadores de desempenho, esses pacotes de gerenciamento reduzem o tempo de resolução de problemas e aumentam a disponibilidade e o desempenho geral dos sistemas que executam o Windows Server sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="edc9a-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="edc9a-112">Além dos pacotes de gerenciamento do Windows Server relevantes para o System Center Operations Manager, as seguintes ferramentas e recursos do sistema podem ser usados para monitorar a integridade do sistema operacional (dependendo da versão do sistema operacional).</span><span class="sxs-lookup"><span data-stu-id="edc9a-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="edc9a-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="edc9a-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="edc9a-114">O Windows Server 2008 R2 inclui as seguintes funcionalidades e ferramentas adicionais para ajudar os administradores com monitoramento e gerenciamento básico do sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="edc9a-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="edc9a-p103">O **Monitor de Recursos do Windows** é uma ferramenta avançada para compreender como os recursos do sistema são usados por processos e serviços. Além de monitorar o uso do recurso em tempo real, um Monitor de Recursos pode ajudar a analisar processos sem resposta, identificar quais aplicativos estão usando arquivos e controlar processos e serviços.</span><span class="sxs-lookup"><span data-stu-id="edc9a-p103">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services. In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="edc9a-p104">O **Componente de Análise de Confiabilidade** é um agente nativo que fornece informações detalhadas de experiência sobre uso e confiabilidade do sistema. Essas informações são expostas por meio de uma interface WMI para serem disponibilizadas para consumo por Sistemas de Leitores Portáteis. A exposição do Componente de Análise de Confiabilidade através de uma interface WMI permite que os desenvolvedores monitorem e analisem aplicativos, aumentando a confiabilidade e o desempenho.</span><span class="sxs-lookup"><span data-stu-id="edc9a-p104">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability. This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems. By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="edc9a-120">O **Windows Server 2008 R2** usa o componente de análise de confiabilidade interno para calcular um índice de confiabilidade, que fornece informações sobre o uso geral do sistema e a estabilidade ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="edc9a-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="edc9a-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span><span class="sxs-lookup"><span data-stu-id="edc9a-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="edc9a-122">Monitor de confiabilidade e desempenho do Windows Server 2008 do Windows</span><span class="sxs-lookup"><span data-stu-id="edc9a-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="edc9a-p106">O Monitor de Confiabilidade e Desempenho do Windows é um Snap-in do MMC que combina a funcionalidade das ferramentas autônomas anteriores, incluindo Logs e Alertas de Desempenho, Supervisor de Desempenho de Servidor e Monitor do Sistema. Ele fornece uma interface gráfica para personalizar a coleta de dados de desempenho e as Sessões de Rastreamento de Eventos.</span><span class="sxs-lookup"><span data-stu-id="edc9a-p106">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor. It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="edc9a-125">Ele também inclui o Monitor de Confiabilidade, um Snap-in do MMC que acompanha as alterações no sistema, comparando-as com as alterações na estabilidade do sistema, e fornece uma exibição gráfica de sua relação.</span><span class="sxs-lookup"><span data-stu-id="edc9a-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="edc9a-126">Monitor de Confiabilidade e Desempenho do Windows</span><span class="sxs-lookup"><span data-stu-id="edc9a-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="edc9a-127">Embora o monitor de confiabilidade e desempenho do Windows Combine funcionalidades de algumas ferramentas autônomas antigas, como logs e alertas de desempenho, e o monitor do sistema e o supervisor de desempenho do servidor, ele também fornece uma nova funcionalidade ao Windows Server 2008 e Windows Server 2008 R2, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="edc9a-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="edc9a-128">Conjuntos de Coletores de Dados</span><span class="sxs-lookup"><span data-stu-id="edc9a-128">Data Collector Sets</span></span>

  - <span data-ttu-id="edc9a-129">Modo de Exibição de Recursos</span><span class="sxs-lookup"><span data-stu-id="edc9a-129">Resource View</span></span>

  - <span data-ttu-id="edc9a-130">Monitor de Confiabilidade</span><span class="sxs-lookup"><span data-stu-id="edc9a-130">Reliability Monitor</span></span>

  - <span data-ttu-id="edc9a-131">Assistentes e modelos para a criação de logs</span><span class="sxs-lookup"><span data-stu-id="edc9a-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="edc9a-p107">O **Conjunto de Coletores de Dados** agrupa os coletores de dados em elementos reutilizáveis para serem usados com cenários de monitoramento de desempenho diferentes. Depois que um grupo de coletores de dados é armazenado como um Conjunto de Coletores de Dados, as operações, como agendamento, podem ser aplicadas a todo o conjunto através de uma única mudança de propriedade. O Monitor de Confiabilidade e Desempenho do Windows inclui modelos padrão de Conjuntos de Coletores de Dados para ajudar os administradores de sistema a iniciar imediatamente a coleta de dados de desempenho específicos de uma função de servidor ou de um cenário de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="edc9a-p107">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios. After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="edc9a-p108">A home page do Monitor de Confiabilidade e Desempenho do Windows é a nova tela **Modo de Exibição de Recursos**, que apresenta uma visão geral gráfica em tempo real do uso da CPU, do disco, da rede e da memória. Ao expandir cada um desses elementos monitorados, os administradores de sistema conseguem identificar quais processos estão usando quais recursos. Nas versões anteriores do Windows, esses dados em tempo real, específicos de processo, estavam disponíveis apenas de forma limitada no Gerenciador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="edc9a-p108">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage. By expanding each of these monitored elements, system administrators can identify which processes are using which resources. In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="edc9a-p109">O **Monitor de Confiabilidade** calcula um Índice de Estabilidade do Sistema que reflete se problemas inesperados reduziram a confiabilidade do sistema. Um gráfico ao longo do tempo do Índice de Estabilidade identifica rapidamente as datas em que os problemas começaram a ocorrer. O Relatório de Estabilidade do Sistema de acompanhamento fornece detalhes para ajudar a solucionar problemas da causa da confiabilidade reduzida. A exibição lado a lado das alterações no sistema (instalação ou remoção de aplicativos, atualizações no sistema operacional ou adição ou modificação de drivers) junto com as falhas (falhas de aplicativos, panes do sistema operacional ou falhas de hardware) permite o rápido desenvolvimento de uma estratégia para tratar os problemas.</span><span class="sxs-lookup"><span data-stu-id="edc9a-p109">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system. A graph of the Stability Index over time quickly identifies dates when issues began to occur. The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability. By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="edc9a-p110">A adição de contadores a arquivos de log e o agendamento de seu início, de sua interrupção ou de sua duração agora podem ser realizados através de uma **interface de Assistente**. Além disso, salvar essa configuração como modelo permite que os administradores de sistema coletem o mesmo log em outros computadores sem repetir os processos de seleção e agencamento do coletor de dados. Os recursos de Logs e Alertas de Desempenho foram incorporados ao Monitor de Confiabilidade e Desempenho do Windows para serem usados com qualquer Conjunto de Coletores de Dados.</span><span class="sxs-lookup"><span data-stu-id="edc9a-p110">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**. In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes. Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

