---
title: 'Lync Server 2013: monitorando o desempenho da rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc6941f612fdf18f081cb52e55e2c7f7201e64b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="09b75-102">Monitorando o desempenho da rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09b75-102">Monitoring network performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09b75-103">_**Última modificação do tópico:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="09b75-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="09b75-104">O Lync Server 2013 é uma tecnologia de comunicação em tempo real que depende fortemente da rede para habilitar a comunicação entre usuários, através de mensagens instantâneas (IM), chamadas de voz ou comunicação de vídeo.</span><span class="sxs-lookup"><span data-stu-id="09b75-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="09b75-105">Portanto, é importante monitorar o desempenho da rede continuamente para ajudar a garantir que a modalidade de comunicação escolhida pelo usuário ofereça a melhor experiência possível.</span><span class="sxs-lookup"><span data-stu-id="09b75-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="09b75-106">O desempenho da rede pode ser medido em dois níveis:</span><span class="sxs-lookup"><span data-stu-id="09b75-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="09b75-107">**Desempenho geral da rede**   esse nível de medição de desempenho permitirá que uma organização crie uma visão geral de sua rede e, em geral, é implementada por meio de sistemas de monitoramento de rede de terceiros.</span><span class="sxs-lookup"><span data-stu-id="09b75-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="09b75-108">Esses sistemas receberão dados de desempenho e capacidade de dispositivos de rede remotas, como roteadores e comutados por toda a rede para permitir que os administradores determinem a integridade de um determinado componente de rede em qualquer ocasião do dia.</span><span class="sxs-lookup"><span data-stu-id="09b75-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="09b75-109">**Desempenho do servidor individual**   esse nível de medição de desempenho está limitado a um servidor específico e ajudará os administradores no gauging o desempenho de rede de um servidor específico para ajudar na solução de problemas de um problema específico de desempenho ou para medir o desempenho do respectivo servidor em um determinado período como parte de um processo de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="09b75-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="09b75-110">Você pode monitorar a rede usando as ferramentas descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="09b75-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="09b75-111">Ferramentas para monitoramento geral do desempenho da rede</span><span class="sxs-lookup"><span data-stu-id="09b75-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="09b75-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="09b75-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="09b75-113">O System Center Operations Manager oferece gerenciamento de serviço de ponta a ponta que é fácil de personalizar e estender para níveis de serviço aprimorados em um ambiente de ti.</span><span class="sxs-lookup"><span data-stu-id="09b75-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="09b75-114">Isso permite que as operações e as equipes de gerenciamento de ti identifiquem e resolvam os problemas que afetam a integridade dos serviços de ti distribuídos.</span><span class="sxs-lookup"><span data-stu-id="09b75-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="09b75-115">O gerenciamento de serviços de ponta a ponta não é restrito a ambientes baseados em Microsoft.</span><span class="sxs-lookup"><span data-stu-id="09b75-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="09b75-116">Suporte para serviços Web para gerenciamento (WS-Management), SNMP (protocolo de gerenciamento de rede simples) e soluções de parceiros permitem que sistemas que não executam sistemas operacionais e hardware da Microsoft sejam incluídos no monitoramento de serviços no System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="09b75-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="09b75-117">Soluções de gerenciamento de rede do System Center Operations Manager 2012 e de terceiros</span><span class="sxs-lookup"><span data-stu-id="09b75-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="09b75-118">**EMC Smarts**   EMC Solutions for Operations Manager ajuda a resolver rapidamente problemas que afetam os níveis de serviço.</span><span class="sxs-lookup"><span data-stu-id="09b75-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="09b75-119">Usando o EMC Solutions for Operations Manager, você pode gerenciar e monitorar toda a sua cadeia de serviços de ti com uma solução integrada e automatizada.</span><span class="sxs-lookup"><span data-stu-id="09b75-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="09b75-120">Você identificará facilmente as causas raiz dos problemas de desempenho e disponibilidade e os resolverá mais rapidamente, reduzindo os efeitos e os custos.</span><span class="sxs-lookup"><span data-stu-id="09b75-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="09b75-121">Os principais benefícios incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="09b75-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="09b75-122">Foco de gerenciamento avançado e fácil de usar para fornecer o valor estratégico de negócios, em vez de classificar e filtrar manualmente os alertas confusos.</span><span class="sxs-lookup"><span data-stu-id="09b75-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="09b75-123">**Resolução mais rápida**   resolvem problemas de ti e atendem às necessidades de negócios com mais rapidez, reduzindo o efeito e o custo.</span><span class="sxs-lookup"><span data-stu-id="09b75-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="09b75-124">**Operações simplificadas**   evitam complexidade de ti combinando várias ferramentas de gerenciamento, aplicativos e terminais.</span><span class="sxs-lookup"><span data-stu-id="09b75-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="09b75-125">É possível encontrar mais informações aqui:</span><span class="sxs-lookup"><span data-stu-id="09b75-125">More information can be found here:</span></span>

