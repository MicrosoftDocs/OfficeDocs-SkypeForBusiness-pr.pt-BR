---
title: Usando o relatório de roteamento direto do CQD PSTN
ms.author: lolaj
author: LolaJacobsen
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
description: Use o relatório de roteamento direto do Microsoft Teams Call (CQD)) PSTN para monitorar e solucionar problemas de chamadas PSTN no Microsoft Teams.
ms.openlocfilehash: 0987ae30c9bb0b428a4d46bf036c2de938c555f0
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085337"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="1381c-103">Usando o relatório de roteamento direto do CQD PSTN</span><span class="sxs-lookup"><span data-stu-id="1381c-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="1381c-104">Novidades de março de 2020, adicionamos um relatório de roteamento direto PSTN do Microsoft Teams CQD (Microsoft Teams Call Quality) a nossos [modelos de consulta para download do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="1381c-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="1381c-105">O CQD PSTN Direct Routing Report (CQD PSTN Direct Routing Report. PBit) ajuda você a entender os padrões de uso e a qualidade dos seus serviços PSTN.</span><span class="sxs-lookup"><span data-stu-id="1381c-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="1381c-106">Use esse relatório para monitorar o uso do serviço, informações sobre o seu controlador de borda de sessão (SBC), o serviço de telefonia, os parâmetros de rede e os detalhes da taxa de eficácia da rede.</span><span class="sxs-lookup"><span data-stu-id="1381c-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="1381c-107">Essas informações podem ajudá-lo a identificar problemas, incluindo o motivo para as chamadas descartadas.</span><span class="sxs-lookup"><span data-stu-id="1381c-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="1381c-108">Por exemplo, você poderá ver quando o volume cai ou quantas chamadas são afetadas e por qual motivo.</span><span class="sxs-lookup"><span data-stu-id="1381c-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="1381c-109">O relatório de roteamento direto PSTN CQD tem quatro seções:</span><span class="sxs-lookup"><span data-stu-id="1381c-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="1381c-110">Visão geral da PSTN</span><span class="sxs-lookup"><span data-stu-id="1381c-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="1381c-111">Detalhes do serviço</span><span class="sxs-lookup"><span data-stu-id="1381c-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="1381c-112">Taxa de eficácia da rede</span><span class="sxs-lookup"><span data-stu-id="1381c-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="1381c-113">Parâmetros de rede</span><span class="sxs-lookup"><span data-stu-id="1381c-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="1381c-114">Alça</span><span class="sxs-lookup"><span data-stu-id="1381c-114">Highlights</span></span>

1. <span data-ttu-id="1381c-115">Analisar por tipo de chamada, SBC, chamador e chamado Country</span><span class="sxs-lookup"><span data-stu-id="1381c-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="1381c-116">O CQD PSTN Direct Routing Report agrega as métricas de confiabilidade e uso de todos os SBCs em seu locatário para os últimos 7, 30 ou 180 dias (6 meses).</span><span class="sxs-lookup"><span data-stu-id="1381c-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="1381c-117">Você pode analisar dados por tipo de chamada, SBC, chamador e chamado país.</span><span class="sxs-lookup"><span data-stu-id="1381c-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="1381c-118">Se estiver interessado em um determinado SBC ou país, você poderá identificar as alterações nas tendências ao longo do intervalo de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1381c-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Captura de tela de filtros disponíveis no relatório de roteamento direto PSTN CQD":::
   
2. <span data-ttu-id="1381c-120">Controlar tendências</span><span class="sxs-lookup"><span data-stu-id="1381c-120">Track trends</span></span>

    <span data-ttu-id="1381c-121">A análise de tendências é essencial ao tentar entender o uso e a confiabilidade do serviço.</span><span class="sxs-lookup"><span data-stu-id="1381c-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="1381c-122">As tendências horárias fornecem uma visão detalhada do desempenho diário, o que ajuda a identificar incidentes em tempo real.</span><span class="sxs-lookup"><span data-stu-id="1381c-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="1381c-123">As tendências diárias permitem que você veja a integridade do seu serviço a partir de uma perspectiva de longo prazo.</span><span class="sxs-lookup"><span data-stu-id="1381c-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="1381c-124">É importante poder alternar entre esses dois modos com a granularidade de dados adequada.</span><span class="sxs-lookup"><span data-stu-id="1381c-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="1381c-125">O CQD PSTN Direct Routing Report fornece uma visão geral de tendências de 6 meses, tendências diárias de 7 e 30 dias e tendências horárias, para que você possa analisar o desempenho em cada nível.</span><span class="sxs-lookup"><span data-stu-id="1381c-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Captura de tela de gráficos de tendências no CQD PSTN Direct Routing Report":::

3. <span data-ttu-id="1381c-127">Fazer drill-through para SBC ou em nível de usuário</span><span class="sxs-lookup"><span data-stu-id="1381c-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="1381c-128">Criamos recursos de Drill-through em muitas categorias de dados no CQD, que permite que você entenda rapidamente o uso ou a distribuição de confiabilidade no SBC ou no nível do usuário.</span><span class="sxs-lookup"><span data-stu-id="1381c-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="1381c-129">Ao usar Drill through, você pode poinpoint rapidamente problemas e entender o impacto real dos usuários.</span><span class="sxs-lookup"><span data-stu-id="1381c-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="1381c-130">Os recursos do relatório de roteamento direto PSTN CQD analisam as métricas de detalhes do serviço e de eficácia da rede.</span><span class="sxs-lookup"><span data-stu-id="1381c-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="1381c-131">Clique no ponto de dados em que você está interessado para analisar detalhes do nível do usuário ou do SBC.</span><span class="sxs-lookup"><span data-stu-id="1381c-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Captura de tela mostrando a funcionalidade de Drill-through em um ponto de dados":::


## <a name="pstn-overview"></a><span data-ttu-id="1381c-133">Visão geral da PSTN</span><span class="sxs-lookup"><span data-stu-id="1381c-133">PSTN Overview</span></span>

<span data-ttu-id="1381c-134">O CQD PSTN Direct Routing Report fornece as informações a seguir relacionadas à integridade geral do serviço dos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="1381c-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="1381c-135">![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="1381c-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="1381c-136">Por exemplo, se você estiver interessado no uso geral e na integridade de todas as chamadas recebidas por meio do SBC abc.bca.adatum.biz conosco como o país interno:</span><span class="sxs-lookup"><span data-stu-id="1381c-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="1381c-137">**Chame para fora**</span><span class="sxs-lookup"><span data-stu-id="1381c-137">**Call Out**</span></span> | <span data-ttu-id="1381c-138">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1381c-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1381c-139">1</span><span class="sxs-lookup"><span data-stu-id="1381c-139">1</span></span>            | <span data-ttu-id="1381c-140">Você pode usar os filtros na parte superior para fazer drill down e selecionar ByotIn como tipo de chamada, abc.bca.contoso.com como controlador de placa de sessão e EUA como país interno.</span><span class="sxs-lookup"><span data-stu-id="1381c-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="1381c-141">2</span><span class="sxs-lookup"><span data-stu-id="1381c-141">2</span></span>            | <span data-ttu-id="1381c-142">Tendência de uso dos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="1381c-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="1381c-143">Você pode encontrar o relatório de detalhes de uso na página de detalhes do serviço.</span><span class="sxs-lookup"><span data-stu-id="1381c-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="1381c-144">3</span><span class="sxs-lookup"><span data-stu-id="1381c-144">3</span></span>            | <span data-ttu-id="1381c-145">Atraso de discagem, latência, tremulação e tendência de perda de pacote nos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="1381c-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="1381c-146">Você pode encontrar um relatório detalhado na página parâmetros de rede.</span><span class="sxs-lookup"><span data-stu-id="1381c-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="1381c-147">4</span><span class="sxs-lookup"><span data-stu-id="1381c-147">4</span></span>            | <span data-ttu-id="1381c-148">Chamada simultânea e tendência de usuário ativo diário para os últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="1381c-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="1381c-149">Este gráfico pode ajudá-lo a entender o volume máximo do serviço.</span><span class="sxs-lookup"><span data-stu-id="1381c-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="1381c-150">5</span><span class="sxs-lookup"><span data-stu-id="1381c-150">5</span></span>            | <span data-ttu-id="1381c-151">Melhor motivo de término de chamada afetado qualidade do serviço dos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="1381c-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="1381c-152">Você pode encontrar detalhes de integridade do serviço na página de índice efetivo de rede (NER).</span><span class="sxs-lookup"><span data-stu-id="1381c-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="1381c-153">Detalhes do serviço</span><span class="sxs-lookup"><span data-stu-id="1381c-153">Service Details</span></span>

<span data-ttu-id="1381c-154">Esta página fornece as tendências de uso de serviço por dia e a divisão de comentários do usuário por meio do meio geográfico.</span><span class="sxs-lookup"><span data-stu-id="1381c-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="1381c-155">**Total de chamadas de tentativa –** Total de chamadas de tentativa nesse intervalo de tempo, incluindo tanto êxito como chamadas com falha</span><span class="sxs-lookup"><span data-stu-id="1381c-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="1381c-156">**Total de chamadas conectadas-** Total de chamadas conectadas nesse intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="1381c-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="1381c-157">**Total de minutos –** Uso total de minutos nesse intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="1381c-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="1381c-158">**Usuários ativos diariamente (DAU) –** Contagem de usuários ativos diários que fizeram pelo menos uma chamada conectada nesse dia</span><span class="sxs-lookup"><span data-stu-id="1381c-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="1381c-159">**Chamadas simultâneas –** Máximo de chamadas ativas simultâneas em um minuto</span><span class="sxs-lookup"><span data-stu-id="1381c-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="1381c-160">**Comentários do usuário –** A pontuação "classificar minha chamada" vem do usuário.</span><span class="sxs-lookup"><span data-stu-id="1381c-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="1381c-161">3-5 é considerado uma boa chamada.</span><span class="sxs-lookup"><span data-stu-id="1381c-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="1381c-162">1-2 é considerado como uma chamada incorreta.</span><span class="sxs-lookup"><span data-stu-id="1381c-162">1-2 is considered as a bad call.</span></span>

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report2.png)

