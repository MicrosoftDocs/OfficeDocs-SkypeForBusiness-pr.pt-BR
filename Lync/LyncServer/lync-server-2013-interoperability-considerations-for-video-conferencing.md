---
title: 'Lync Server 2013: considerações de interoperabilidade para conferência de vídeo'
description: 'Lync Server 2013: considerações de interoperabilidade para conferência de vídeo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89675954ea4c4f188f50aab8fb2cb49494bcc247
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543927"
---
# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="2b4b1-103">Considerações de interoperabilidade para conferência de vídeo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b4b1-103">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b4b1-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2b4b1-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2b4b1-105">Esta seção descreve a experiência do usuário durante a fase de coexistência da migração, quando há interoperabilidade entre clientes herdados e um pool do Lync Server 2013 ou clientes do Lync Server 2013 e um pool herdado.</span><span class="sxs-lookup"><span data-stu-id="2b4b1-105">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="2b4b1-106">Pools do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b4b1-106">Lync Server 2013 Pools</span></span>

<span data-ttu-id="2b4b1-107">Os usuários perceberão o seguinte comportamento quando um cliente herdado for usado em um pool do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="2b4b1-107">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="2b4b1-108">Para chamadas de duas partes, a resolução de vídeo é a mesma da resolução do pool herdado.</span><span class="sxs-lookup"><span data-stu-id="2b4b1-108">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="2b4b1-p101">Para conferências com vários participantes, os recursos de resolução de vídeo e videoconferência são os mesmos dos presentes no pool herdado. O modo de exibição de galeria e a alta resolução não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2b4b1-p101">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool. Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="2b4b1-111">Pools herdados</span><span class="sxs-lookup"><span data-stu-id="2b4b1-111">Legacy Pools</span></span>

<span data-ttu-id="2b4b1-112">Os usuários experimentarão o seguinte comportamento quando um cliente do Lync Server 2013 for usado em um pool herdado:</span><span class="sxs-lookup"><span data-stu-id="2b4b1-112">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="2b4b1-113">Para chamadas de duas partes, os clientes do Lync Server 2013 podem usar os novos recursos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2b4b1-113">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="2b4b1-114">H. 264 estará disponível se ambos os participantes estiverem usando os clientes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b4b1-114">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="2b4b1-115">O cliente do Lync Server 2013 usa o valor padrão para TotalReceiveVideoBitRateKb, já que o servidor herdado não envia essas informações com o provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="2b4b1-115">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="2b4b1-116">Para conferências com vários participantes, os recursos de resolução de vídeo e videoconferência são os mesmos observados por um cliente herdado no pool herdado.</span><span class="sxs-lookup"><span data-stu-id="2b4b1-116">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b4b1-117">Quando um servidor herdado hospeda um cliente do Lync Server 2013, é possível configurar a largura de banda de audioconferência para que todos os usuários do pool recebam apenas vídeo de baixa resolução, mas enviem vídeo de alta resolução.</span><span class="sxs-lookup"><span data-stu-id="2b4b1-117">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="2b4b1-118">Um exemplo disso é quando MaxVideoRateAllowed é definido como CIF-250K na configuração de mídia e VideoBitRateKb é definido como 2.000 kbps na política de conferências.</span><span class="sxs-lookup"><span data-stu-id="2b4b1-118">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="2b4b1-119">O efeito líquido dessa situação é que uma alta resolução não é possível para os usuários no pool.</span><span class="sxs-lookup"><span data-stu-id="2b4b1-119">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="2b4b1-120">Como o MaxVideoRateAllowed não é mais usado para clientes do Lync Server 2013, ele não pode impedir que os clientes do Lync Server 2013 solicitem vídeo de alta resolução.</span><span class="sxs-lookup"><span data-stu-id="2b4b1-120">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="2b4b1-121">Em vez disso, defina VideoBitRateKb na política de conferências para todos os usuários do pool como o mesmo valor de MaxVideoRateAllowed (isto é, CIF é definido como 250 kbps, VGA é definido como 600 kbps ou HD é definido como 1.500 kbps).</span><span class="sxs-lookup"><span data-stu-id="2b4b1-121">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

