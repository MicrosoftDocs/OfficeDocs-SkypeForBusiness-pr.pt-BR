---
title: 'Lync Server 2013: cartaz: principais indicadores de integridade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aca31ca681c75438bbcbb67b1d2dc5c0b6305cb7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="fa0bb-102">Principais indicadores de integridade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa0bb-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa0bb-103">_**Última modificação do tópico:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="fa0bb-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="fa0bb-104">Este artigo é um complemento aos [principais indicadores de integridade: a Fundação para manter](https://go.microsoft.com/fwlink/?linkid=391838) o pôster saudável dos servidores do Lync, que você pode baixar do centro de download.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="fa0bb-105">![Cartaz descrevendo a solução de problemas usando dados do KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Cartaz descrevendo a solução de problemas usando dados do KHI")</span><span class="sxs-lookup"><span data-stu-id="fa0bb-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="fa0bb-106">Você pode usar este cartaz para saber mais sobre os principais indicadores de integridade (KHIs), contadores de desempenho com limiares destinados à revelação de problemas de experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="fa0bb-107">Coletar dados de KHI é geralmente a primeira etapa para implementar a metodologia de qualidade de chamada (CQM), que se concentra em garantir uma experiência de áudio de qualidade para usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="fa0bb-108">Se você tiver dúvidas sobre como usar o CQM, você pode enviar suas perguntas para o cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="fa0bb-109">O cartaz explica as seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="fa0bb-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="fa0bb-110">Quais são os principais indicadores de integridade?</span><span class="sxs-lookup"><span data-stu-id="fa0bb-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="fa0bb-111">Para coletar dados do KHI</span><span class="sxs-lookup"><span data-stu-id="fa0bb-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="fa0bb-112">Fluxo de correção para todas as funções de servidor</span><span class="sxs-lookup"><span data-stu-id="fa0bb-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="fa0bb-113">Glossário</span><span class="sxs-lookup"><span data-stu-id="fa0bb-113">Glossary</span></span>

  - <span data-ttu-id="fa0bb-114">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="fa0bb-114">Front-end Servers</span></span>

  - <span data-ttu-id="fa0bb-115">Servidores SQL de back-end</span><span class="sxs-lookup"><span data-stu-id="fa0bb-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="fa0bb-116">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="fa0bb-116">Mediation Servers</span></span>

  - <span data-ttu-id="fa0bb-117">Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="fa0bb-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="fa0bb-118">Quais são os principais indicadores de integridade?</span><span class="sxs-lookup"><span data-stu-id="fa0bb-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="fa0bb-119">Os principais indicadores de integridade são contadores de desempenho com limiares destinados à revelação de problemas de experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="fa0bb-120">Coletar dados de KHI é geralmente a primeira etapa para implementar a metodologia de qualidade de chamada (CQM), que se concentra em garantir uma experiência de áudio de qualidade para usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="fa0bb-121">Os KHIs são usados além das soluções de monitoramento padrão do Lync (por exemplo, o System Center Operations Manager, as transações sintéticas, o monitoramento do servidor) e não em vez dessas soluções.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="fa0bb-122">Colete os contadores de desempenho do KHI e preencha a planilha KHI que acompanha o guia de rede para produzir um scorecard que o ajudará a determinar a integridade do servidor de uma implantação do Lync.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="fa0bb-123">Depois de preenchida, ele orienta você a reparar o ambiente e dá mais percepção a outros participantes.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="fa0bb-124">Avaliar o KHIs mensalmente e incorporá-los em todos os processos operacionais em andamento da implantação.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="fa0bb-125">Baixe o [Guia de rede do Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) para ver a lista completa de KHIs e para obter as planilhas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-125">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="fa0bb-126">Para coletar dados do KHI</span><span class="sxs-lookup"><span data-stu-id="fa0bb-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="fa0bb-127">Execute o script KHI incluído no guia de rede do Lync Server em cada Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="fa0bb-128">Isso criará um coletor de dados dentro do monitor de desempenho e o nomeará KHI.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="fa0bb-129">Por padrão, os dados serão pesquisados a cada 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="fa0bb-130">Antes do início do dia útil da sua empresa, vá para cada servidor do Lync e inicie o coletor de dados KHI.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="fa0bb-131">No final desse dia, interrompa o coletor de dados do KHI e copie os dados para um local central.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="fa0bb-132">Após usar o monitor de desempenho para preencher a planilha do KHI incluída no download do guia de rede do Lync Server, compare os resultados com os alvos recomendados.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="fa0bb-133">Fluxo de correção para todas as funções de servidor</span><span class="sxs-lookup"><span data-stu-id="fa0bb-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="fa0bb-134">Para cada servidor em sua implementação do Lync, comece verificando se a integridade do componente do servidor e o desempenho do sistema estão no nível desejado ou acima dele.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="fa0bb-135">Somente depois isso deve observar os indicadores relacionados à função do servidor na implementação geral do Lync.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="fa0bb-136">Comece coletando dados de desempenho do KHI para todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="fa0bb-137">Para cada uma das funções de sistema (detalhes abordados posteriormente neste documento), determine se os componentes básicos do sistema atendem aos alvos recomendados.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="fa0bb-138">Caso contrário, corrija o desempenho do sistema e, em seguida, colete novamente os dados do KHI e garanta a integridade do sistema antes de examinar as métricas específicas da função do servidor na implementação do Lync.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="fa0bb-139">A integridade do componente para todas as funções é definida como:</span><span class="sxs-lookup"><span data-stu-id="fa0bb-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="fa0bb-140">Utilização \< da CPU 80%</span><span class="sxs-lookup"><span data-stu-id="fa0bb-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="fa0bb-141">Média de gravação \< de disco 10 ms</span><span class="sxs-lookup"><span data-stu-id="fa0bb-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="fa0bb-142">Média de leitura \< de disco 10 ms</span><span class="sxs-lookup"><span data-stu-id="fa0bb-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="fa0bb-143">Memória \>disponível de 20% no total de sistema</span><span class="sxs-lookup"><span data-stu-id="fa0bb-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="fa0bb-144">Comprimento \< da fila de rede 2</span><span class="sxs-lookup"><span data-stu-id="fa0bb-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="fa0bb-145">Pacotes descartados (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="fa0bb-146">Glossário</span><span class="sxs-lookup"><span data-stu-id="fa0bb-146">Glossary</span></span>

