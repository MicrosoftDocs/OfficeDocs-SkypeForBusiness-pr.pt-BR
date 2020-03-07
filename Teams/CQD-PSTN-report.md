---
title: Usando o relatório de roteamento direto do CQD PSTN
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
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
description: Use o relatório de roteamento direto PSTN do CQD para monitorar e solucionar problemas de chamadas PSTN no Microsoft Teams.
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559358"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="87357-103">Usando o relatório de roteamento direto do CQD PSTN</span><span class="sxs-lookup"><span data-stu-id="87357-103">Using the CQD PSTN Direct Routing Report</span></span>

<span data-ttu-id="87357-104">Novidades de março de 2020, adicionamos um relatório de roteamento direto de PSTN CQD a nossos [modelos de consulta para download do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="87357-104">New in March 2020, we've added a CQD PSTN Direct Routing Report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="87357-105">O CQD PSTN Direct Routing Report ajuda os clientes a entender os padrões de uso e a qualidade de suas informações de monitoração de serviços PSTN sobre seu SBC, o serviço de telefonia, os parâmetros de rede e os detalhes da taxa de eficácia da rede e o uso da atender.</span><span class="sxs-lookup"><span data-stu-id="87357-105">The CQD PSTN Direct Routing Report helps customers to understand the usage patterns and quality of their PSTN services monitor information about your SBC, the telephony service, the network parameters, and Network Effectiveness Ratio details and usage of the service.</span></span> <span data-ttu-id="87357-106">Essas informações podem ajudá-lo a identificar problemas, incluindo o motivo para as chamadas descartadas.</span><span class="sxs-lookup"><span data-stu-id="87357-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="87357-107">Por exemplo, você poderá saber quando o volume será eliminado, quantas chamadas serão afetadas por qual motivo.</span><span class="sxs-lookup"><span data-stu-id="87357-107">For example, you will be able to know when volume drops, how many calls get affected by what reason.</span></span>

<span data-ttu-id="87357-108">O relatório de roteamento direto PSTN CQD tem quatro seções:</span><span class="sxs-lookup"><span data-stu-id="87357-108">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="87357-109">Visão geral da PSTN</span><span class="sxs-lookup"><span data-stu-id="87357-109">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="87357-110">Detalhes do serviço</span><span class="sxs-lookup"><span data-stu-id="87357-110">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="87357-111">Taxa de eficácia da rede</span><span class="sxs-lookup"><span data-stu-id="87357-111">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="87357-112">Parâmetros de rede</span><span class="sxs-lookup"><span data-stu-id="87357-112">Network Parameters</span></span>](#network-parameters)

## <a name="pstn-overview"></a><span data-ttu-id="87357-113">Visão geral da PSTN</span><span class="sxs-lookup"><span data-stu-id="87357-113">PSTN Overview</span></span>

<span data-ttu-id="87357-114">O CQD PSTN Direct Routing Report fornece as informações a seguir relacionadas à integridade geral do serviço dos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="87357-114">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="87357-115">![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="87357-115">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="87357-116">Por exemplo, se você estiver interessado no uso geral e na integridade de todas as chamadas recebidas por meio do SBC abc.bca.adatum.biz conosco como o país interno:</span><span class="sxs-lookup"><span data-stu-id="87357-116">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="87357-117">**Chame para fora**</span><span class="sxs-lookup"><span data-stu-id="87357-117">**Call Out**</span></span> | <span data-ttu-id="87357-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="87357-118">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="87357-119">1</span><span class="sxs-lookup"><span data-stu-id="87357-119">1</span></span>            | <span data-ttu-id="87357-120">Você pode usar os filtros na parte superior para fazer drill down e selecionar ByotIn como tipo de chamada, abc.bca.contoso.com como controlador de placa de sessão e EUA como país interno.</span><span class="sxs-lookup"><span data-stu-id="87357-120">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="87357-121">2</span><span class="sxs-lookup"><span data-stu-id="87357-121">2</span></span>            | <span data-ttu-id="87357-122">Tendência de uso dos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="87357-122">Usage trend for the past 180 days.</span></span> <span data-ttu-id="87357-123">Você pode encontrar o relatório de detalhes de uso na página de detalhes do serviço.</span><span class="sxs-lookup"><span data-stu-id="87357-123">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="87357-124">3</span><span class="sxs-lookup"><span data-stu-id="87357-124">3</span></span>            | <span data-ttu-id="87357-125">Atraso de discagem, latência, tremulação e tendência de perda de pacote nos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="87357-125">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="87357-126">Você pode encontrar um relatório detalhado na página parâmetros de rede.</span><span class="sxs-lookup"><span data-stu-id="87357-126">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="87357-127">4</span><span class="sxs-lookup"><span data-stu-id="87357-127">4</span></span>            | <span data-ttu-id="87357-128">Chamada simultânea e tendência de usuário ativo diário para os últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="87357-128">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="87357-129">Este gráfico pode ajudá-lo a entender o volume máximo do serviço.</span><span class="sxs-lookup"><span data-stu-id="87357-129">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="87357-130">5</span><span class="sxs-lookup"><span data-stu-id="87357-130">5</span></span>            | <span data-ttu-id="87357-131">Melhor motivo de término de chamada afetado qualidade do serviço dos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="87357-131">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="87357-132">Você pode encontrar detalhes de integridade do serviço na página de índice efetivo de rede (NER).</span><span class="sxs-lookup"><span data-stu-id="87357-132">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="87357-133">Detalhes do serviço</span><span class="sxs-lookup"><span data-stu-id="87357-133">Service Details</span></span>

<span data-ttu-id="87357-134">Esta página fornece as tendências de uso de serviço por dia e a divisão de comentários do usuário por meio do meio geográfico.</span><span class="sxs-lookup"><span data-stu-id="87357-134">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="87357-135">**Total de chamadas de tentativa –** Total de chamadas de tentativa nesse intervalo de tempo, incluindo tanto êxito como chamadas com falha</span><span class="sxs-lookup"><span data-stu-id="87357-135">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="87357-136">**Total de chamadas conectadas-** Total de chamadas conectadas nesse intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="87357-136">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="87357-137">**Total de minutos –** Uso total de minutos nesse intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="87357-137">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="87357-138">**Usuários ativos diariamente (DAU) –** Contagem de usuários ativos diários que fizeram pelo menos uma chamada conectada nesse dia</span><span class="sxs-lookup"><span data-stu-id="87357-138">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="87357-139">**Chamadas simultâneas –** Máximo de chamadas ativas simultâneas em um minuto</span><span class="sxs-lookup"><span data-stu-id="87357-139">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="87357-140">**Comentários do usuário –** A pontuação "classificar minha chamada" vem do usuário.</span><span class="sxs-lookup"><span data-stu-id="87357-140">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="87357-141">3-5 é considerado uma boa chamada.</span><span class="sxs-lookup"><span data-stu-id="87357-141">3-5 is considered as a good call.</span></span> <span data-ttu-id="87357-142">1-2 é considerado como uma chamada incorreta.</span><span class="sxs-lookup"><span data-stu-id="87357-142">1-2 is considered as a bad call.</span></span>

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report2.png)

<span data-ttu-id="87357-144">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="87357-144">For example:</span></span>

1.  <span data-ttu-id="87357-145">Se você vir as quedas médias de duração da chamada para 0 no 02/14/2020, você pode primeiro verificar se o volume da chamada está normal e ver se há uma grande discrepância entre o total de chamadas do Connect e as chamadas de tentativas totais.</span><span class="sxs-lookup"><span data-stu-id="87357-145">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="87357-146">Em seguida, acesse a página de razão da eficácia da rede para investir em motivos de falha na chamada.</span><span class="sxs-lookup"><span data-stu-id="87357-146">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="87357-147">Se vir o aumento dos pontos vermelhos no mapa de comentários do usuário, você poderá acessar a página de índice de eficácia da rede e o parâmetro de rede para ver se há anomalias e se você pode disparar um bilhete usando o MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="87357-147">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="87357-148">Taxa de eficácia da rede</span><span class="sxs-lookup"><span data-stu-id="87357-148">Network Effectiveness Ratio</span></span>

<span data-ttu-id="87357-149">Esta é a mesma métrica que aparece no painel de integridade geral.</span><span class="sxs-lookup"><span data-stu-id="87357-149">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="87357-150">Você pode verificar o número de NER por hora com os detalhes das chamadas afetadas para as direções da chamada (de entrada/saída) na taxa de eficácia horária da rede e no gráfico de motivo de término da chamada abaixo.</span><span class="sxs-lookup"><span data-stu-id="87357-150">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="87357-151">**Ner** – a capacidade (%) de uma rede para entregar chamadas medindo o número de chamadas enviadas versus o número de chamadas entregues a um destinatário.</span><span class="sxs-lookup"><span data-stu-id="87357-151">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="87357-152">**Código de resposta SIP**-um código de resposta de inteiro de três dígitos mostra o status da chamada.</span><span class="sxs-lookup"><span data-stu-id="87357-152">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="87357-153">**Código de resposta da Microsoft**-um código de resposta enviado do componente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="87357-153">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="87357-154">**Descrição** – a fase de motivo correspondente ao código de resposta SIP e ao código de resposta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="87357-154">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="87357-155">**Número de chamadas afetadas** – o número total de chamadas que você tem afetado durante o intervalo de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="87357-155">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="87357-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="87357-157">For example:</span></span>

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report4.png)

