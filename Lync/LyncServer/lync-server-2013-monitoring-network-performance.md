---
title: 'Lync Server 2013: Monitorando o desempenho da rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="c70ca-102">Monitorando o desempenho da rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c70ca-102">Monitoring network performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c70ca-103">_**Tópico da última modificação:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="c70ca-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="c70ca-104">O Lync Server 2013 é uma tecnologia de comunicação em tempo real que depende muito da rede para permitir a comunicação entre usuários, seja por meio de mensagens instantâneas (IM), chamadas de voz ou comunicação com vídeo.</span><span class="sxs-lookup"><span data-stu-id="c70ca-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="c70ca-105">Portanto, é importante monitorar o desempenho da rede continuamente para ajudar a garantir que a modalidade de comunicação escolhida pelo usuário ofereça a melhor experiência possível.</span><span class="sxs-lookup"><span data-stu-id="c70ca-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="c70ca-106">O desempenho da rede pode ser medido em dois níveis:</span><span class="sxs-lookup"><span data-stu-id="c70ca-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="c70ca-107">**Desempenho geral da rede**   esse nível de medição de desempenho permitirá que uma organização crie uma exibição "grande" da rede e, em geral, é implementada por sistemas de monitoramento de rede de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c70ca-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="c70ca-108">Esses sistemas receberão dados de desempenho e capacidade de dispositivos de rede remoto, como roteadores e comutados em toda a rede, para permitir que os administradores determinem a integridade de qualquer componente de rede fornecido a qualquer hora do dia.</span><span class="sxs-lookup"><span data-stu-id="c70ca-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="c70ca-109">**Desempenho individual do servidor**   esse nível de medição de desempenho é limitado a um servidor específico e ajuda os administradores com o gauging o desempenho de rede de um servidor específico para ajudar a solucionar um desempenho específico problema ou para medir o desempenho do respectivo servidor em um determinado período como parte de um processo de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="c70ca-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="c70ca-110">Você pode monitorar a rede usando as ferramentas descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c70ca-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="c70ca-111">Ferramentas para monitoramento geral do desempenho de rede</span><span class="sxs-lookup"><span data-stu-id="c70ca-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="c70ca-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="c70ca-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="c70ca-113">O System Center Operations Manager fornece gerenciamento de serviços de ponta a ponta que é fácil de personalizar e estender para níveis de serviço aprimorados em um ambiente de ti.</span><span class="sxs-lookup"><span data-stu-id="c70ca-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="c70ca-114">Isso permite às operações e às equipes de gerenciamento de ti identificar e resolver problemas que afetem a integridade dos serviços de ti distribuídos.</span><span class="sxs-lookup"><span data-stu-id="c70ca-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="c70ca-115">O gerenciamento de serviços completo não está restrito a ambientes baseados na Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c70ca-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="c70ca-116">Suporte para serviços Web para gerenciamento (WS-Management), protocolo de gerenciamento de rede simples (SNMP) e soluções de parceiros permitem que sistemas que não executam sistemas operacionais e hardware da Microsoft sejam incluídos no monitoramento de serviços no System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="c70ca-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="c70ca-117">System Center Operations Manager 2012 e soluções de gerenciamento de rede de terceiros</span><span class="sxs-lookup"><span data-stu-id="c70ca-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="c70ca-118">**EMC Smarts**   EMC Solutions for Operations Manager ajudam a resolver rapidamente problemas que afetem os níveis de serviço.</span><span class="sxs-lookup"><span data-stu-id="c70ca-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="c70ca-119">Ao usar o EMC Solutions for Operations Manager, você pode gerenciar e monitorar toda a sua cadeia de serviços de ti com uma solução integrada e automatizada.</span><span class="sxs-lookup"><span data-stu-id="c70ca-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="c70ca-120">Você identificará facilmente as causas de desempenho e a disponibilidade dos problemas de desempenho e os resolverá mais rapidamente, o que reduz os efeitos e os custos.</span><span class="sxs-lookup"><span data-stu-id="c70ca-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="c70ca-121">Os principais benefícios incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c70ca-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="c70ca-122">O gerenciamento avançado e fácil de usar se concentra em oferecer um valor estratégico para os negócios, em vez de classificar e filtrar alertas confusos manualmente.</span><span class="sxs-lookup"><span data-stu-id="c70ca-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="c70ca-123">**Solução mais rápida**   solucione problemas e atenda às necessidades dos negócios com mais rapidez, reduzindo o efeito e o custo.</span><span class="sxs-lookup"><span data-stu-id="c70ca-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="c70ca-124">**Operações simplificadas**   evitam a complexidade da ti ao combinar várias ferramentas de gerenciamento, aplicativos e terminais.</span><span class="sxs-lookup"><span data-stu-id="c70ca-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="c70ca-125">Mais informações podem ser encontradas aqui:</span><span class="sxs-lookup"><span data-stu-id="c70ca-125">More information can be found here:</span></span>