<span data-ttu-id="fa0bb-147">Os seguintes termos e acrônimos são usados neste cartaz:</span><span class="sxs-lookup"><span data-stu-id="fa0bb-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="fa0bb-148">Como MCU = unidade de controle de vários pontos do compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fa0bb-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="fa0bb-149">AV MCU = áudio/vídeo MCU</span><span class="sxs-lookup"><span data-stu-id="fa0bb-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="fa0bb-150">IM MCU = mensagens instantâneas MCU</span><span class="sxs-lookup"><span data-stu-id="fa0bb-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="fa0bb-151">UCWA = API Web de comunicações unificadas</span><span class="sxs-lookup"><span data-stu-id="fa0bb-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="fa0bb-152">Borda AV = passagem de áudio/vídeo por borda</span><span class="sxs-lookup"><span data-stu-id="fa0bb-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="fa0bb-153">Autenticação AV = autenticação de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="fa0bb-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="fa0bb-154">Pilha SIP = contém a implementação principal SIP do Lync</span><span class="sxs-lookup"><span data-stu-id="fa0bb-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="fa0bb-155">Proxy de dados = usado para conferência de borda</span><span class="sxs-lookup"><span data-stu-id="fa0bb-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="fa0bb-156">LySS = serviço de armazenamento do Lync</span><span class="sxs-lookup"><span data-stu-id="fa0bb-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="fa0bb-157">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="fa0bb-157">Front-end Servers</span></span>

