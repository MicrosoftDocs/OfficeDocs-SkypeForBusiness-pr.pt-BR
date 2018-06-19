---
title: Verificar regras de normalização para Estacionamento de Chamadas no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Saiba mais sobre as regras de normalização para estacionamento de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: d97c882efccf208d4457ec3bbbc0c2bf1a4e0b53
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500665"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="df5c8-103">Verificar regras de normalização para Estacionamento de Chamadas no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="df5c8-103">Verify normalization rules for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="df5c8-104">Saiba mais sobre as regras de normalização para estacionamento de chamada no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="df5c8-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="df5c8-105">Órbitas de estacionamento de chamada não devem ser normalizadas.</span><span class="sxs-lookup"><span data-stu-id="df5c8-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="df5c8-106">Verifique seus planos de discagem para garantir que seus números de órbita não estão normalizados.</span><span class="sxs-lookup"><span data-stu-id="df5c8-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="df5c8-107">Se for preciso criar uma regra de normalização adicional para evitar que seu Órbitas que está sendo normalizado, siga o procedimento em [criar ou modificar um plano de discagem no Skype para Business Server 2015](dial-plans.md) para definir uma nova regra de normalização, então esse **padrão para corresponder** identifica o intervalo de órbita e **padrão de conversão** é de **US $1**.</span><span class="sxs-lookup"><span data-stu-id="df5c8-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="df5c8-108">Por exemplo, se o intervalo de órbita de estacionamento de chamada for 7000-7999, o **padrão para corresponder** é **^(7\d{3})$** e **padrão de conversão** é de **US $1**.</span><span class="sxs-lookup"><span data-stu-id="df5c8-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="df5c8-109">Certifique-se de que a regra de normalização padrão em seus planos de discagem não contém **^(\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="df5c8-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="df5c8-110">Caso contrário, a regra de normalização de estacionamento de chamada nunca será executado.</span><span class="sxs-lookup"><span data-stu-id="df5c8-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="df5c8-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="df5c8-111">See also</span></span>

[<span data-ttu-id="df5c8-112">Criar ou modificar um plano de discagem no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="df5c8-112">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)