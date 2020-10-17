---
title: 'Lync Server 2013: clientes com suporte para estacionamento de chamada'
description: 'Lync Server 2013: clientes com suporte para estacionamento de chamada.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a923f0e62c246a12b811628d578ab571f4f13e36
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543487"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="8f2ac-103">Clientes com suporte para estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f2ac-103">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f2ac-104">_**Última modificação do tópico:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="8f2ac-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="8f2ac-105">Esta seção identifica os clientes que podem ser usados para estacionar chamadas e os clientes que podem ser usados para recuperar chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8f2ac-105">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="8f2ac-106">Clientes com suporte para estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="8f2ac-106">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="8f2ac-107">As chamadas de qualquer IP, PBX (rede telefônica pública comutada), PSTN ou celular podem ser estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8f2ac-107">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f2ac-108">Somente as chamadas de áudio podem ser estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8f2ac-108">Only audio calls can be parked.</span></span> <span data-ttu-id="8f2ac-109">Mensagens instantâneas e conferências não podem ser estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8f2ac-109">Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="8f2ac-110">Os clientes a seguir podem usar o estacionamento de chamadas para estacionar chamadas:</span><span class="sxs-lookup"><span data-stu-id="8f2ac-110">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="8f2ac-111">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8f2ac-111">Lync 2013</span></span>

  - <span data-ttu-id="8f2ac-112">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8f2ac-112">Lync 2010</span></span>

  - <span data-ttu-id="8f2ac-113">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="8f2ac-113">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="8f2ac-114">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8f2ac-114">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f2ac-115">Telefones celulares não podem usar o estacionamento de chamadas para estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8f2ac-115">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="8f2ac-116">Clientes com suporte para recuperação de chamadas</span><span class="sxs-lookup"><span data-stu-id="8f2ac-116">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="8f2ac-117">Os intervalos de órbitas são configurados como blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído).</span><span class="sxs-lookup"><span data-stu-id="8f2ac-117">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="8f2ac-118">Quando você configura órbitas como extensões virtuais, telefones celulares e telefones PSTN não podem recuperar chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8f2ac-118">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="8f2ac-119">Os usuários federados não podem recuperar chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8f2ac-119">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="8f2ac-120">Os clientes a seguir podem recuperar chamadas estacionadas no estacionamento de chamada:</span><span class="sxs-lookup"><span data-stu-id="8f2ac-120">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="8f2ac-121">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8f2ac-121">Lync 2013</span></span>

  - <span data-ttu-id="8f2ac-122">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8f2ac-122">Lync 2010</span></span>

  - <span data-ttu-id="8f2ac-123">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="8f2ac-123">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="8f2ac-124">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8f2ac-124">Lync Phone Edition</span></span>

  - <span data-ttu-id="8f2ac-125">Telefones de área comum IP</span><span class="sxs-lookup"><span data-stu-id="8f2ac-125">IP common area phones</span></span>

  - <span data-ttu-id="8f2ac-126">Telefones não IP que estão conectados à infraestrutura do Lync Server 2013, incluindo telefones de área comum e telefones de PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="8f2ac-126">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