<span data-ttu-id="fa0bb-158">Os seguintes destinos KHI recomendados são específicos para servidores front-end, além da integridade básica do componente:</span><span class="sxs-lookup"><span data-stu-id="fa0bb-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa0bb-159">Área funcional</span><span class="sxs-lookup"><span data-stu-id="fa0bb-159">Functional area</span></span></th>
<th><span data-ttu-id="fa0bb-160">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="fa0bb-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa0bb-161">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="fa0bb-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-162">Estado &lt;2 da integridade MCU</span><span class="sxs-lookup"><span data-stu-id="fa0bb-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0bb-163">Componentes Web</span><span class="sxs-lookup"><span data-stu-id="fa0bb-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-164">Tempos limite &lt;do AD de expansão de lista de distribuição 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="fa0bb-165">Falhas de ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="fa0bb-166">Falhas de LIS = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="fa0bb-167">Erros &lt; de autenticação 1/seg</span><span class="sxs-lookup"><span data-stu-id="fa0bb-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="fa0bb-168">Solicitações ASP.NET v4 rejeitadas = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0bb-169">Pilha SIP</span><span class="sxs-lookup"><span data-stu-id="fa0bb-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-170">Média de processamento &lt; de mensagens de entrada 1 seg</span><span class="sxs-lookup"><span data-stu-id="fa0bb-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="fa0bb-171">Respostas de entrada &lt; ignoradas 1/seg solicitações &lt; de entrada descartadas 1/s</span><span class="sxs-lookup"><span data-stu-id="fa0bb-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="fa0bb-172">Latência &lt; da fila 100 ms</span><span class="sxs-lookup"><span data-stu-id="fa0bb-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="fa0bb-173">Latência &lt; SPROC 100 ms</span><span class="sxs-lookup"><span data-stu-id="fa0bb-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="fa0bb-174">Solicitações limitadas = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="fa0bb-175">Erros &lt; de autenticação 1/seg</span><span class="sxs-lookup"><span data-stu-id="fa0bb-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="fa0bb-176">Mensagens de entrada tempo limite &lt; de 2</span><span class="sxs-lookup"><span data-stu-id="fa0bb-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="fa0bb-177">Média de mensagens de entrada &lt; suspensas 1 seg</span><span class="sxs-lookup"><span data-stu-id="fa0bb-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="fa0bb-178">Conexões &lt; controladas por fluxo 2</span><span class="sxs-lookup"><span data-stu-id="fa0bb-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="fa0bb-179">Atraso &lt; médio da fila de saída 2 seg</span><span class="sxs-lookup"><span data-stu-id="fa0bb-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0bb-180">LySS</span><span class="sxs-lookup"><span data-stu-id="fa0bb-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-181">% de espaço usado pelo serviço de armazenamento &lt; DB 80</span><span class="sxs-lookup"><span data-stu-id="fa0bb-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="fa0bb-182">#falhas de replicação de réplica = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="fa0bb-183">#eventos de perda de dados = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0bb-184">SQL</span><span class="sxs-lookup"><span data-stu-id="fa0bb-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-185">Expectativa de vida da &gt; página 300 seg.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="fa0bb-186">Solicitações em lote/ &lt; s 2500</span><span class="sxs-lookup"><span data-stu-id="fa0bb-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="fa0bb-187">Servidores SQL de back-end</span><span class="sxs-lookup"><span data-stu-id="fa0bb-187">Backend SQL Servers</span></span>

<span data-ttu-id="fa0bb-188">Os seguintes destinos KHI recomendados são específicos para os SQL Servers, além da integridade básica do componente:</span><span class="sxs-lookup"><span data-stu-id="fa0bb-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa0bb-189">Área funcional</span><span class="sxs-lookup"><span data-stu-id="fa0bb-189">Functional area</span></span></th>
<th><span data-ttu-id="fa0bb-190">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="fa0bb-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa0bb-191">SQL</span><span class="sxs-lookup"><span data-stu-id="fa0bb-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-192">Expectativa de vida da &gt; página 300 seg.</span><span class="sxs-lookup"><span data-stu-id="fa0bb-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="fa0bb-193">Solicitações em lote/ &lt; s 2500</span><span class="sxs-lookup"><span data-stu-id="fa0bb-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="fa0bb-194">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="fa0bb-194">Mediation Servers</span></span>

