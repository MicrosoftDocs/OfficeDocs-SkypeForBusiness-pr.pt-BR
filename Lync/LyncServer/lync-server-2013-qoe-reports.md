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
ms.openlocfilehash: 958c67b1b10b25e44805d2582ffe2e9fab575568
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="44a6b-102">Relatórios de QoE no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44a6b-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44a6b-103">_**Última modificação do tópico:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="44a6b-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="44a6b-104">Relatórios de resumo/tendências de QoE</span><span class="sxs-lookup"><span data-stu-id="44a6b-104">QoE summary/trend reports</span></span>

<span data-ttu-id="44a6b-105">Os relatórios de resumo/tendências de QoE são úteis para encontrar os horários de pico de uso do dia e examinar a qualidade da mídia durante esses horários para ajudar a garantir que os recursos de rede da sua organização sejam suficientes.</span><span class="sxs-lookup"><span data-stu-id="44a6b-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="44a6b-106">Sua organização também pode usar os vários filtros disponíveis no relatório para isolar números de desempenho de determinados locais, tipos de dispositivos e clientes e servidores.</span><span class="sxs-lookup"><span data-stu-id="44a6b-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="44a6b-107">Relatórios de resumo/tendência de QoE consistem em:</span><span class="sxs-lookup"><span data-stu-id="44a6b-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="44a6b-108">Relatório de resumo/tendência UC-to-UC</span><span class="sxs-lookup"><span data-stu-id="44a6b-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="44a6b-109">Relatório de resumo/tendência PSTN</span><span class="sxs-lookup"><span data-stu-id="44a6b-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="44a6b-110">Relatório de Resumo de conferências/tendências</span><span class="sxs-lookup"><span data-stu-id="44a6b-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="44a6b-111">Relatórios de desempenho de QoE</span><span class="sxs-lookup"><span data-stu-id="44a6b-111">QoE performance reports</span></span>

<span data-ttu-id="44a6b-112">Relatórios de desempenho de QoE fornecem detalhes sobre os três relatórios que se concentram no desempenho de QoE de servidores de mediação, servidores de conferência A/V e locais de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="44a6b-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="44a6b-113">Relatório de desempenho do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="44a6b-113">Mediation server performance report</span></span>

