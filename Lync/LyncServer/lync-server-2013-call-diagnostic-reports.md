---
title: 'Lync Server 2013: relatórios de diagnóstico de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46073c5540b0b4cd48f6c5a13c17d4a4d3f12a46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526328"
---
# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="633fd-102">Relatórios de diagnóstico de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="633fd-102">Call Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="633fd-103">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="633fd-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="633fd-104">Os Relatórios de Diagnóstico de Chamada oferecem informações de resumo e dados de diagnóstico para sessões ponto a ponto e de conferência com falhas.</span><span class="sxs-lookup"><span data-stu-id="633fd-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="633fd-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="633fd-105">In This Section</span></span>

  - <span data-ttu-id="633fd-106">[Relatório de Resumo de diagnóstico de chamadas no Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)     Fornece um resumo geral das sessões ponto a ponto com falha e sessões de conferência.</span><span class="sxs-lookup"><span data-stu-id="633fd-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="633fd-107">Sessões ponto a ponto são aquelas que envolvem somente dois participantes.</span><span class="sxs-lookup"><span data-stu-id="633fd-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="633fd-108">Sessões de conferência envolvem três ou mais participantes.</span><span class="sxs-lookup"><span data-stu-id="633fd-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="633fd-109">[Relatório de diagnóstico de atividade ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)     Fornece uma visão geral de tendência de sessões ponto a ponto com falha.</span><span class="sxs-lookup"><span data-stu-id="633fd-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="633fd-110">Uma sessão ponto a ponto envolve somente dois participantes.</span><span class="sxs-lookup"><span data-stu-id="633fd-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="633fd-111">[Relatório de diagnóstico de conferência no Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)     Fornece uma visão geral de tendência de sessões de conferência com falha e modos de exibição de tendência para cada modalidade de conferência.</span><span class="sxs-lookup"><span data-stu-id="633fd-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="633fd-112">Sessões de conferência envolvem no mínimo três participantes.</span><span class="sxs-lookup"><span data-stu-id="633fd-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="633fd-113">[Relatório de falhas principais no Lync Server 2013](lync-server-2013-top-failures-report.md)     Fornece uma lista das falhas mais frequentes e suas tendências ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="633fd-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="633fd-114">[Relatório de distribuição de falhas no Lync Server 2013](lync-server-2013-failure-distribution-report.md)     Fornece uma análise de sessões com falha.</span><span class="sxs-lookup"><span data-stu-id="633fd-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="633fd-115">[Relatório de lista de falhas no Lync Server 2013](lync-server-2013-failure-list-report.md)     Fornece informações detalhadas sobre os participantes individuais envolvidos em uma conferência com falha.</span><span class="sxs-lookup"><span data-stu-id="633fd-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="633fd-116">[Relatório de diagnóstico no Lync Server 2013](lync-server-2013-diagnostic-report.md)     Fornece informações de diagnóstico e solução de problemas (incluindo códigos de resposta SIP e cabeçalhos e IDs de diagnóstico) para sessões com falha.</span><span class="sxs-lookup"><span data-stu-id="633fd-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