<span data-ttu-id="1381c-164">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1381c-164">For example:</span></span>

1.  <span data-ttu-id="1381c-165">Se você vir as quedas médias de duração da chamada para 0 no 02/14/2020, você pode primeiro verificar se o volume da chamada está normal e ver se há uma grande discrepância entre o total de chamadas do Connect e as chamadas de tentativas totais.</span><span class="sxs-lookup"><span data-stu-id="1381c-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="1381c-166">Em seguida, acesse a página de razão da eficácia da rede para investir em motivos de falha na chamada.</span><span class="sxs-lookup"><span data-stu-id="1381c-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="1381c-167">Se vir o aumento dos pontos vermelhos no mapa de comentários do usuário, você poderá acessar a página de índice de eficácia da rede e o parâmetro de rede para ver se há anomalias e se você pode disparar um bilhete usando o MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="1381c-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="1381c-168">Taxa de eficácia da rede</span><span class="sxs-lookup"><span data-stu-id="1381c-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="1381c-169">Esta é a mesma métrica que aparece no painel de integridade geral.</span><span class="sxs-lookup"><span data-stu-id="1381c-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="1381c-170">Você pode verificar o número de NER por hora com os detalhes das chamadas afetadas para as direções da chamada (de entrada/saída) na taxa de eficácia horária da rede e no gráfico de motivo de término da chamada abaixo.</span><span class="sxs-lookup"><span data-stu-id="1381c-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="1381c-171">**Ner** – a capacidade (%) de uma rede para entregar chamadas medindo o número de chamadas enviadas versus o número de chamadas entregues a um destinatário.</span><span class="sxs-lookup"><span data-stu-id="1381c-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="1381c-172">**Código de resposta SIP**-um código de resposta de inteiro de três dígitos mostra o status da chamada.</span><span class="sxs-lookup"><span data-stu-id="1381c-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="1381c-173">**Código de resposta da Microsoft**-um código de resposta enviado do componente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1381c-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="1381c-174">**Descrição** – a fase de motivo correspondente ao código de resposta SIP e ao código de resposta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1381c-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="1381c-175">**Número de chamadas afetadas** – o número total de chamadas que você tem afetado durante o intervalo de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1381c-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="1381c-177">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1381c-177">For example:</span></span>

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report4.png)