[<span data-ttu-id="09b75-126">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="09b75-126">Microsoft System Center Operations Manager</span></span>](https://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="09b75-127">Soluções para o Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="09b75-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="09b75-128">Soluções de terceiros</span><span class="sxs-lookup"><span data-stu-id="09b75-128">Third-Party Solutions</span></span>

<span data-ttu-id="09b75-129">**Centro de gerenciamento de rede HP (anteriormente conhecido como HP OpenView) o centro de**   [Gerenciamento de rede HP](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) oferece gerenciamento de falhas e desempenho integrados para melhorar a disponibilidade e o desempenho da rede.</span><span class="sxs-lookup"><span data-stu-id="09b75-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="09b75-130">O centro de gerenciamento de rede é parte da solução de gerenciamento automatizado de rede HP que unifica o gerenciamento de falhas, desempenho, configuração e alteração.</span><span class="sxs-lookup"><span data-stu-id="09b75-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="09b75-131">**Os produtos**   de gerenciamento e automação de rede da Cisco para a empresa, a Cisco tem vários produtos de gerenciamento disponíveis, incluindo a solução de gerenciamento de LAN da CiscoWorks e o módulo de análise de rede da Cisco, para ajudar a melhorar a eficiência operacional e reduzir o tempo</span><span class="sxs-lookup"><span data-stu-id="09b75-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="09b75-132">Para obter dados adicionais sobre esses produtos, consulte o site da Cisco [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html)em.</span><span class="sxs-lookup"><span data-stu-id="09b75-132">For additional data on these products, refer to the Cisco website at [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="09b75-133">SNMP (protocolo de gerenciamento de rede simples) SNMP é um padrão de gerenciamento de rede que define uma estratégia para gerenciar redes TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="09b75-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="09b75-134">O SNMP permite capturar informações de configuração e status sobre a rede e enviar as informações para um computador designado para monitoramento de eventos.</span><span class="sxs-lookup"><span data-stu-id="09b75-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="09b75-135">Este protocolo de gerenciamento de rede baseado em padrões usa uma arquitetura distribuída que inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="09b75-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="09b75-136">Vários nós gerenciados, cada um com uma entidade SNMP chamada de um agente que fornece acesso remoto à instrumentação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="09b75-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="09b75-137">Pelo menos uma entidade SNMP conhecida como gerente que executa aplicativos de gerenciamento para monitorar e controlar os elementos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="09b75-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="09b75-138">Elementos gerenciados são dispositivos como hosts, roteadores e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="09b75-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="09b75-139">Eles são monitorados e controlados acessando suas informações de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="09b75-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="09b75-140">Um protocolo de gerenciamento, SNMP, é usado para comunicar informações de gerenciamento entre as estações de gerenciamento e os agentes.</span><span class="sxs-lookup"><span data-stu-id="09b75-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="09b75-141">As informações de gerenciamento referem-se a uma coleção de objetos gerenciados que residem em um repositório de informações virtual, chamado de MIB (Management Information base).</span><span class="sxs-lookup"><span data-stu-id="09b75-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09b75-142">Os exemplos de soluções de monitoramento de rede de terceiros são fornecidos acima.</span><span class="sxs-lookup"><span data-stu-id="09b75-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="09b75-143">Essa lista não é definitiva, e a Microsoft não favorece nenhuma solução de fornecedor específico.</span><span class="sxs-lookup"><span data-stu-id="09b75-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="09b75-144">Consulte um provedor de serviços de rede e seu respectivo provedor de tecnologia para determinar a melhor solução de monitoramento de rede para sua organização.</span><span class="sxs-lookup"><span data-stu-id="09b75-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="09b75-145">Ferramentas para monitorar o desempenho da rede de servidor individual</span><span class="sxs-lookup"><span data-stu-id="09b75-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="09b75-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="09b75-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="09b75-147">O System Center Operations Manager 2012 permite que os administradores exibam o desempenho de rede de servidores individuais por meio do pacote de gerenciamento do Windows Server 2012: o pacote de gerenciamento do sistema operacional Windows Server inclui um pacote de gerenciamento de "desempenho" Isso permite que os administradores monitorem o desempenho do adaptador de rede e a integridade do adaptador.</span><span class="sxs-lookup"><span data-stu-id="09b75-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="09b75-148">Monitor de rede do Windows</span><span class="sxs-lookup"><span data-stu-id="09b75-148">Windows Network Monitor</span></span>

<span data-ttu-id="09b75-149">Coleta, exibe, analisa o uso do recurso em um servidor e mede o tráfego de rede.</span><span class="sxs-lookup"><span data-stu-id="09b75-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="09b75-150">O monitor de rede monitora exclusivamente a atividade da rede.</span><span class="sxs-lookup"><span data-stu-id="09b75-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="09b75-151">Ao capturar e analisar dados de rede e usar esses dados com logs de desempenho, você pode determinar o uso da rede, identificar problemas de rede e prever as necessidades futuras da rede.</span><span class="sxs-lookup"><span data-stu-id="09b75-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="09b75-152">Para obter mais informações sobre o monitor de rede 3,4 e sobre como instalar e configurar o monitor de rede e capturar e analisar dados, revise esta sessão: monitor de rede 3,3 visão geral.</span><span class="sxs-lookup"><span data-stu-id="09b75-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="09b75-153">Além disso, revise o [blog do monitor de rede](https://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="09b75-153">Also, review the [Network Monitor blog](https://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

