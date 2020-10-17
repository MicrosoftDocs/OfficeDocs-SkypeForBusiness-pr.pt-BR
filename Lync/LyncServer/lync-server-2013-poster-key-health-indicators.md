---
title: 'Lync Server 2013: cartaz: principais indicadores de integridade'
description: 'Lync Server 2013: cartaz: principais indicadores de integridade.'
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
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566337"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="0203e-103">Principais indicadores de integridade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0203e-103">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0203e-104">_**Última modificação do tópico:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="0203e-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="0203e-105">Este artigo é um complemento aos [principais indicadores de integridade: a Fundação para manter](https://go.microsoft.com/fwlink/?linkid=391838) o pôster saudável dos servidores do Lync, que você pode baixar do centro de download.</span><span class="sxs-lookup"><span data-stu-id="0203e-105">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="0203e-106">![Cartaz descrevendo a solução de problemas usando dados do KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Cartaz descrevendo a solução de problemas usando dados do KHI")</span><span class="sxs-lookup"><span data-stu-id="0203e-106">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="0203e-107">Você pode usar este cartaz para saber mais sobre os principais indicadores de integridade (KHIs), contadores de desempenho com limiares destinados à revelação de problemas de experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="0203e-107">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="0203e-108">Coletar dados de KHI é geralmente a primeira etapa para implementar a metodologia de qualidade de chamada (CQM), que se concentra em garantir uma experiência de áudio de qualidade para usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="0203e-108">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="0203e-109">Se você tiver dúvidas sobre como usar o CQM, você pode enviar suas perguntas para o cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0203e-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="0203e-110">O cartaz explica as seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="0203e-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="0203e-111">Quais são os principais indicadores de integridade?</span><span class="sxs-lookup"><span data-stu-id="0203e-111">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="0203e-112">Para coletar dados do KHI</span><span class="sxs-lookup"><span data-stu-id="0203e-112">To Collect KHI Data</span></span>

  - <span data-ttu-id="0203e-113">Fluxo de correção para todas as funções de servidor</span><span class="sxs-lookup"><span data-stu-id="0203e-113">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="0203e-114">Glossário</span><span class="sxs-lookup"><span data-stu-id="0203e-114">Glossary</span></span>

  - <span data-ttu-id="0203e-115">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="0203e-115">Front-end Servers</span></span>

  - <span data-ttu-id="0203e-116">Servidores SQL de back-end</span><span class="sxs-lookup"><span data-stu-id="0203e-116">Backend SQL Servers</span></span>

  - <span data-ttu-id="0203e-117">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="0203e-117">Mediation Servers</span></span>

  - <span data-ttu-id="0203e-118">Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="0203e-118">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="0203e-119">Quais são os principais indicadores de integridade?</span><span class="sxs-lookup"><span data-stu-id="0203e-119">What are Key Health Indicators?</span></span>

<span data-ttu-id="0203e-120">Os principais indicadores de integridade são contadores de desempenho com limiares destinados à revelação de problemas de experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="0203e-120">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="0203e-121">Coletar dados de KHI é geralmente a primeira etapa para implementar a metodologia de qualidade de chamada (CQM), que se concentra em garantir uma experiência de áudio de qualidade para usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="0203e-121">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="0203e-122">Os KHIs são usados além das soluções de monitoramento padrão do Lync (por exemplo, o System Center Operations Manager, as transações sintéticas, o monitoramento do servidor) e não em vez dessas soluções.</span><span class="sxs-lookup"><span data-stu-id="0203e-122">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="0203e-123">Colete os contadores de desempenho do KHI e preencha a planilha KHI que acompanha o guia de rede para produzir um scorecard que o ajudará a determinar a integridade do servidor de uma implantação do Lync.</span><span class="sxs-lookup"><span data-stu-id="0203e-123">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="0203e-124">Depois de preenchida, ele orienta você a reparar o ambiente e dá mais percepção a outros participantes.</span><span class="sxs-lookup"><span data-stu-id="0203e-124">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="0203e-125">Avaliar o KHIs mensalmente e incorporá-los em todos os processos operacionais em andamento da implantação.</span><span class="sxs-lookup"><span data-stu-id="0203e-125">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="0203e-126">Baixe o [Guia de rede do Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) para ver a lista completa de KHIs e para obter as planilhas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0203e-126">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="0203e-127">Para coletar dados do KHI</span><span class="sxs-lookup"><span data-stu-id="0203e-127">To Collect KHI Data</span></span>

1.  <span data-ttu-id="0203e-128">Execute o script KHI incluído no guia de rede do Lync Server em cada Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0203e-128">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="0203e-129">Isso criará um coletor de dados dentro do monitor de desempenho e o nomeará KHI.</span><span class="sxs-lookup"><span data-stu-id="0203e-129">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="0203e-130">Por padrão, os dados serão pesquisados a cada 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="0203e-130">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="0203e-131">Antes do início do dia útil da sua empresa, vá para cada servidor do Lync e inicie o coletor de dados KHI.</span><span class="sxs-lookup"><span data-stu-id="0203e-131">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="0203e-132">No final desse dia, interrompa o coletor de dados do KHI e copie os dados para um local central.</span><span class="sxs-lookup"><span data-stu-id="0203e-132">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="0203e-133">Após usar o monitor de desempenho para preencher a planilha do KHI incluída no download do guia de rede do Lync Server, compare os resultados com os alvos recomendados.</span><span class="sxs-lookup"><span data-stu-id="0203e-133">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="0203e-134">Fluxo de correção para todas as funções de servidor</span><span class="sxs-lookup"><span data-stu-id="0203e-134">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="0203e-135">Para cada servidor em sua implementação do Lync, comece verificando se a integridade do componente do servidor e o desempenho do sistema estão no nível desejado ou acima dele.</span><span class="sxs-lookup"><span data-stu-id="0203e-135">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="0203e-136">Somente depois isso deve observar os indicadores relacionados à função do servidor na implementação geral do Lync.</span><span class="sxs-lookup"><span data-stu-id="0203e-136">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="0203e-137">Comece coletando dados de desempenho do KHI para todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="0203e-137">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="0203e-138">Para cada uma das funções de sistema (detalhes abordados posteriormente neste documento), determine se os componentes básicos do sistema atendem aos alvos recomendados.</span><span class="sxs-lookup"><span data-stu-id="0203e-138">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="0203e-139">Caso contrário, corrija o desempenho do sistema e, em seguida, colete novamente os dados do KHI e garanta a integridade do sistema antes de examinar as métricas específicas da função do servidor na implementação do Lync.</span><span class="sxs-lookup"><span data-stu-id="0203e-139">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="0203e-140">A integridade do componente para todas as funções é definida como:</span><span class="sxs-lookup"><span data-stu-id="0203e-140">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="0203e-141">Utilização da CPU \< 80%</span><span class="sxs-lookup"><span data-stu-id="0203e-141">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="0203e-142">Média de gravação de disco \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="0203e-142">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="0203e-143">Média de leitura de disco \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="0203e-143">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="0203e-144">Memória disponível de \> 20% no total de sistema</span><span class="sxs-lookup"><span data-stu-id="0203e-144">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="0203e-145">Comprimento da fila de rede \< 2</span><span class="sxs-lookup"><span data-stu-id="0203e-145">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="0203e-146">Pacotes descartados (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-146">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="0203e-147">Glossário</span><span class="sxs-lookup"><span data-stu-id="0203e-147">Glossary</span></span>

<span data-ttu-id="0203e-148">Os seguintes termos e acrônimos são usados neste cartaz:</span><span class="sxs-lookup"><span data-stu-id="0203e-148">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="0203e-149">Como MCU = unidade de controle de vários pontos do compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="0203e-149">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="0203e-150">AV MCU = áudio/vídeo MCU</span><span class="sxs-lookup"><span data-stu-id="0203e-150">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="0203e-151">IM MCU = mensagens instantâneas MCU</span><span class="sxs-lookup"><span data-stu-id="0203e-151">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="0203e-152">UCWA = API Web de comunicações unificadas</span><span class="sxs-lookup"><span data-stu-id="0203e-152">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="0203e-153">Borda AV = passagem de áudio/vídeo por borda</span><span class="sxs-lookup"><span data-stu-id="0203e-153">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="0203e-154">Autenticação AV = autenticação de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="0203e-154">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="0203e-155">Pilha SIP = contém a implementação principal SIP do Lync</span><span class="sxs-lookup"><span data-stu-id="0203e-155">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="0203e-156">Proxy de dados = usado para conferência de borda</span><span class="sxs-lookup"><span data-stu-id="0203e-156">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="0203e-157">LySS = serviço de armazenamento do Lync</span><span class="sxs-lookup"><span data-stu-id="0203e-157">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="0203e-158">Servidores front-end</span><span class="sxs-lookup"><span data-stu-id="0203e-158">Front-end Servers</span></span>

<span data-ttu-id="0203e-159">Os seguintes destinos KHI recomendados são específicos para servidores front-end, além da integridade básica do componente:</span><span class="sxs-lookup"><span data-stu-id="0203e-159">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0203e-160">Área funcional</span><span class="sxs-lookup"><span data-stu-id="0203e-160">Functional area</span></span></th>
<th><span data-ttu-id="0203e-161">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="0203e-161">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0203e-162">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="0203e-162">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="0203e-163">Estado 2 da integridade MCU &lt;</span><span class="sxs-lookup"><span data-stu-id="0203e-163">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0203e-164">Web Components</span><span class="sxs-lookup"><span data-stu-id="0203e-164">Web Components</span></span></p></td>
<td><p><span data-ttu-id="0203e-165">Tempos limite do AD de expansão de lista de distribuição &lt; 0</span><span class="sxs-lookup"><span data-stu-id="0203e-165">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="0203e-166">Falhas de ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-166">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="0203e-167">Falhas de LIS = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-167">LIS failures = 0</span></span></p>
<p><span data-ttu-id="0203e-168">Erros de autenticação &lt; 1/seg</span><span class="sxs-lookup"><span data-stu-id="0203e-168">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="0203e-169">Solicitações ASP.NET v4 rejeitadas = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-169">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0203e-170">Pilha SIP</span><span class="sxs-lookup"><span data-stu-id="0203e-170">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="0203e-171">Média de processamento de mensagens de entrada &lt; 1 seg</span><span class="sxs-lookup"><span data-stu-id="0203e-171">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="0203e-172">Respostas de entrada ignoradas &lt; 1/seg solicitações de entrada descartadas &lt; 1/s</span><span class="sxs-lookup"><span data-stu-id="0203e-172">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="0203e-173">Latência da fila &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="0203e-173">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="0203e-174">Latência SPROC &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="0203e-174">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="0203e-175">Solicitações limitadas = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-175">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="0203e-176">Erros de autenticação &lt; 1/seg</span><span class="sxs-lookup"><span data-stu-id="0203e-176">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="0203e-177">Mensagens de entrada tempo limite de &lt; 2</span><span class="sxs-lookup"><span data-stu-id="0203e-177">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="0203e-178">Média de mensagens de entrada suspensas &lt; 1 seg</span><span class="sxs-lookup"><span data-stu-id="0203e-178">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="0203e-179">Conexões controladas por fluxo &lt; 2</span><span class="sxs-lookup"><span data-stu-id="0203e-179">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="0203e-180">Atraso médio da fila de saída &lt; 2 seg</span><span class="sxs-lookup"><span data-stu-id="0203e-180">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0203e-181">LySS</span><span class="sxs-lookup"><span data-stu-id="0203e-181">LySS</span></span></p></td>
<td><p><span data-ttu-id="0203e-182">% de espaço usado pelo serviço de armazenamento DB &lt; 80</span><span class="sxs-lookup"><span data-stu-id="0203e-182">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="0203e-183"># falhas de replicação de réplica = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-183"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="0203e-184"># eventos de perda de dados = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-184"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0203e-185">SQL</span><span class="sxs-lookup"><span data-stu-id="0203e-185">SQL</span></span></p></td>
<td><p><span data-ttu-id="0203e-186">Expectativa de vida da página &gt; 300 seg.</span><span class="sxs-lookup"><span data-stu-id="0203e-186">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="0203e-187">Solicitações em lote/s &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="0203e-187">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="0203e-188">Servidores SQL de back-end</span><span class="sxs-lookup"><span data-stu-id="0203e-188">Backend SQL Servers</span></span>

<span data-ttu-id="0203e-189">Os seguintes destinos KHI recomendados são específicos para os SQL Servers, além da integridade básica do componente:</span><span class="sxs-lookup"><span data-stu-id="0203e-189">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0203e-190">Área funcional</span><span class="sxs-lookup"><span data-stu-id="0203e-190">Functional area</span></span></th>
<th><span data-ttu-id="0203e-191">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="0203e-191">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0203e-192">SQL</span><span class="sxs-lookup"><span data-stu-id="0203e-192">SQL</span></span></p></td>
<td><p><span data-ttu-id="0203e-193">Expectativa de vida da página &gt; 300 seg.</span><span class="sxs-lookup"><span data-stu-id="0203e-193">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="0203e-194">Solicitações em lote/s &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="0203e-194">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="0203e-195">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="0203e-195">Mediation Servers</span></span>

<span data-ttu-id="0203e-196">Os seguintes destinos KHI recomendados são específicos para servidores de mediação além da integridade básica do componente:</span><span class="sxs-lookup"><span data-stu-id="0203e-196">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0203e-197">Área funcional</span><span class="sxs-lookup"><span data-stu-id="0203e-197">Functional area</span></span></th>
<th><span data-ttu-id="0203e-198">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="0203e-198">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0203e-199">Serviço do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="0203e-199">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="0203e-200">Índice de falha de chamada de carregamento = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-200">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="0203e-201">Chamadas com falha devido ao proxy &lt; 10</span><span class="sxs-lookup"><span data-stu-id="0203e-201">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="0203e-202">Chamadas com falha devido ao gateway &lt; 10</span><span class="sxs-lookup"><span data-stu-id="0203e-202">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="0203e-203">Chamadas (in ou out) rejeitadas = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-203">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="0203e-204">Candidatos à mídia ausentes = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-204">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="0203e-205">Falhas de verificação de conectividade de mídia = 0</span><span class="sxs-lookup"><span data-stu-id="0203e-205">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="0203e-206">Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="0203e-206">Edge Servers</span></span>

<span data-ttu-id="0203e-207">Os seguintes destinos KHI recomendados são específicos para servidores de borda além da integridade básica do componente:</span><span class="sxs-lookup"><span data-stu-id="0203e-207">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0203e-208">Área funcional</span><span class="sxs-lookup"><span data-stu-id="0203e-208">Functional area</span></span></th>
<th><span data-ttu-id="0203e-209">Métricas de destino</span><span class="sxs-lookup"><span data-stu-id="0203e-209">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0203e-210">Autenticação AV</span><span class="sxs-lookup"><span data-stu-id="0203e-210">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="0203e-211">Solicitações inválidas &lt; 20/seg</span><span class="sxs-lookup"><span data-stu-id="0203e-211">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0203e-212">Borda de AV</span><span class="sxs-lookup"><span data-stu-id="0203e-212">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="0203e-213">Falhas de auth. &lt; 20/seg</span><span class="sxs-lookup"><span data-stu-id="0203e-213">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="0203e-214">Falhas de alocação &lt; 20/seg</span><span class="sxs-lookup"><span data-stu-id="0203e-214">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="0203e-215">Pacotes removidos &lt; 300/s</span><span class="sxs-lookup"><span data-stu-id="0203e-215">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0203e-216">Proxy de dados</span><span class="sxs-lookup"><span data-stu-id="0203e-216">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="0203e-217">Conexões de servidor limitado &lt; 3</span><span class="sxs-lookup"><span data-stu-id="0203e-217">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="0203e-218">O sistema está regulando &lt; 1</span><span class="sxs-lookup"><span data-stu-id="0203e-218">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0203e-219">Pilha SIP</span><span class="sxs-lookup"><span data-stu-id="0203e-219">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="0203e-220">Conexões com limite ignorado &lt; 1</span><span class="sxs-lookup"><span data-stu-id="0203e-220">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="0203e-221">Envio do tempo limite de &lt; 10</span><span class="sxs-lookup"><span data-stu-id="0203e-221">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="0203e-222">Conexões de fluxo controlado &lt; 100</span><span class="sxs-lookup"><span data-stu-id="0203e-222">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="0203e-223">Solicitações de entrada descartadas &lt; 1/s</span><span class="sxs-lookup"><span data-stu-id="0203e-223">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="0203e-224">Média de processamento de mensagens &lt; 3 seg</span><span class="sxs-lookup"><span data-stu-id="0203e-224">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0203e-225">Confira também</span><span class="sxs-lookup"><span data-stu-id="0203e-225">See Also</span></span>


[<span data-ttu-id="0203e-226">Guia de rede do Lync Server</span><span class="sxs-lookup"><span data-stu-id="0203e-226">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="0203e-227">Principais indicadores de integridade: a base para manter os servidores de Lync saudáveis</span><span class="sxs-lookup"><span data-stu-id="0203e-227">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="0203e-228">Metodologia de qualidade de chamada do Lync</span><span class="sxs-lookup"><span data-stu-id="0203e-228">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