<span data-ttu-id="87357-159">Se o NER diário tiver um DIP no 02/05/2020, você poderá clicar na data e outros gráficos serão ampliados para essa data específica.</span><span class="sxs-lookup"><span data-stu-id="87357-159">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report5.png)

<span data-ttu-id="87357-161">Na NER boa porcentagem de tendência horária, você pode encontrar o DIP em torno de 21:00.</span><span class="sxs-lookup"><span data-stu-id="87357-161">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="87357-162">Em seguida, clique novamente para aplicar zoom à hora 21 e verificar detalhes de chamadas afetadas para ver quantas chamadas falharam nessa hora e quais são os motivos de término da chamada.</span><span class="sxs-lookup"><span data-stu-id="87357-162">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="87357-163">Você pode começar com a solução de problemas do SBC em qualquer problema de SBC ou relatório para o serviço de suporte se o problema não estiver relacionado ao SBC.</span><span class="sxs-lookup"><span data-stu-id="87357-163">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="87357-164">Parâmetros de rede</span><span class="sxs-lookup"><span data-stu-id="87357-164">Network Parameters</span></span>

<span data-ttu-id="87357-165">Todos os parâmetros de rede são medidos da interface de roteamento direto para o controlador de borda de sessão.</span><span class="sxs-lookup"><span data-stu-id="87357-165">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="87357-166">Para obter informações sobre os valores recomendados, consulte [preparar a rede da sua organização para o Microsoft Teams](prepare-network.md)e verificar os valores recomendados de borda do cliente para o Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="87357-166">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="87357-167">**Tremulação** – é a medida de milissegundos da variação no tempo de atraso de propagação de rede calculado entre dois pontos de extremidade usando RTCP (o protocolo de controle RTP).</span><span class="sxs-lookup"><span data-stu-id="87357-167">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="87357-168">**Perda de pacotes** – é uma medida do pacote que falhou ao chegar; Ele é calculado entre dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="87357-168">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="87357-169">**Latência** -(também conhecido como tempo de viagem de ida e volta) é o período de tempo que leva para o envio de um sinal mais o tempo necessário para que a confirmação daquele sinal seja recebida.</span><span class="sxs-lookup"><span data-stu-id="87357-169">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="87357-170">Esse atraso de tempo consiste nos tempos de propagação entre os dois pontos de um sinal.</span><span class="sxs-lookup"><span data-stu-id="87357-170">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report6.png)

<span data-ttu-id="87357-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="87357-172">For example:</span></span>

<span data-ttu-id="87357-173">Se você vir um pico em qualquer um dos quatro gráficos (latência, tremulação, taxa de perda de pacote, atraso de discagem automática) para uma data específica, por exemplo, latência em 02/14/2020, clique no ponto de data.</span><span class="sxs-lookup"><span data-stu-id="87357-173">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="87357-174">O gráfico de tendências horárias na parte inferior será atualizado para mostrar o número por hora.</span><span class="sxs-lookup"><span data-stu-id="87357-174">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="87357-175">Você pode verificar o SBCs ou disparar um bilhete com o MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="87357-175">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="87357-177">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="87357-177">Related topics</span></span>

[<span data-ttu-id="87357-178">Usar o Power BI para analisar dados do CQD para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="87357-178">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)