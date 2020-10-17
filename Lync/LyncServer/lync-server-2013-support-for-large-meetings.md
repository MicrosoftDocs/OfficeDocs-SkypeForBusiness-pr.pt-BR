---
title: Lync Server 2013 suporte para grandes reuniões
description: Lync Server 2013 suporte para grandes reuniões.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for large meetings
ms:assetid: 8f0446d5-1ed9-4ea0-bb97-6c062a98a1eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205090(v=OCS.15)
ms:contentKeyID: 48184820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb37cbfb95e36b9a07604eb4fbbc548e4d7ce9a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546257"
---
# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="63763-103">Suporte para grandes reuniões no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63763-103">Support for large meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63763-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="63763-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="63763-105">O Lync Server 2013 pode dar suporte a reuniões com até 1000 participantes usando a conferência de áudio/vídeo (A/V), incluindo o compartilhamento de apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="63763-105">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="63763-106">Esse suporte requer um pool dedicado configurado para dar suporte a grandes reuniões e gerenciados de forma a garantir a hospedagem de apenas uma única reunião de grande porte.</span><span class="sxs-lookup"><span data-stu-id="63763-106">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="63763-107">Esta seção descreve como dar suporte a grandes reuniões usando um pool dedicado do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63763-107">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="63763-108">Descreve as considerações de escalabilidade e os requisitos de implementação de um pool dedicado, incluindo a topologia, o hardware, o software e os requisitos de configuração.</span><span class="sxs-lookup"><span data-stu-id="63763-108">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="63763-109">Ele também fornece um conjunto de recomendações de práticas recomendadas para o suporte a grandes reuniões, um resumo dos métodos de teste e resultados de testes de escalabilidade de servidor conduzidos pela equipe de engenharia do Lync Server e as respostas para perguntas frequentes sobre o suporte a grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="63763-109">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="63763-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="63763-110">In This Section</span></span>

  - [<span data-ttu-id="63763-111">Visão geral da escalabilidade de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63763-111">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="63763-112">Suporte a reuniões grandes usando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63763-112">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="63763-113">Perguntas frequentes de suporte para grandes reuniões do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63763-113">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

