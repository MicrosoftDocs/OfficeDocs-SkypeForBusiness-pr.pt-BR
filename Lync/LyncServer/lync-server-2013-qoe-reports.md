---
title: 'Lync Server 2013: relatórios de QoE'
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
ms.openlocfilehash: 9eead17e9cd08267f941d80cb25460f4d456d896
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="3b61d-102">Relatórios de QoE no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b61d-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b61d-103">_**Tópico da última modificação:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="3b61d-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="3b61d-104">Relatórios de resumo/tendências de QoE</span><span class="sxs-lookup"><span data-stu-id="3b61d-104">QoE summary/trend reports</span></span>

<span data-ttu-id="3b61d-105">Os relatórios de resumo/tendências de QoE são úteis para encontrar os períodos de pico de uso do dia e examinar a qualidade da mídia durante esses horários para ajudar a garantir que os recursos de rede da sua organização sejam suficientes.</span><span class="sxs-lookup"><span data-stu-id="3b61d-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="3b61d-106">Sua organização também pode usar os vários filtros disponíveis no relatório para isolar números de desempenho de certos locais, tipos de cliente e dispositivos e servidores.</span><span class="sxs-lookup"><span data-stu-id="3b61d-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="3b61d-107">Relatórios de resumo/tendências de QoE consistem em:</span><span class="sxs-lookup"><span data-stu-id="3b61d-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="3b61d-108">Relatório de Resumo de UC para UC/tendências</span><span class="sxs-lookup"><span data-stu-id="3b61d-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="3b61d-109">Relatório de resumo/tendência PSTN</span><span class="sxs-lookup"><span data-stu-id="3b61d-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="3b61d-110">Relatório Resumo da Conferência/resumo de tendências</span><span class="sxs-lookup"><span data-stu-id="3b61d-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="3b61d-111">Relatórios de desempenho de QoE</span><span class="sxs-lookup"><span data-stu-id="3b61d-111">QoE performance reports</span></span>

<span data-ttu-id="3b61d-112">Relatórios de desempenho de QoE fornecem detalhes sobre os três relatórios que se concentram no desempenho do QoE de servidores de mediação a/V e em locais de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="3b61d-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="3b61d-113">Relatório de desempenho do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="3b61d-113">Mediation server performance report</span></span>

