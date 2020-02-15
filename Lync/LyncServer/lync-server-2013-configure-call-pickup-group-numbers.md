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
ms.openlocfilehash: 42023f82240e99695678bc25f1f38b7a20234d37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="eebfe-102">Configurar números de grupos de recebimento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eebfe-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eebfe-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="eebfe-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="eebfe-104">O recebimento de chamadas em grupo é baseado no aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="eebfe-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="eebfe-105">Ao implantar o recebimento de chamadas em grupo, você configura a tabela de órbita de estacionamento de chamada com intervalos de números de telefone designados como números de grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="eebfe-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="eebfe-106">Esses números de grupo são os números que os usuários discam para pegar chamadas que estejam tocando para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="eebfe-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="eebfe-107">Como números de órbita de estacionamento de chamada, os números de grupo de recebimento de chamada precisam ser extensões virtuais que não têm nenhum usuário ou telefone atribuído a eles.</span><span class="sxs-lookup"><span data-stu-id="eebfe-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="eebfe-108">Cada pool de front-ends onde você implanta o recebimento de chamadas em grupo pode ter um ou mais intervalos de números de grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="eebfe-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="eebfe-109">Os intervalos de números de grupo devem ser globalmente exclusivos na implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eebfe-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eebfe-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="eebfe-110">In This Section</span></span>

[<span data-ttu-id="eebfe-111">Criar ou modificar um intervalo de números de recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eebfe-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

