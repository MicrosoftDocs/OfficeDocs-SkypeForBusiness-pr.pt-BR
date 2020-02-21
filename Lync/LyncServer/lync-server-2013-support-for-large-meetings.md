---
title: Lync Server 2013 suporte para grandes reuniões
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
ms.openlocfilehash: cb551013a07cf16236e9fae5f8c3a3056bdb2f51
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="d9439-102">Suporte para grandes reuniões no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9439-102">Support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9439-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d9439-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d9439-104">O Lync Server 2013 pode dar suporte a reuniões com até 1000 participantes usando a conferência de áudio/vídeo (A/V), incluindo o compartilhamento de apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d9439-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="d9439-105">Esse suporte requer um pool dedicado configurado para dar suporte a grandes reuniões e gerenciados de forma a garantir a hospedagem de apenas uma única reunião de grande porte.</span><span class="sxs-lookup"><span data-stu-id="d9439-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="d9439-106">Esta seção descreve como dar suporte a grandes reuniões usando um pool dedicado do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9439-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="d9439-107">Descreve as considerações de escalabilidade e os requisitos de implementação de um pool dedicado, incluindo a topologia, o hardware, o software e os requisitos de configuração.</span><span class="sxs-lookup"><span data-stu-id="d9439-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="d9439-108">Ele também fornece um conjunto de recomendações de práticas recomendadas para o suporte a grandes reuniões, um resumo dos métodos de teste e resultados de testes de escalabilidade de servidor conduzidos pela equipe de engenharia do Lync Server e as respostas para perguntas frequentes sobre o suporte para grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="d9439-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d9439-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d9439-109">In This Section</span></span>

  - [<span data-ttu-id="d9439-110">Visão geral da escalabilidade de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9439-110">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="d9439-111">Suporte a reuniões grandes usando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9439-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="d9439-112">Perguntas frequentes de suporte para grandes reuniões do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9439-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