<span data-ttu-id="3b61d-114">O relatório de desempenho do servidor de mediação lista as métricas obtidas por uma ou mais mediação durante o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="3b61d-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="3b61d-115">As métricas do trecho do servidor de comunicação unificada (UC) para o servidor de mediação e o trecho do servidor de mediação para gateway de cada chamada são reportados separadamente.</span><span class="sxs-lookup"><span data-stu-id="3b61d-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="3b61d-116">Use esse relatório para comparar o volume e o desempenho dos vários servidores de mediação da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3b61d-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="3b61d-117">Para cada servidor de mediação (e para cada segmento de chamada), o relatório exibe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3b61d-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="3b61d-118">Número de chamadas</span><span class="sxs-lookup"><span data-stu-id="3b61d-118">Number of calls</span></span>

  - <span data-ttu-id="3b61d-119">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="3b61d-119">Packet Loss</span></span>

  - <span data-ttu-id="3b61d-120">Tempo de viagem de ida e volta</span><span class="sxs-lookup"><span data-stu-id="3b61d-120">Round Trip Time</span></span>

  - <span data-ttu-id="3b61d-121">Tremulação</span><span class="sxs-lookup"><span data-stu-id="3b61d-121">Jitter</span></span>

  - <span data-ttu-id="3b61d-122">Pontuação média de opinião de conversa (MOS)</span><span class="sxs-lookup"><span data-stu-id="3b61d-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="3b61d-123">Como enviar MOS</span><span class="sxs-lookup"><span data-stu-id="3b61d-123">Sending MOS</span></span>

  - <span data-ttu-id="3b61d-124">MOS ouvindo</span><span class="sxs-lookup"><span data-stu-id="3b61d-124">Listening MOS</span></span>

  - <span data-ttu-id="3b61d-125">MOS de rede</span><span class="sxs-lookup"><span data-stu-id="3b61d-125">Network MOS</span></span>

  - <span data-ttu-id="3b61d-126">Degradação de MOS de rede</span><span class="sxs-lookup"><span data-stu-id="3b61d-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="3b61d-127">Retorno de eco</span><span class="sxs-lookup"><span data-stu-id="3b61d-127">Echo Return</span></span>

  - <span data-ttu-id="3b61d-128">Nível do sinal</span><span class="sxs-lookup"><span data-stu-id="3b61d-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="3b61d-129">Relatório de desempenho do servidor de conferência A/V</span><span class="sxs-lookup"><span data-stu-id="3b61d-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="3b61d-130">O relatório de desempenho do servidor de conferência A/V fornece listas de métricas obtidas por um ou mais servidores de conferência A/V durante o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="3b61d-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="3b61d-131">Esse relatório pode ser usado para comparar o volume e o desempenho dos vários servidores de conferência A/V da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3b61d-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="3b61d-132">Sua organização também pode isolar o relatório para mostrar apenas a experiência de tipos específicos de cliente, como clientes do Lync ou clientes PSTN.</span><span class="sxs-lookup"><span data-stu-id="3b61d-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="3b61d-133">Para cada servidor de conferência A/V, o relatório exibe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3b61d-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="3b61d-134">Número de conferências</span><span class="sxs-lookup"><span data-stu-id="3b61d-134">Number of conferences</span></span>

  - <span data-ttu-id="3b61d-135">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="3b61d-135">Packet Loss</span></span>

  - <span data-ttu-id="3b61d-136">Tempo de viagem de ida e volta</span><span class="sxs-lookup"><span data-stu-id="3b61d-136">Round Trip Time</span></span>

  - <span data-ttu-id="3b61d-137">Tremulação</span><span class="sxs-lookup"><span data-stu-id="3b61d-137">Jitter</span></span>

  - <span data-ttu-id="3b61d-138">Pontuação média de opinião de conversa (MOS)</span><span class="sxs-lookup"><span data-stu-id="3b61d-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="3b61d-139">Como enviar MOS</span><span class="sxs-lookup"><span data-stu-id="3b61d-139">Sending MOS</span></span>

  - <span data-ttu-id="3b61d-140">MOS ouvindo</span><span class="sxs-lookup"><span data-stu-id="3b61d-140">Listening MOS</span></span>

  - <span data-ttu-id="3b61d-141">MOS de rede</span><span class="sxs-lookup"><span data-stu-id="3b61d-141">Network MOS</span></span>

  - <span data-ttu-id="3b61d-142">Degradação de MOS de rede</span><span class="sxs-lookup"><span data-stu-id="3b61d-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="3b61d-143">Retorno de eco</span><span class="sxs-lookup"><span data-stu-id="3b61d-143">Echo Return</span></span>

  - <span data-ttu-id="3b61d-144">Nível do sinal</span><span class="sxs-lookup"><span data-stu-id="3b61d-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="3b61d-145">Relatório de desempenho baseado em local</span><span class="sxs-lookup"><span data-stu-id="3b61d-145">Location-based performance report</span></span>

<span data-ttu-id="3b61d-146">O relatório de desempenho baseado em local fornece uma lista de locais de rede e para cada local mostra o número de chamadas em cada intervalo predeterminado de qualidade.</span><span class="sxs-lookup"><span data-stu-id="3b61d-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="3b61d-147">O objetivo deste relatório é fornecer uma visão geral da qualidade da mídia do maior volume de chamadas telefônicas da sua organização para vários locais, de modo que você possa identificar locais deficientes e ver as diferentes classificações de qualidade da mídia na sua organização locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="3b61d-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="3b61d-148">Ao exibir o relatório, diferentes tabelas de métricas são exibidas — uma tabela para cada métrica à qual sua organização decide se reportar.</span><span class="sxs-lookup"><span data-stu-id="3b61d-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="3b61d-149">Você pode escolher entre as seguintes métricas deste relatório:</span><span class="sxs-lookup"><span data-stu-id="3b61d-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="3b61d-150">Pontuação média de opinião de conversa (MOS)</span><span class="sxs-lookup"><span data-stu-id="3b61d-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="3b61d-151">MOS de rede</span><span class="sxs-lookup"><span data-stu-id="3b61d-151">Network MOS</span></span>

  - <span data-ttu-id="3b61d-152">Degradação de MOS de rede</span><span class="sxs-lookup"><span data-stu-id="3b61d-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="3b61d-153">Como enviar MOS</span><span class="sxs-lookup"><span data-stu-id="3b61d-153">Sending MOS</span></span>

  - <span data-ttu-id="3b61d-154">MOS ouvindo</span><span class="sxs-lookup"><span data-stu-id="3b61d-154">Listening MOS</span></span>

  - <span data-ttu-id="3b61d-155">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="3b61d-155">Packet Loss</span></span>

  - <span data-ttu-id="3b61d-156">Tremulação</span><span class="sxs-lookup"><span data-stu-id="3b61d-156">Jitter</span></span>

  - <span data-ttu-id="3b61d-157">Latência</span><span class="sxs-lookup"><span data-stu-id="3b61d-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

