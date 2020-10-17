---
title: 'Lync Server 2013: relatórios de diagnóstico de qualidade de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 058c12ed9f1b07df885e9e7b90f43780043cdf56
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500687"
---
# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="b7bd8-102">Relatórios de diagnóstico de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7bd8-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7bd8-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="b7bd8-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="b7bd8-104">Os Relatórios de Diagnóstico de Qualidade de Mídia oferecem informações sobre a qualidade de chamadas e informações sobre diagnóstico de solução de problemas para chamadas com falhas.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b7bd8-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b7bd8-105">In This Section</span></span>

  - <span data-ttu-id="b7bd8-106">[Relatório de Resumo de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-summary-report.md)     Fornece dados de qualidade geral para diferentes tipos de ponto de extremidade, incluindo chamadas ponto a ponto do Enterprise Voice, chamadas de conferência do Enterprise Voice e chamadas que dependem, pelo menos em parte, na PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="b7bd8-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="b7bd8-107">[Relatório de comparação de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)     Fornece uma comparação de valores de qualidade de chamada para diferentes tipos de chamadas de áudio (por exemplo, chamadas feitas por uma rede sem fio vs. chamadas feitas em uma conexão com fio).</span><span class="sxs-lookup"><span data-stu-id="b7bd8-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="b7bd8-108">[Relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md)     Lista os servidores que apresentaram mais problemas, com base nas medições dessas métricas de qualidade de chave como degradação, perda de pacotes e Tremulação.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="b7bd8-109">[Relatório de localização no Lync Server 2013](lync-server-2013-location-report.md)     Fornece uma lista de locais de rede e um resumo da qualidade de mídia das chamadas que ocorrem em cada local.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="b7bd8-110">Para esse relatório, os locais se baseiam em sub-redes IP.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="b7bd8-111">[Relatório de dispositivos no Lync Server 2013](lync-server-2013-device-report.md)     Fornece um resumo dos dispositivos usados para chamadas do Enterprise Voice e inclui a qualidade média de mídia das chamadas por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="b7bd8-112">[Relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md)     Fornece informações detalhadas sobre as chamadas telefônicas feitas ou recebidas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="b7bd8-113">[Relatório detalhado de chamadas no Lync Server 2013](lync-server-2013-call-detail-report.md)     Fornece informações detalhadas sobre as chamadas telefônicas feitas ou recebidas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="b7bd8-114">[Relatório de tendências de qualidade de mídia do servidor no Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)     Fornece uma maneira de comparar graficamente até 5 servidores em métricas de qualidade da experiência, como volume da chamada, porcentagem de chamada ruim, perda de pacotes e Tremulação.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="b7bd8-115">[O relatório de distribuição de métricas de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)     Fornece um gráfico que mostra os valores de distribuição para uma métrica de qualidade da experiência, como tremulação ou perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="b7bd8-116">[Relatório de tendências de local no Lync Server 2013](lync-server-2013-location-trend-report.md)     Fornece informações de tendência de qualidade de chamada para locais de rede.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