[<span data-ttu-id="c70ca-126">Gerenciador de operações do Microsoft System Center</span><span class="sxs-lookup"><span data-stu-id="c70ca-126">Microsoft System Center Operations Manager</span></span>](http://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="c70ca-127">Soluções para o Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="c70ca-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="c70ca-128">Soluções de terceiros</span><span class="sxs-lookup"><span data-stu-id="c70ca-128">Third-Party Solutions</span></span>

<span data-ttu-id="c70ca-129">**Centro de gerenciamento de redes HP (anteriormente conhecido como HP OpenView)** O    [centro de gerenciamento de redes HP](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) oferece gerenciamento integrado de falhas e desempenho para melhorar a disponibilidade e o desempenho da rede.</span><span class="sxs-lookup"><span data-stu-id="c70ca-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="c70ca-130">O centro de gerenciamento de rede é parte da solução de gerenciamento automatizado de rede da HP que unifica o gerenciamento de falhas, desempenho, configuração e alterações.</span><span class="sxs-lookup"><span data-stu-id="c70ca-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="c70ca-131">**Gerenciamento de rede e produtos**   de automação da Cisco para empresas, a Cisco tem vários produtos de gerenciamento disponíveis, incluindo a solução de gerenciamento de LAN da CiscoWorks e o módulo de análise de rede da Cisco, para ajudar a melhorar a eficiência operacional e reduzir o tempo de inatividade da rede.</span><span class="sxs-lookup"><span data-stu-id="c70ca-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="c70ca-132">Para obter dados adicionais sobre esses produtos, consulte o website da Cisco [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)em.</span><span class="sxs-lookup"><span data-stu-id="c70ca-132">For additional data on these products, refer to the Cisco website at [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="c70ca-133">O protocolo de gerenciamento de rede simples (SNMP) é um padrão de gerenciamento de rede (SNMP) que define uma estratégia para gerenciar redes TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="c70ca-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="c70ca-134">O SNMP permite que você capture informações de configuração e status sobre a rede e envie as informações para um computador designado para monitoramento de eventos.</span><span class="sxs-lookup"><span data-stu-id="c70ca-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="c70ca-135">Esse protocolo baseado em padrões de gerenciamento de rede usa uma arquitetura distribuída que inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c70ca-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="c70ca-136">Vários nós gerenciados, cada um com uma entidade SNMP chamada de agente, que fornece acesso remoto à instrumentação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="c70ca-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="c70ca-137">Pelo menos uma entidade SNMP conhecida como gerente que executa aplicativos de gerenciamento para monitorar e controlar elementos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="c70ca-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="c70ca-138">Elementos gerenciados são dispositivos como hosts, roteadores e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c70ca-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="c70ca-139">Elas são monitoradas e controladas acessando suas informações de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="c70ca-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="c70ca-140">Um protocolo de gerenciamento, SNMP, é usado para comunicar informações de gerenciamento entre as estações de gerenciamento e agentes.</span><span class="sxs-lookup"><span data-stu-id="c70ca-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="c70ca-141">Informações de gerenciamento referem-se a uma coleção de objetos gerenciados que residem em um repositório de informações virtual chamado de uma base de informações de gerenciamento (MIB).</span><span class="sxs-lookup"><span data-stu-id="c70ca-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c70ca-142">Exemplos de soluções de monitoramento de rede de terceiros são fornecidos acima.</span><span class="sxs-lookup"><span data-stu-id="c70ca-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="c70ca-143">Esta lista não é definitiva, e a Microsoft não favorece nenhuma solução específica de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="c70ca-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="c70ca-144">Consulte um provedor de serviços de rede e ou seu respectivo provedor de tecnologia para determinar a melhor solução de monitoramento de rede para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="c70ca-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="c70ca-145">Ferramentas para monitorar o desempenho de uma rede de servidor individual</span><span class="sxs-lookup"><span data-stu-id="c70ca-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="c70ca-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="c70ca-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="c70ca-147">O System Center Operations Manager 2012 permite que os administradores visualizem o desempenho de rede de servidores individuais por meio do pacote de gerenciamento do Windows Server 2012: o pacote de gerenciamento do sistema operacional Windows Server inclui um pacote de gerenciamento de "desempenho" Isso permite que os administradores monitorem o desempenho do adaptador de rede e a integridade do adaptador.</span><span class="sxs-lookup"><span data-stu-id="c70ca-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="c70ca-148">Monitor de rede do Windows</span><span class="sxs-lookup"><span data-stu-id="c70ca-148">Windows Network Monitor</span></span>

<span data-ttu-id="c70ca-149">Coleta, exibe, analisa o uso de recursos em um servidor e mede o tráfego de rede.</span><span class="sxs-lookup"><span data-stu-id="c70ca-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="c70ca-150">O monitor de rede monitora exclusivamente as atividades da rede.</span><span class="sxs-lookup"><span data-stu-id="c70ca-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="c70ca-151">Ao capturar e analisar dados de rede e usar esses dados com logs de desempenho, você pode determinar o uso da rede, identificar problemas de rede e prever as necessidades futuras de rede.</span><span class="sxs-lookup"><span data-stu-id="c70ca-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="c70ca-152">Para obter mais informações sobre o monitor de rede 3,4 e sobre como instalar e configurar o monitor de rede e capturar e analisar dados, Confira esta sessão: monitor de rede 3,3 visão geral.</span><span class="sxs-lookup"><span data-stu-id="c70ca-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="c70ca-153">Além disso, examine o [blog do monitor de rede](http://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="c70ca-153">Also, review the [Network Monitor blog](http://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

