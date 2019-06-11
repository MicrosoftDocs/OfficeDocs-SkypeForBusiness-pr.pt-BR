---
title: 'Lync Server 2013: verificar regras de normalização para estacionamento de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114c7e035d96217f8cf41e88a87ccfd490fe5754
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="d56eb-102">Verificar as regras de normalização para o parque de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d56eb-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d56eb-103">_**Tópico da última modificação:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="d56eb-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="d56eb-104">As órbitas do estacionamento de chamada não devem ser normalizadas.</span><span class="sxs-lookup"><span data-stu-id="d56eb-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="d56eb-105">Verifique seus planos de discagem para garantir que seus números de órbita não estão normalizados.</span><span class="sxs-lookup"><span data-stu-id="d56eb-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="d56eb-106">Se você deve criar uma regra de normalização adicional para impedir que as órbitas sejam normalizadas, siga o procedimento em [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md) para definir uma nova regra de normalização, para que o **padrão correspondente** identifique o intervalo de órbita e o **padrão de tradução** é **$1**.</span><span class="sxs-lookup"><span data-stu-id="d56eb-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="d56eb-107">Por exemplo, se a faixa de texto da sua chamada é 7000 – 7999, o **padrão a ser correspondido** é **\\^{3}(7 d) $** e o **padrão de tradução** é **$1**.</span><span class="sxs-lookup"><span data-stu-id="d56eb-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d56eb-108">Certifique-se de que a regra de normalização padrão em seu plano de discagem não contém o <STRONG>^(\d\*)</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d56eb-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="d56eb-109">Caso contrário, sua regra de normalização do estacionamento de chamada nunca será executada.</span><span class="sxs-lookup"><span data-stu-id="d56eb-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d56eb-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="d56eb-110">See Also</span></span>


[<span data-ttu-id="d56eb-111">Criar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d56eb-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