<span data-ttu-id="1381c-179">Se o NER diário tiver um DIP no 02/05/2020, você poderá clicar na data e outros gráficos serão ampliados para essa data específica.</span><span class="sxs-lookup"><span data-stu-id="1381c-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report5.png)

<span data-ttu-id="1381c-181">Na NER boa porcentagem de tendência horária, você pode encontrar o DIP em torno de 21:00.</span><span class="sxs-lookup"><span data-stu-id="1381c-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="1381c-182">Em seguida, clique novamente para aplicar zoom à hora 21 e verificar detalhes de chamadas afetadas para ver quantas chamadas falharam nessa hora e quais são os motivos de término da chamada.</span><span class="sxs-lookup"><span data-stu-id="1381c-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="1381c-183">Você pode começar com a solução de problemas do SBC em qualquer problema de SBC ou relatório para o serviço de suporte se o problema não estiver relacionado ao SBC.</span><span class="sxs-lookup"><span data-stu-id="1381c-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="1381c-184">Parâmetros de rede</span><span class="sxs-lookup"><span data-stu-id="1381c-184">Network Parameters</span></span>

<span data-ttu-id="1381c-185">Todos os parâmetros de rede são medidos da interface de roteamento direto para o controlador de borda de sessão.</span><span class="sxs-lookup"><span data-stu-id="1381c-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="1381c-186">Para obter informações sobre os valores recomendados, consulte [preparar a rede da sua organização para o Microsoft Teams](prepare-network.md)e verificar os valores recomendados de borda do cliente para o Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="1381c-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="1381c-187">**Tremulação** – é a medida de milissegundos da variação no tempo de atraso de propagação de rede calculado entre dois pontos de extremidade usando RTCP (o protocolo de controle RTP).</span><span class="sxs-lookup"><span data-stu-id="1381c-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="1381c-188">**Perda de pacotes** – é uma medida do pacote que falhou ao chegar; Ele é calculado entre dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="1381c-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="1381c-189">**Latência** -(também conhecido como tempo de viagem de ida e volta) é o período de tempo que leva para o envio de um sinal mais o tempo necessário para que a confirmação daquele sinal seja recebida.</span><span class="sxs-lookup"><span data-stu-id="1381c-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="1381c-190">Esse atraso de tempo consiste nos tempos de propagação entre os dois pontos de um sinal.</span><span class="sxs-lookup"><span data-stu-id="1381c-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report6.png)

<span data-ttu-id="1381c-192">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1381c-192">For example:</span></span>

<span data-ttu-id="1381c-193">Se você vir um pico em qualquer um dos quatro gráficos (latência, tremulação, taxa de perda de pacote, atraso de discagem automática) para uma data específica, por exemplo, latência em 02/14/2020, clique no ponto de data.</span><span class="sxs-lookup"><span data-stu-id="1381c-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="1381c-194">O gráfico de tendências horárias na parte inferior será atualizado para mostrar o número por hora.</span><span class="sxs-lookup"><span data-stu-id="1381c-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="1381c-195">Você pode verificar o SBCs ou disparar um bilhete com o MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="1381c-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="1381c-197">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1381c-197">Related topics</span></span>

[<span data-ttu-id="1381c-198">Usar o Power BI para analisar dados do CQD para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1381c-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="1381c-199">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="1381c-199">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)