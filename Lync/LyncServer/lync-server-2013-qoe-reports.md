---
title: 'Lync Server 2013: relatórios de QoE'
description: 'Lync Server 2013: relatórios de QoE.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55965d246b7f0ddd71eaeeec99d218eaf8819c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571397"
---
# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="fbc15-103">Relatórios de QoE no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbc15-103">QoE reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbc15-104">_**Última modificação do tópico:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="fbc15-104">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="fbc15-105">Relatórios de resumo/tendências de QoE</span><span class="sxs-lookup"><span data-stu-id="fbc15-105">QoE summary/trend reports</span></span>

<span data-ttu-id="fbc15-106">Os relatórios de resumo/tendências de QoE são úteis para encontrar os horários de pico de uso do dia e examinar a qualidade da mídia durante esses horários para ajudar a garantir que os recursos de rede da sua organização sejam suficientes.</span><span class="sxs-lookup"><span data-stu-id="fbc15-106">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="fbc15-107">Sua organização também pode usar os vários filtros disponíveis no relatório para isolar números de desempenho de determinados locais, tipos de dispositivos e clientes e servidores.</span><span class="sxs-lookup"><span data-stu-id="fbc15-107">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="fbc15-108">Relatórios de resumo/tendência de QoE consistem em:</span><span class="sxs-lookup"><span data-stu-id="fbc15-108">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="fbc15-109">Relatório de resumo/tendência UC-to-UC</span><span class="sxs-lookup"><span data-stu-id="fbc15-109">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="fbc15-110">Relatório de resumo/tendência PSTN</span><span class="sxs-lookup"><span data-stu-id="fbc15-110">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="fbc15-111">Relatório de Resumo de conferências/tendências</span><span class="sxs-lookup"><span data-stu-id="fbc15-111">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="fbc15-112">Relatórios de desempenho de QoE</span><span class="sxs-lookup"><span data-stu-id="fbc15-112">QoE performance reports</span></span>

<span data-ttu-id="fbc15-113">Relatórios de desempenho de QoE fornecem detalhes sobre os três relatórios que se concentram no desempenho de QoE de servidores de mediação, servidores de conferência A/V e locais de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="fbc15-113">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="fbc15-114">Relatório de desempenho do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="fbc15-114">Mediation server performance report</span></span>

<span data-ttu-id="fbc15-115">O relatório de desempenho do servidor de mediação lista as métricas obtidas por uma ou mais mediação durante o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="fbc15-115">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="fbc15-116">As métricas para o trecho do servidor de comunicações unificadas (UC) para o servidor de mediação e o trecho do servidor de mediação para gateway de cada chamada são relatados separadamente.</span><span class="sxs-lookup"><span data-stu-id="fbc15-116">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="fbc15-117">Use este relatório para comparar o volume e o desempenho dos vários servidores de mediação da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fbc15-117">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="fbc15-118">Para cada servidor de mediação (e para cada segmento de chamada), o relatório exibe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fbc15-118">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="fbc15-119">Número de chamadas</span><span class="sxs-lookup"><span data-stu-id="fbc15-119">Number of calls</span></span>

  - <span data-ttu-id="fbc15-120">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="fbc15-120">Packet Loss</span></span>

  - <span data-ttu-id="fbc15-121">Tempo de ida e volta</span><span class="sxs-lookup"><span data-stu-id="fbc15-121">Round Trip Time</span></span>

  - <span data-ttu-id="fbc15-122">Torção</span><span class="sxs-lookup"><span data-stu-id="fbc15-122">Jitter</span></span>

  - <span data-ttu-id="fbc15-123">Pontuação média de opinião da conversa (MOS)</span><span class="sxs-lookup"><span data-stu-id="fbc15-123">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="fbc15-124">MOS enviando</span><span class="sxs-lookup"><span data-stu-id="fbc15-124">Sending MOS</span></span>

  - <span data-ttu-id="fbc15-125">MOS ouvindo</span><span class="sxs-lookup"><span data-stu-id="fbc15-125">Listening MOS</span></span>

  - <span data-ttu-id="fbc15-126">MOS de rede</span><span class="sxs-lookup"><span data-stu-id="fbc15-126">Network MOS</span></span>

  - <span data-ttu-id="fbc15-127">Degradação de MOS de rede</span><span class="sxs-lookup"><span data-stu-id="fbc15-127">Network MOS Degradation</span></span>

  - <span data-ttu-id="fbc15-128">Retorno de eco</span><span class="sxs-lookup"><span data-stu-id="fbc15-128">Echo Return</span></span>

  - <span data-ttu-id="fbc15-129">Nível do sinal</span><span class="sxs-lookup"><span data-stu-id="fbc15-129">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="fbc15-130">Relatório de desempenho de servidor de conferência A/V</span><span class="sxs-lookup"><span data-stu-id="fbc15-130">A/V conferencing server performance report</span></span>

