---
title: 'Lync Server 2013: planejamento e implantação de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d22ebee3227577edea9f937dddc510424d021dd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="52ba1-102">Planejamento e implantação de vídeo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ba1-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52ba1-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="52ba1-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="52ba1-104">O Lync Server 2013 apresenta os seguintes novos recursos de vídeo:</span><span class="sxs-lookup"><span data-stu-id="52ba1-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="52ba1-105">\*\*\*\*   Os usuários de vídeo HD podem experimentar resoluções até alta definição (HD) (ou seja, 1920 x 1080) em chamadas de duas partes e conferências com vários participantes.</span><span class="sxs-lookup"><span data-stu-id="52ba1-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="52ba1-106">**Modo de exibição**   de galeria em conferências de vídeo que têm mais de duas pessoas, os usuários podem ver vídeos de participantes na conferência.</span><span class="sxs-lookup"><span data-stu-id="52ba1-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="52ba1-107">Se a conferência possui mais de cinco participantes, o vídeo de apenas os participantes mais ativos aparecem na linha superior e uma foto aparece para os outros participantes.</span><span class="sxs-lookup"><span data-stu-id="52ba1-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="52ba1-108">**Vídeo h. 264**   o codec de vídeo h. 264 agora é o padrão para codificar vídeo nos clientes do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="52ba1-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="52ba1-109">O vídeo H.264 suporta um intervalo maior de resoluções e taxas de quadro e melhora a escalabilidade de vídeo.</span><span class="sxs-lookup"><span data-stu-id="52ba1-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52ba1-110">O Lync Server 2013 ainda oferece suporte ao codec VC1 para interoperabilidade com versões anteriores do Lync.</span><span class="sxs-lookup"><span data-stu-id="52ba1-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="52ba1-111">Para obter detalhes e informações detalhadas sobre o novo codec de vídeo, confira o artigo de blog de Jeff Schertz, "Interoperability de vídeo no <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>Lync 2013", em.</span><span class="sxs-lookup"><span data-stu-id="52ba1-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="52ba1-112">Esta seção descreve como gerenciar a largura de banda para o vídeo no Lync Server 2013 e como configurar os recursos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="52ba1-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="52ba1-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="52ba1-113">In This Section</span></span>

  - [<span data-ttu-id="52ba1-114">Configurando largura de banda de vídeo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ba1-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="52ba1-115">Configurando o modo de exibição de galeria no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ba1-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="52ba1-116">Configurando cenários de exemplo de vídeo para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ba1-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="52ba1-117">Considerações de interoperabilidade para conferência de vídeo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52ba1-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

