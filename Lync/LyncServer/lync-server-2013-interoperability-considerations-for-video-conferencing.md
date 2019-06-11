---
title: 'Lync Server 2013: considerações de interoperabilidade para videoconferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 880b2e41a1ea92b3d6da9cd29153695b474e88f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="0de31-102">Considerações de interoperabilidade para videoconferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0de31-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0de31-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0de31-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0de31-104">Esta seção descreve a experiência do usuário durante a fase de coexistência da migração, quando há interoperabilidade entre clientes herdados e um pool do Lync Server 2013 ou clientes do Lync Server 2013 e um pool herdado.</span><span class="sxs-lookup"><span data-stu-id="0de31-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="0de31-105">Pools do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0de31-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="0de31-106">Os usuários perceberão o seguinte comportamento quando um cliente herdado for usado em um pool do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0de31-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="0de31-107">Para chamadas de dois participantes, a resolução de vídeo é a mesma do pool herdado.</span><span class="sxs-lookup"><span data-stu-id="0de31-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="0de31-108">Para conferências com vários participantes, a resolução de vídeo e os recursos de videoconferência são iguais aos do pool herdado.</span><span class="sxs-lookup"><span data-stu-id="0de31-108">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool.</span></span> <span data-ttu-id="0de31-109">O modo de exibição de galeria e alta resolução não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0de31-109">Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="0de31-110">Pools herdados</span><span class="sxs-lookup"><span data-stu-id="0de31-110">Legacy Pools</span></span>

<span data-ttu-id="0de31-111">Os usuários perceberão o seguinte comportamento quando um cliente do Lync Server 2013 for usado em um pool herdado:</span><span class="sxs-lookup"><span data-stu-id="0de31-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="0de31-112">Para chamadas de dois participantes, os clientes do Lync Server 2013 podem usar novos recursos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="0de31-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="0de31-113">H. 264 estará disponível se ambos os participantes estiverem usando os clientes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0de31-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="0de31-114">O cliente do Lync Server 2013 usa o valor padrão para TotalReceiveVideoBitRateKb, uma vez que o servidor herdado não envia essas informações com o provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="0de31-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="0de31-115">Para conferências com vários participantes, a resolução de vídeo e os recursos de videoconferência são os mesmos que um cliente herdado no pool herdado.</span><span class="sxs-lookup"><span data-stu-id="0de31-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0de31-116">Quando um servidor herdado hospeda um cliente do Lync Server 2013, é possível configurar a largura de banda de videoconferência para que todos os usuários do pool recebam somente vídeo de baixa resolução, mas enviem vídeo de alta resolução.</span><span class="sxs-lookup"><span data-stu-id="0de31-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="0de31-117">Um exemplo disso é quando MaxVideoRateAllowed está definido como CIF-250K na configuração de mídia e VideoBitRateKb é definido como 2000 kbps na política de conferência.</span><span class="sxs-lookup"><span data-stu-id="0de31-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="0de31-118">Nesse caso, o efeito de alta resolução não é possível para os usuários do pool.</span><span class="sxs-lookup"><span data-stu-id="0de31-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="0de31-119">Como o MaxVideoRateAllowed não é mais usado para clientes do Lync Server 2013, ele não pode impedir que os clientes do Lync Server 2013 solicitem vídeo de alta resolução.</span><span class="sxs-lookup"><span data-stu-id="0de31-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="0de31-120">Em vez disso, defina VideoBitRateKb na política de conferência para todos os usuários no pool para o mesmo valor que MaxVideoRateAllowed (ou seja, CIF é definido como 250 kbps ou VGA está definido como 600 kbps ou HD é definido como 1500 kbps).</span><span class="sxs-lookup"><span data-stu-id="0de31-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