<span data-ttu-id="fbc15-131">O relatório de desempenho do servidor de conferência A/V fornece listas de métricas obtidas por um ou mais servidores de conferência A/V durante o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="fbc15-131">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="fbc15-132">Este relatório pode ser usado para comparar o volume e o desempenho dos vários servidores de conferência A/V da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fbc15-132">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="fbc15-133">Sua organização também pode isolar o relatório para mostrar apenas a experiência de tipos específicos de clientes, como clientes do Lync ou clientes PSTN.</span><span class="sxs-lookup"><span data-stu-id="fbc15-133">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="fbc15-134">Para cada servidor de conferência A/V, o relatório exibe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fbc15-134">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="fbc15-135">Número de conferências</span><span class="sxs-lookup"><span data-stu-id="fbc15-135">Number of conferences</span></span>

  - <span data-ttu-id="fbc15-136">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="fbc15-136">Packet Loss</span></span>

  - <span data-ttu-id="fbc15-137">Tempo de ida e volta</span><span class="sxs-lookup"><span data-stu-id="fbc15-137">Round Trip Time</span></span>

  - <span data-ttu-id="fbc15-138">Torção</span><span class="sxs-lookup"><span data-stu-id="fbc15-138">Jitter</span></span>

  - <span data-ttu-id="fbc15-139">Pontuação média de opinião da conversa (MOS)</span><span class="sxs-lookup"><span data-stu-id="fbc15-139">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="fbc15-140">MOS enviando</span><span class="sxs-lookup"><span data-stu-id="fbc15-140">Sending MOS</span></span>

  - <span data-ttu-id="fbc15-141">MOS ouvindo</span><span class="sxs-lookup"><span data-stu-id="fbc15-141">Listening MOS</span></span>

  - <span data-ttu-id="fbc15-142">MOS de rede</span><span class="sxs-lookup"><span data-stu-id="fbc15-142">Network MOS</span></span>

  - <span data-ttu-id="fbc15-143">Degradação de MOS de rede</span><span class="sxs-lookup"><span data-stu-id="fbc15-143">Network MOS Degradation</span></span>

  - <span data-ttu-id="fbc15-144">Retorno de eco</span><span class="sxs-lookup"><span data-stu-id="fbc15-144">Echo Return</span></span>

  - <span data-ttu-id="fbc15-145">Nível do sinal</span><span class="sxs-lookup"><span data-stu-id="fbc15-145">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="fbc15-146">Relatório de desempenho baseado em local</span><span class="sxs-lookup"><span data-stu-id="fbc15-146">Location-based performance report</span></span>

<span data-ttu-id="fbc15-147">O Location-Based relatório de desempenho fornece uma lista de locais de rede e para cada local mostra o número de chamadas em cada intervalo de qualidade predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fbc15-147">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="fbc15-148">O objetivo deste relatório é fornecer informações sobre a qualidade da mídia do grande volume de chamadas telefônicas da sua organização para vários locais, para que você possa identificar locais com desempenho ruim e ver as diferentes pontuações de qualidade de mídia nos diferentes locais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fbc15-148">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="fbc15-149">Ao exibir o relatório, diferentes tabelas de métricas aparecem — uma tabela para cada métrica que sua organização decide relatar.</span><span class="sxs-lookup"><span data-stu-id="fbc15-149">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="fbc15-150">Você pode escolher entre as seguintes métricas para este relatório:</span><span class="sxs-lookup"><span data-stu-id="fbc15-150">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="fbc15-151">Pontuação média de opinião da conversa (MOS)</span><span class="sxs-lookup"><span data-stu-id="fbc15-151">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="fbc15-152">MOS de rede</span><span class="sxs-lookup"><span data-stu-id="fbc15-152">Network MOS</span></span>

  - <span data-ttu-id="fbc15-153">Degradação de MOS de rede</span><span class="sxs-lookup"><span data-stu-id="fbc15-153">Network MOS Degradation</span></span>

  - <span data-ttu-id="fbc15-154">MOS enviando</span><span class="sxs-lookup"><span data-stu-id="fbc15-154">Sending MOS</span></span>

  - <span data-ttu-id="fbc15-155">MOS ouvindo</span><span class="sxs-lookup"><span data-stu-id="fbc15-155">Listening MOS</span></span>

  - <span data-ttu-id="fbc15-156">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="fbc15-156">Packet Loss</span></span>

  - <span data-ttu-id="fbc15-157">Torção</span><span class="sxs-lookup"><span data-stu-id="fbc15-157">Jitter</span></span>

  - <span data-ttu-id="fbc15-158">Latência</span><span class="sxs-lookup"><span data-stu-id="fbc15-158">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

