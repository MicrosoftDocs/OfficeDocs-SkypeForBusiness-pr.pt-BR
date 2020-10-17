---
title: 'Lync Server 2013: configurar Sign-In automáticas de cliente para usar o diretor'
description: 'Lync Server 2013: Configure cliente automático Sign-In para usar o diretor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9c45a1a677d3a30704d8dca1771ef865cef29ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546647"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="65844-103">Configurar o Sign-In automático do cliente para usar o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65844-103">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65844-104">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="65844-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="65844-105">Quando você implanta um Lync Server 2013, diretor ou um pool de diretores, recomendamos que você use o cliente automático Sign-In como prática recomendada.</span><span class="sxs-lookup"><span data-stu-id="65844-105">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="65844-106">Para obter detalhes sobre como configurar servidores DNS para entrada automática de cliente, consulte [DNS Requirements for Automatic Client Sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="65844-106">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="65844-107">Se você já implantou a Entrada Automática do Cliente, consulte as seções a seguir para configurá-la em seu(s) Diretor(es).</span><span class="sxs-lookup"><span data-stu-id="65844-107">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="65844-108">Instância de um único Diretor</span><span class="sxs-lookup"><span data-stu-id="65844-108">Single Director Instance</span></span>

<span data-ttu-id="65844-109">Se você já tiver o cliente Sign-In implantado e ele estiver apontando para um servidor front-end ou um pool de front-ends, será necessário alterar o registro SRV DNS para apontar para o diretor.</span><span class="sxs-lookup"><span data-stu-id="65844-109">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="65844-110">Pool de Diretor</span><span class="sxs-lookup"><span data-stu-id="65844-110">Director Pool</span></span>

<span data-ttu-id="65844-111">Se você já tiver o cliente Sign-In implantado e ele estiver apontando para um servidor front-end ou um pool de front-ends, será necessário alterar o registro SRV DNS para apontar para o pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="65844-111">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

