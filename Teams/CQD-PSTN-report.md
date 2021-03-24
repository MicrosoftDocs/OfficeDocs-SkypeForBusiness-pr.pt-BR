---
title: Usando o relatório de Roteamento Direto PSTN PSTN
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Use o relatório CQD (Painel de Qualidade de Chamadas) PSTN do Microsoft Teams para monitorar e solucionar problemas de chamadas PSTN no Microsoft Teams.
ms.openlocfilehash: f2b63f991f42aa4de9e0e4474137f7f992f95c53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094975"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="538fd-103">Usando o relatório de Roteamento Direto PSTN PSTN</span><span class="sxs-lookup"><span data-stu-id="538fd-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="538fd-104">Novo em março de 2020, adicionamos um relatório de Roteamento Direto do Painel de Qualidade de Chamadas (CQD) do Microsoft Teams para nossos modelos de consulta do Power BI baixáveis para [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="538fd-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="538fd-105">O relatório de Roteamento Direto PSTN (CQD PSTN Direct Routing Report.pbit) ajuda você a entender os padrões de uso e a qualidade dos seus serviços PSTN.</span><span class="sxs-lookup"><span data-stu-id="538fd-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="538fd-106">Use este relatório para monitorar o uso do serviço, informações sobre seu Controlador de Borda de Sessão (SBC), o serviço de telefonia, os parâmetros de rede e os detalhes da Taxa de Eficácia de Rede.</span><span class="sxs-lookup"><span data-stu-id="538fd-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="538fd-107">Essas informações podem ajudá-lo a identificar problemas, incluindo o motivo das chamadas não a atender.</span><span class="sxs-lookup"><span data-stu-id="538fd-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="538fd-108">Por exemplo, você poderá ver quando o volume cair ou quantas chamadas serão afetadas e por qual motivo.</span><span class="sxs-lookup"><span data-stu-id="538fd-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="538fd-109">O Relatório de Roteamento Direto PSTN do CQD tem quatro seções:</span><span class="sxs-lookup"><span data-stu-id="538fd-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="538fd-110">Visão geral do PSTN</span><span class="sxs-lookup"><span data-stu-id="538fd-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="538fd-111">Detalhes do serviço</span><span class="sxs-lookup"><span data-stu-id="538fd-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="538fd-112">Taxa de eficácia da rede</span><span class="sxs-lookup"><span data-stu-id="538fd-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="538fd-113">Parâmetros de rede</span><span class="sxs-lookup"><span data-stu-id="538fd-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="538fd-114">Realçadores</span><span class="sxs-lookup"><span data-stu-id="538fd-114">Highlights</span></span>

1. <span data-ttu-id="538fd-115">Analisar por tipo de chamada, SBC, país chamador e chamador</span><span class="sxs-lookup"><span data-stu-id="538fd-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="538fd-116">O relatório de Roteamento Direto PSTN do CQD agrega métricas de confiabilidade e uso para todos os SBCs em seu locatário nos últimos 7, 30 ou 180 dias (6 meses).</span><span class="sxs-lookup"><span data-stu-id="538fd-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="538fd-117">Você pode analisar dados por tipo de chamada, SBC, país de chamador e chamador.</span><span class="sxs-lookup"><span data-stu-id="538fd-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="538fd-118">Se você estiver interessado em um determinado SBC ou país, poderá identificar alterações nas tendências ao longo do intervalo de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="538fd-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Captura de tela de filtros disponíveis no relatório de Roteamento Direto PSTN PSTN":::
   
2. <span data-ttu-id="538fd-120">Acompanhar tendências</span><span class="sxs-lookup"><span data-stu-id="538fd-120">Track trends</span></span>

    <span data-ttu-id="538fd-121">A análise de tendências é essencial ao tentar entender o uso e a confiabilidade do serviço.</span><span class="sxs-lookup"><span data-stu-id="538fd-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="538fd-122">As tendências de hora em hora fornecem uma olhada de perto no desempenho diário, o que ajuda a identificar incidentes em tempo real.</span><span class="sxs-lookup"><span data-stu-id="538fd-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="538fd-123">As tendências diárias permitem que você veja a saúde do serviço de uma perspectiva de longo prazo.</span><span class="sxs-lookup"><span data-stu-id="538fd-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="538fd-124">É importante poder mudar entre esses dois modos com granularidade de dados apropriada.</span><span class="sxs-lookup"><span data-stu-id="538fd-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="538fd-125">O relatório de Roteamento Direto PSTN do CQD fornece uma visão geral de tendências de 6 meses, tendências diárias de 7 e 30 dias e tendências por hora para que você possa analisar o desempenho em cada nível.</span><span class="sxs-lookup"><span data-stu-id="538fd-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Captura de tela dos gráficos de tendências no relatório de Roteamento Direto PSTN PSTN":::

3. <span data-ttu-id="538fd-127">Faça uma análise de SBC ou nível do usuário</span><span class="sxs-lookup"><span data-stu-id="538fd-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="538fd-128">Estamos criando recursos de análise em várias categorias de dados no CQD, o que permite entender rapidamente a distribuição de uso ou confiabilidade no nível SBC ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="538fd-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="538fd-129">Usando o drill through, você pode rapidamente resolver problemas e entender o impacto real do usuário.</span><span class="sxs-lookup"><span data-stu-id="538fd-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="538fd-130">Os recursos do relatório de Roteamento Direto do PSTN do CQD são detalhados nas métricas Detalhe do Serviço e Taxa de Eficácia da Rede.</span><span class="sxs-lookup"><span data-stu-id="538fd-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="538fd-131">Clique no ponto de dados em que você está interessado para fazer uma análise de detalhes no nível do usuário ou SBC.</span><span class="sxs-lookup"><span data-stu-id="538fd-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Captura de tela mostrando a funcionalidade de drill-through em um ponto de dados":::


## <a name="pstn-overview"></a><span data-ttu-id="538fd-133">Visão geral do PSTN</span><span class="sxs-lookup"><span data-stu-id="538fd-133">PSTN Overview</span></span>

<span data-ttu-id="538fd-134">O Relatório de Roteamento Direto PSTN do CQD fornece as seguintes informações relacionadas à saúde geral do serviço nos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="538fd-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="538fd-135">![Captura de tela: relatório CQD do PSTN](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="538fd-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="538fd-136">Por exemplo, se você estiver interessado no uso geral e na saúde sobre todas as chamadas de entrada que passam pelo SBC abc.bca.adatum.biz com os EUA como o país interno:</span><span class="sxs-lookup"><span data-stu-id="538fd-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="538fd-137">**Chamada**</span><span class="sxs-lookup"><span data-stu-id="538fd-137">**Call Out**</span></span> | <span data-ttu-id="538fd-138">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="538fd-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="538fd-139">1</span><span class="sxs-lookup"><span data-stu-id="538fd-139">1</span></span>            | <span data-ttu-id="538fd-140">Você pode usar os filtros na parte superior para detalhar e selecionar ByotIn como tipo de chamada, abc.bca.contoso.com como Controlador de Quadro de Sessão e EUA como país interno.</span><span class="sxs-lookup"><span data-stu-id="538fd-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="538fd-141">2</span><span class="sxs-lookup"><span data-stu-id="538fd-141">2</span></span>            | <span data-ttu-id="538fd-142">Tendência de uso dos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="538fd-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="538fd-143">Você pode encontrar o relatório de detalhes de uso na página Detalhes do Serviço.</span><span class="sxs-lookup"><span data-stu-id="538fd-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="538fd-144">3</span><span class="sxs-lookup"><span data-stu-id="538fd-144">3</span></span>            | <span data-ttu-id="538fd-145">Tendência de atraso, latência, tremência e perda de pacotes nos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="538fd-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="538fd-146">Você pode encontrar o relatório detalhado na página Parâmetros de Rede.</span><span class="sxs-lookup"><span data-stu-id="538fd-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="538fd-147">4</span><span class="sxs-lookup"><span data-stu-id="538fd-147">4</span></span>            | <span data-ttu-id="538fd-148">Tendência de Chamada Simultânea e Usuário Ativo Diário nos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="538fd-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="538fd-149">Este gráfico pode ajudá-lo a entender o volume máximo do serviço.</span><span class="sxs-lookup"><span data-stu-id="538fd-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="538fd-150">5</span><span class="sxs-lookup"><span data-stu-id="538fd-150">5</span></span>            | <span data-ttu-id="538fd-151">Motivo de término de chamada superior afetou a qualidade do serviço nos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="538fd-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="538fd-152">Você pode encontrar detalhes de saúde do serviço na página Network Effective Ratio(NER).</span><span class="sxs-lookup"><span data-stu-id="538fd-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="538fd-153">Detalhes do serviço</span><span class="sxs-lookup"><span data-stu-id="538fd-153">Service Details</span></span>

<span data-ttu-id="538fd-154">Esta página fornece tendências de uso do serviço por dia e análise de comentários do usuário por geográfico.</span><span class="sxs-lookup"><span data-stu-id="538fd-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="538fd-155">**Total de chamadas de tentativa –** Total de chamadas de tentativa nesse intervalo de tempo, incluindo chamadas bem-sucedidas e com falha</span><span class="sxs-lookup"><span data-stu-id="538fd-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="538fd-156">**Total de chamadas conectadas -** Total de chamadas conectadas nesse intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="538fd-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="538fd-157">**Total de Minutos –** Uso total de minutos nesse intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="538fd-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="538fd-158">**Dau (Daily Active Users) –** Contagem de usuários ativos diários que fizeram pelo menos uma chamada conectada nesse dia</span><span class="sxs-lookup"><span data-stu-id="538fd-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="538fd-159">**Chamadas simultâneas –** Máximo de chamadas ativas simultâneas em um minuto</span><span class="sxs-lookup"><span data-stu-id="538fd-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="538fd-160">**Comentários do usuário –** A pontuação "Rate My Call" vem do usuário.</span><span class="sxs-lookup"><span data-stu-id="538fd-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="538fd-161">3 a 5 é considerado uma boa chamada.</span><span class="sxs-lookup"><span data-stu-id="538fd-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="538fd-162">1-2 é considerado como uma chamada ruim.</span><span class="sxs-lookup"><span data-stu-id="538fd-162">1-2 is considered as a bad call.</span></span>

![Captura de tela: relatório CQD do PSTN](media/CQD-PSTN-report2.png)

<span data-ttu-id="538fd-164">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="538fd-164">For example:</span></span>

1.  <span data-ttu-id="538fd-165">Se você vir que a duração média da chamada cai para 0 em 14/02/2020, primeiro você pode verificar se o volume da chamada parece normal e ver se há uma grande discrepância entre o total de chamadas de conexão e o total de chamadas de tentativa.</span><span class="sxs-lookup"><span data-stu-id="538fd-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="538fd-166">Em seguida, vá para a página Taxa de Eficácia de Rede para investir em motivos de falha de chamada.</span><span class="sxs-lookup"><span data-stu-id="538fd-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="538fd-167">Se você vir o aumento de pontos vermelhos no mapa de comentários do usuário, poderá ir para a página Taxa de Eficácia de Rede e Parâmetro de Rede para ver se há alguma anomalia e você pode levantar um tíquete usando o MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="538fd-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="538fd-168">Taxa de eficácia da rede</span><span class="sxs-lookup"><span data-stu-id="538fd-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="538fd-169">Essa é a mesma métrica que aparece no painel Saúde Geral.</span><span class="sxs-lookup"><span data-stu-id="538fd-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="538fd-170">Você pode verificar o número de NER por hora com os detalhes de chamadas afetadas para ambas as direções de chamada (entrada/saída) na taxa de eficácia da rede por hora e gráfico de motivos de término de chamada abaixo.</span><span class="sxs-lookup"><span data-stu-id="538fd-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="538fd-171">**NER** - A capacidade (%) de uma rede para fornecer chamadas medindo o número de chamadas enviadas versus o número de chamadas entregues a um destinatário.</span><span class="sxs-lookup"><span data-stu-id="538fd-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="538fd-172">**Código de resposta SIP**- Um código de resposta inteiro de três dígitos mostra o status da chamada.</span><span class="sxs-lookup"><span data-stu-id="538fd-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="538fd-173">**Código de resposta da Microsoft**- Um código de resposta enviado do componente microsoft.</span><span class="sxs-lookup"><span data-stu-id="538fd-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="538fd-174">**Descrição** – A fase do motivo que corresponde ao código de resposta SIP e ao código de resposta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="538fd-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="538fd-175">**Número de chamadas afetadas** – O número total de chamadas foi afetada durante o intervalo de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="538fd-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Captura de tela: relatório CQD do PSTN](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="538fd-177">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="538fd-177">For example:</span></span>

![Captura de tela: relatório CQD do PSTN](media/CQD-PSTN-report4.png)

<span data-ttu-id="538fd-179">Se o NER Diário tiver um dip em 05/02/2020, você poderá clicar na data e outros gráficos aumentarão para essa data específica.</span><span class="sxs-lookup"><span data-stu-id="538fd-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Captura de tela: relatório CQD do PSTN](media/CQD-PSTN-report5.png)

<span data-ttu-id="538fd-181">No NER Good Percentage Hourly Trend, você pode encontrar que o dip acontece por volta das 21:00.</span><span class="sxs-lookup"><span data-stu-id="538fd-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="538fd-182">Em seguida, clique novamente para ampliar para a hora 21 e verifique Detalhes da Chamada Efetiva para ver quantas chamadas falharam nessa hora e quais são os motivos de término da chamada.</span><span class="sxs-lookup"><span data-stu-id="538fd-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="538fd-183">Você pode começar com disparos de autoprofissão em qualquer problema SBC ou relatar ao Service Desk se o problema não estiver relacionado ao SBC.</span><span class="sxs-lookup"><span data-stu-id="538fd-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="538fd-184">Parâmetros de rede</span><span class="sxs-lookup"><span data-stu-id="538fd-184">Network Parameters</span></span>

<span data-ttu-id="538fd-185">Todos os parâmetros de rede são medidos da interface roteamento direto para o Controlador de Borda de Sessão.</span><span class="sxs-lookup"><span data-stu-id="538fd-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="538fd-186">Para obter informações sobre os valores recomendados, consulte [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span><span class="sxs-lookup"><span data-stu-id="538fd-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="538fd-187">**Tremido** – É a medida milissegunda de variação no tempo de atraso de propagação da rede calculada entre dois pontos de extremidade usando RTCP (O Protocolo de Controle RTP).</span><span class="sxs-lookup"><span data-stu-id="538fd-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="538fd-188">**Perda de pacotes** – é uma medida de pacote que falhou ao chegar; ele é calculado entre dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="538fd-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="538fd-189">**Latência** - (Também conhecido como tempo de viagem de ida e volta) é o tempo necessário para que um sinal seja enviado mais o tempo necessário para o reconhecimento desse sinal ser recebido.</span><span class="sxs-lookup"><span data-stu-id="538fd-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="538fd-190">Esse atraso de tempo consiste nos tempos de propagação entre os dois pontos de um sinal.</span><span class="sxs-lookup"><span data-stu-id="538fd-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Captura de tela: relatório CQD do PSTN](media/CQD-PSTN-report6.png)

<span data-ttu-id="538fd-192">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="538fd-192">For example:</span></span>

<span data-ttu-id="538fd-193">Se você vir um pico em qualquer um dos quatro gráficos (Latência, Tremência, Taxa de Perda de Pacote, Atraso pós-discagem) para uma data específica, por exemplo, Latência em 14/02/2020, clique no ponto de data.</span><span class="sxs-lookup"><span data-stu-id="538fd-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="538fd-194">E o gráfico de tendências por hora na parte inferior será atualizado para mostrar o número por hora.</span><span class="sxs-lookup"><span data-stu-id="538fd-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="538fd-195">Você pode verificar os SBCs ou levantar um tíquete com o MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="538fd-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Captura de tela: relatório CQD do PSTN](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="538fd-197">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="538fd-197">Related topics</span></span>

[<span data-ttu-id="538fd-198">Usar o Power BI para analisar dados CQD para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="538fd-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="538fd-199">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="538fd-199">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)