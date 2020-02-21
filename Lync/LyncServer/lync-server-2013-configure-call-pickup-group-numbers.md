---
title: 'Lync Server 2013: configurar números de grupos de recebimento de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call pickup group numbers
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945631(v=OCS.15)
ms:contentKeyID: 51541479
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e380e5b857a59405d42e382d18d7470395a5f580
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="3598e-102">Configurar números de grupos de recebimento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3598e-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3598e-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="3598e-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="3598e-104">O recebimento de chamadas em grupo é baseado no aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="3598e-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="3598e-105">Ao implantar o recebimento de chamadas em grupo, você configura a tabela de órbita de estacionamento de chamada com intervalos de números de telefone designados como números de grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="3598e-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="3598e-106">Esses números de grupo são os números que os usuários discam para pegar chamadas que estejam tocando para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="3598e-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="3598e-107">Como números de órbita de estacionamento de chamada, os números de grupo de recebimento de chamada precisam ser extensões virtuais que não têm nenhum usuário ou telefone atribuído a eles.</span><span class="sxs-lookup"><span data-stu-id="3598e-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="3598e-108">Cada pool de front-ends onde você implanta o recebimento de chamadas em grupo pode ter um ou mais intervalos de números de grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="3598e-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="3598e-109">Os intervalos de números de grupo devem ser globalmente exclusivos na implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3598e-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3598e-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3598e-110">In This Section</span></span>

[<span data-ttu-id="3598e-111">Criar ou modificar um intervalo de números de recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3598e-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