<span data-ttu-id="fa0bb-195">Os seguintes destinos KHI recomendados são específicos para servidores de mediação além da integridade básica do componente:</span><span class="sxs-lookup"><span data-stu-id="fa0bb-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa0bb-196">Área funcional</span><span class="sxs-lookup"><span data-stu-id="fa0bb-196">Functional area</span></span></th>
<th><span data-ttu-id="fa0bb-197">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="fa0bb-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa0bb-198">Serviço do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="fa0bb-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-199">Índice de falha de chamada de carregamento = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="fa0bb-200">Chamadas com falha devido ao &lt;proxy 10</span><span class="sxs-lookup"><span data-stu-id="fa0bb-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="fa0bb-201">Chamadas com falha devido ao &lt;gateway 10</span><span class="sxs-lookup"><span data-stu-id="fa0bb-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="fa0bb-202">Chamadas (in ou out) rejeitadas = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="fa0bb-203">Candidatos à mídia ausentes = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="fa0bb-204">Falhas de verificação de conectividade de mídia = 0</span><span class="sxs-lookup"><span data-stu-id="fa0bb-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="fa0bb-205">Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="fa0bb-205">Edge Servers</span></span>

<span data-ttu-id="fa0bb-206">Os seguintes destinos KHI recomendados são específicos para servidores de borda além da integridade básica do componente:</span><span class="sxs-lookup"><span data-stu-id="fa0bb-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa0bb-207">Área funcional</span><span class="sxs-lookup"><span data-stu-id="fa0bb-207">Functional area</span></span></th>
<th><span data-ttu-id="fa0bb-208">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="fa0bb-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa0bb-209">Autenticação AV</span><span class="sxs-lookup"><span data-stu-id="fa0bb-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-210">Solicitações &lt; inválidas 20/seg</span><span class="sxs-lookup"><span data-stu-id="fa0bb-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0bb-211">Borda de AV</span><span class="sxs-lookup"><span data-stu-id="fa0bb-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-212">Falhas &lt;de auth. 20/seg</span><span class="sxs-lookup"><span data-stu-id="fa0bb-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="fa0bb-213">Falhas &lt;de alocação 20/seg</span><span class="sxs-lookup"><span data-stu-id="fa0bb-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="fa0bb-214">Pacotes removidos &lt;300/s</span><span class="sxs-lookup"><span data-stu-id="fa0bb-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0bb-215">Proxy de dados</span><span class="sxs-lookup"><span data-stu-id="fa0bb-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-216">Conexões &lt; de servidor limitado 3</span><span class="sxs-lookup"><span data-stu-id="fa0bb-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="fa0bb-217">O sistema está &lt;regulando 1</span><span class="sxs-lookup"><span data-stu-id="fa0bb-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0bb-218">Pilha SIP</span><span class="sxs-lookup"><span data-stu-id="fa0bb-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="fa0bb-219">Conexões com limite ignorado &lt; 1</span><span class="sxs-lookup"><span data-stu-id="fa0bb-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="fa0bb-220">Envio do tempo limite &lt;de 10</span><span class="sxs-lookup"><span data-stu-id="fa0bb-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="fa0bb-221">Conexões &lt;de fluxo controlado 100</span><span class="sxs-lookup"><span data-stu-id="fa0bb-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="fa0bb-222">Solicitações de entrada &lt; descartadas 1/s</span><span class="sxs-lookup"><span data-stu-id="fa0bb-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="fa0bb-223">Média de processamento &lt; de mensagens 3 seg</span><span class="sxs-lookup"><span data-stu-id="fa0bb-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fa0bb-224">Confira também</span><span class="sxs-lookup"><span data-stu-id="fa0bb-224">See Also</span></span>


[<span data-ttu-id="fa0bb-225">Guia de rede do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fa0bb-225">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="fa0bb-226">Principais indicadores de integridade: a base para manter os servidores de Lync saudáveis</span><span class="sxs-lookup"><span data-stu-id="fa0bb-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="fa0bb-227">Metodologia de qualidade de chamada do Lync</span><span class="sxs-lookup"><span data-stu-id="fa0bb-227">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

