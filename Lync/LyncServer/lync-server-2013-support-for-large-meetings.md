---
title: 'Lync Server 2013: Suporte a reuniões grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for large meetings
ms:assetid: 8f0446d5-1ed9-4ea0-bb97-6c062a98a1eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205090(v=OCS.15)
ms:contentKeyID: 48184820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c98166b42f48e328809960279b9934b87670101b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="06b3a-102">Suporte a reuniões grandes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06b3a-102">Support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06b3a-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="06b3a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="06b3a-104">O Lync Server 2013 pode oferecer suporte a reuniões com até 1000 participantes usando uma conferência de áudio/vídeo (A/V), incluindo o compartilhamento de apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="06b3a-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="06b3a-105">Esse suporte exige um pool dedicado, configurado para suportar grandes reuniões e gerenciado de forma a garantir a hospedagem de apenas uma grande reunião por vez.</span><span class="sxs-lookup"><span data-stu-id="06b3a-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="06b3a-106">Esta seção descreve como dar suporte a reuniões grandes usando um pool dedicado do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06b3a-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="06b3a-107">Ele descreve as considerações sobre escalabilidade e os requisitos de implementação de um pool dedicado, incluindo requisitos de topologia, hardware, software e configuração.</span><span class="sxs-lookup"><span data-stu-id="06b3a-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="06b3a-108">Ele também fornece um conjunto de recomendações de práticas recomendadas para dar suporte a reuniões grandes, um resumo dos métodos de teste e os resultados dos testes de escalabilidade de servidor realizados pela equipe de engenharia do Lync Server e as respostas às perguntas frequentes sobre o suporte para reuniões grandes.</span><span class="sxs-lookup"><span data-stu-id="06b3a-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="06b3a-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="06b3a-109">In This Section</span></span>

  - [<span data-ttu-id="06b3a-110">Visão geral da escalabilidade de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06b3a-110">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="06b3a-111">Suporte a reuniões grandes usando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06b3a-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="06b3a-112">Perguntas frequentes sobre suporte a reuniões grandes do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06b3a-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

