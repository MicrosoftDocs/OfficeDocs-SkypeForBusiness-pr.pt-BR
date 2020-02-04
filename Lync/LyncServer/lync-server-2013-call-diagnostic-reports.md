---
title: 'Lync Server 2013: relatórios de diagnóstico de chamadas'
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
ms.openlocfilehash: 41100a6cc41c38b3d32870d530f99d8c919a2e83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="af2ca-102">Relatórios de diagnóstico de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af2ca-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af2ca-103">_**Tópico da última modificação:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="af2ca-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="af2ca-104">Os Relatórios de Diagnóstico de Chamada oferecem informações de resumo e dados de diagnóstico para sessões ponto a ponto e de conferência com falhas.</span><span class="sxs-lookup"><span data-stu-id="af2ca-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="af2ca-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="af2ca-105">In This Section</span></span>

  - <span data-ttu-id="af2ca-106">[O relatório de resumo do diagnóstico de chamadas no Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   fornece um resumo geral de sessões ponto a ponto com falha e sessões de conferência.</span><span class="sxs-lookup"><span data-stu-id="af2ca-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="af2ca-107">Sessões ponto a ponto são aquelas que envolvem somente dois participantes.</span><span class="sxs-lookup"><span data-stu-id="af2ca-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="af2ca-108">Sessões de conferência envolvem três ou mais participantes.</span><span class="sxs-lookup"><span data-stu-id="af2ca-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="af2ca-109">[Atividade ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   fornece uma visão geral de tendência de sessões ponto a ponto com falha.</span><span class="sxs-lookup"><span data-stu-id="af2ca-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="af2ca-110">Uma sessão ponto a ponto envolve somente dois participantes.</span><span class="sxs-lookup"><span data-stu-id="af2ca-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="af2ca-111">[O relatório de diagnóstico de conferência no Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   fornece uma visão geral de tendências de sessões de conferência com falha e modos de exibição de tendência para cada modalidade de conferência.</span><span class="sxs-lookup"><span data-stu-id="af2ca-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="af2ca-112">Sessões de conferência envolvem no mínimo três participantes.</span><span class="sxs-lookup"><span data-stu-id="af2ca-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="af2ca-113">[O relatório de falhas principais no Lync Server 2013](lync-server-2013-top-failures-report.md)   fornece uma lista das falhas mais frequentes e suas tendências ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="af2ca-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="af2ca-114">[Relatório de distribuição de falha no Lync Server 2013](lync-server-2013-failure-distribution-report.md)   fornece uma análise de sessões com falha.</span><span class="sxs-lookup"><span data-stu-id="af2ca-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="af2ca-115">[O relatório lista de falhas no Lync Server 2013](lync-server-2013-failure-list-report.md)   fornece informações detalhadas sobre os participantes individuais envolvidos em uma conferência com falha.</span><span class="sxs-lookup"><span data-stu-id="af2ca-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="af2ca-116">[O relatório de diagnóstico no Lync Server 2013](lync-server-2013-diagnostic-report.md)   fornece informações de diagnóstico e de solução de problemas (incluindo códigos de resposta SIP e cabeçalhos e identificações de diagnóstico) para sessões com falha.</span><span class="sxs-lookup"><span data-stu-id="af2ca-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