<span data-ttu-id="44a6b-114">O relatório de desempenho do servidor de mediação lista as métricas obtidas por uma ou mais mediação durante o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="44a6b-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="44a6b-115">As métricas para o trecho do servidor de comunicações unificadas (UC) para o servidor de mediação e o trecho do servidor de mediação para gateway de cada chamada são relatados separadamente.</span><span class="sxs-lookup"><span data-stu-id="44a6b-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="44a6b-116">Use este relatório para comparar o volume e o desempenho dos vários servidores de mediação da sua organização.</span><span class="sxs-lookup"><span data-stu-id="44a6b-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="44a6b-117">Para cada servidor de mediação (e para cada segmento de chamada), o relatório exibe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="44a6b-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="44a6b-118">Número de chamadas</span><span class="sxs-lookup"><span data-stu-id="44a6b-118">Number of calls</span></span>

  - <span data-ttu-id="44a6b-119">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="44a6b-119">Packet Loss</span></span>

  - <span data-ttu-id="44a6b-120">Tempo de ida e volta</span><span class="sxs-lookup"><span data-stu-id="44a6b-120">Round Trip Time</span></span>

  - <span data-ttu-id="44a6b-121">Torção</span><span class="sxs-lookup"><span data-stu-id="44a6b-121">Jitter</span></span>

  - <span data-ttu-id="44a6b-122">Pontuação média de opinião da conversa (MOS)</span><span class="sxs-lookup"><span data-stu-id="44a6b-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="44a6b-123">MOS enviando</span><span class="sxs-lookup"><span data-stu-id="44a6b-123">Sending MOS</span></span>

  - <span data-ttu-id="44a6b-124">MOS ouvindo</span><span class="sxs-lookup"><span data-stu-id="44a6b-124">Listening MOS</span></span>

  - <span data-ttu-id="44a6b-125">MOS de rede</span><span class="sxs-lookup"><span data-stu-id="44a6b-125">Network MOS</span></span>

  - <span data-ttu-id="44a6b-126">Degradação de MOS de rede</span><span class="sxs-lookup"><span data-stu-id="44a6b-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="44a6b-127">Retorno de eco</span><span class="sxs-lookup"><span data-stu-id="44a6b-127">Echo Return</span></span>

  - <span data-ttu-id="44a6b-128">Nível do sinal</span><span class="sxs-lookup"><span data-stu-id="44a6b-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="44a6b-129">Relatório de desempenho de servidor de conferência A/V</span><span class="sxs-lookup"><span data-stu-id="44a6b-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="44a6b-130">O relatório de desempenho do servidor de conferência A/V fornece listas de métricas obtidas por um ou mais servidores de conferência A/V durante o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="44a6b-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="44a6b-131">Este relatório pode ser usado para comparar o volume e o desempenho dos vários servidores de conferência A/V da sua organização.</span><span class="sxs-lookup"><span data-stu-id="44a6b-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="44a6b-132">Sua organização também pode isolar o relatório para mostrar apenas a experiência de tipos específicos de clientes, como clientes do Lync ou clientes PSTN.</span><span class="sxs-lookup"><span data-stu-id="44a6b-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="44a6b-133">Para cada servidor de conferência A/V, o relatório exibe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="44a6b-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="44a6b-134">Número de conferências</span><span class="sxs-lookup"><span data-stu-id="44a6b-134">Number of conferences</span></span>

  - <span data-ttu-id="44a6b-135">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="44a6b-135">Packet Loss</span></span>

  - <span data-ttu-id="44a6b-136">Tempo de ida e volta</span><span class="sxs-lookup"><span data-stu-id="44a6b-136">Round Trip Time</span></span>

  - <span data-ttu-id="44a6b-137">Torção</span><span class="sxs-lookup"><span data-stu-id="44a6b-137">Jitter</span></span>

  - <span data-ttu-id="44a6b-138">Pontuação média de opinião da conversa (MOS)</span><span class="sxs-lookup"><span data-stu-id="44a6b-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="44a6b-139">MOS enviando</span><span class="sxs-lookup"><span data-stu-id="44a6b-139">Sending MOS</span></span>

  - <span data-ttu-id="44a6b-140">MOS ouvindo</span><span class="sxs-lookup"><span data-stu-id="44a6b-140">Listening MOS</span></span>

  - <span data-ttu-id="44a6b-141">MOS de rede</span><span class="sxs-lookup"><span data-stu-id="44a6b-141">Network MOS</span></span>

  - <span data-ttu-id="44a6b-142">Degradação de MOS de rede</span><span class="sxs-lookup"><span data-stu-id="44a6b-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="44a6b-143">Retorno de eco</span><span class="sxs-lookup"><span data-stu-id="44a6b-143">Echo Return</span></span>

  - <span data-ttu-id="44a6b-144">Nível do sinal</span><span class="sxs-lookup"><span data-stu-id="44a6b-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="44a6b-145">Relatório de desempenho baseado em local</span><span class="sxs-lookup"><span data-stu-id="44a6b-145">Location-based performance report</span></span>

<span data-ttu-id="44a6b-146">O relatório de desempenho baseado em local fornece uma lista de locais de rede e para cada local mostra o número de chamadas em cada intervalo de qualidade predefinido.</span><span class="sxs-lookup"><span data-stu-id="44a6b-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="44a6b-147">O objetivo deste relatório é fornecer informações sobre a qualidade da mídia do grande volume de chamadas telefônicas da sua organização para vários locais, para que você possa identificar locais com desempenho ruim e ver as diferentes notas de qualidade de mídia na sua organização locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="44a6b-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="44a6b-148">Ao exibir o relatório, diferentes tabelas de métricas aparecem — uma tabela para cada métrica que sua organização decide relatar.</span><span class="sxs-lookup"><span data-stu-id="44a6b-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="44a6b-149">Você pode escolher entre as seguintes métricas para este relatório:</span><span class="sxs-lookup"><span data-stu-id="44a6b-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="44a6b-150">Pontuação média de opinião da conversa (MOS)</span><span class="sxs-lookup"><span data-stu-id="44a6b-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="44a6b-151">MOS de rede</span><span class="sxs-lookup"><span data-stu-id="44a6b-151">Network MOS</span></span>

  - <span data-ttu-id="44a6b-152">Degradação de MOS de rede</span><span class="sxs-lookup"><span data-stu-id="44a6b-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="44a6b-153">MOS enviando</span><span class="sxs-lookup"><span data-stu-id="44a6b-153">Sending MOS</span></span>

  - <span data-ttu-id="44a6b-154">MOS ouvindo</span><span class="sxs-lookup"><span data-stu-id="44a6b-154">Listening MOS</span></span>

  - <span data-ttu-id="44a6b-155">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="44a6b-155">Packet Loss</span></span>

  - <span data-ttu-id="44a6b-156">Torção</span><span class="sxs-lookup"><span data-stu-id="44a6b-156">Jitter</span></span>

  - <span data-ttu-id="44a6b-157">Latênci</span><span class="sxs-lookup"><span data-stu-id="44a6b-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

