---
title: 'Lync Server 2013: cenários para o diretor'
description: 'Lync Server 2013: cenários para o diretor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for the Director
ms:assetid: d2cf384a-0860-4779-80ce-cba2543be322
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398908(v=OCS.15)
ms:contentKeyID: 48185419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45c611fbe680ba55fb148c08fed26d96a848507e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578997"
---
# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="387d7-103">Cenários para o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="387d7-103">Scenarios for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="387d7-104">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="387d7-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="387d7-105">Um diretor é um servidor que executa o software de comunicações do Microsoft Lync Server 2013 que pode autenticar solicitações de usuário, mas não hospeda contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="387d7-105">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="387d7-106">O diretor também hospeda serviços Web similares ao servidor front-end e autentica as solicitações de tíquete da Web e fornece outros serviços.</span><span class="sxs-lookup"><span data-stu-id="387d7-106">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="387d7-107">Se você implantar diretores, deverá publicar os serviços Web do diretor externamente por meio do proxy reverso, bem como os serviços Web do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="387d7-107">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="387d7-108">Os tópicos a seguir descrevem o processo de planejamento para as possíveis topologias do diretor.</span><span class="sxs-lookup"><span data-stu-id="387d7-108">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="387d7-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="387d7-109">In This Section</span></span>

  - [<span data-ttu-id="387d7-110">Visão geral do diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="387d7-110">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="387d7-111">Componentes necessários para o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="387d7-111">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="387d7-112">Requisitos de hardware e software para o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="387d7-112">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="387d7-113">Diretor único no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="387d7-113">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="387d7-114">Pool de diretores em escala no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="387d7-114">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="387d7-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="387d7-115">See Also</span></span>


[<span data-ttu-id="387d7-116">Topologias com suporte no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="387d7-116">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="387d7-117">Plataformas de hardware de servidor para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="387d7-117">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

