---
title: 'Lync Server 2013: configurar intervalos de números de recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbcbf05fbb73e2023b48bdb1f7e74ecdee6a36bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="9b8e9-102">Configurar intervalos de números de recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b8e9-102">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b8e9-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="9b8e9-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="9b8e9-104">O recebimento de chamadas em grupo é baseado no aplicativo parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="9b8e9-105">Ao implantar o recurso de recebimento de chamadas em grupo, configure a tabela órbita do estacionamento de chamada com intervalos de números de telefone designados como números de grupo de recebimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="9b8e9-106">Esses números do grupo são aqueles que os usuários discam para receber chamadas que estão tocando para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="9b8e9-107">Como os números da órbita de estacionamento de chamada, os números do grupo de recebimento de chamada precisam ser extensões virtuais, sem nenhum usuário ou telefone atribuído.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="9b8e9-108">Cada pool de front-ends onde você implanta o recebimento de chamadas em grupo pode ter um ou mais intervalos de números de grupo de recebimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="9b8e9-109">Os intervalos de números de grupo devem ser globalmente exclusivos na implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9b8e9-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9b8e9-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9b8e9-110">In This Section</span></span>

  - [<span data-ttu-id="9b8e9-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b8e9-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="9b8e9-112">Excluir um intervalo de números de retirada de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b8e9-112">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

