---
title: Verificar as regras de normalização para o estacionamento de chamadas no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Saiba mais sobre as regras de normalização para o parque de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 38de300970341d563f2a532847a39c2fe98e15e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240014"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="5dab7-103">Verificar as regras de normalização para o estacionamento de chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5dab7-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="5dab7-104">Saiba mais sobre as regras de normalização para o parque de chamadas no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5dab7-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="5dab7-105">As órbitas do estacionamento de chamada não devem ser normalizadas.</span><span class="sxs-lookup"><span data-stu-id="5dab7-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="5dab7-106">Verifique seus planos de discagem para garantir que seus números de órbita não estão normalizados.</span><span class="sxs-lookup"><span data-stu-id="5dab7-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="5dab7-107">Se você precisar criar uma regra de normalização adicional para impedir que as órbitas sejam normalizadas, siga o procedimento em [criar ou modificar um plano de discagem no Skype for Business Server](dial-plans.md) para definir uma nova regra de normalização, para que o **padrão corresponda** Identifica o intervalo de órbita e o **padrão de tradução** é **$1**.</span><span class="sxs-lookup"><span data-stu-id="5dab7-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="5dab7-108">Por exemplo, se a faixa de texto do parque de chamadas for 7000-7999, o **padrão a ser correspondido** será **^{3}(7 \ d) $** e o **padrão de tradução** será **$1**.</span><span class="sxs-lookup"><span data-stu-id="5dab7-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5dab7-109">Certifique-se de que a regra de normalização padrão em seus planos de discagem não contenha **^ (\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="5dab7-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="5dab7-110">Caso contrário, sua regra de normalização do estacionamento de chamada nunca será executada.</span><span class="sxs-lookup"><span data-stu-id="5dab7-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5dab7-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="5dab7-111">See also</span></span>

[<span data-ttu-id="5dab7-112">Criar ou modificar um plano de discagem no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5dab7-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

