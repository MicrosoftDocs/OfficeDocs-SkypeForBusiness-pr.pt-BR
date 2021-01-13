---
title: Verificar regras de normalização para Estacionamento de Chamadas no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Saiba mais sobre as regras de normalização para Estacionamento de Chamada no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830571"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="8b602-103">Verificar regras de normalização para Estacionamento de Chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8b602-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="8b602-104">Saiba mais sobre as regras de normalização para Estacionamento de Chamada no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="8b602-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="8b602-105">Órbitas do Estacionamento de Chamada não devem ser normalizadas.</span><span class="sxs-lookup"><span data-stu-id="8b602-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="8b602-106">Verifique seus planos de discagem para garantir que seus números de órbita não sejam normalizados.</span><span class="sxs-lookup"><span data-stu-id="8b602-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="8b602-107">Se você tiver que criar uma regra de normalização adicional para impedir que suas órbitas seja normalizada, siga o procedimento  em Criar ou modificar um  plano de discagem no [Skype for Business Server](dial-plans.md) para definir uma nova regra de normalização, de modo que Pattern para corresponder identifique o intervalo de órbitas e o padrão de conversão é de **US$ 1.**</span><span class="sxs-lookup"><span data-stu-id="8b602-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="8b602-108">Por exemplo, se o intervalo de órbita do Estacionamento de Chamada  for de 7000 a 7999, o padrão a ser corresponder será **^(7\d {3} )$** e o padrão de conversão será **$1.** </span><span class="sxs-lookup"><span data-stu-id="8b602-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8b602-109">Certifique-se de que a regra de normalização padrão em seus planos de discagem não contenha **^(\d \* )**.</span><span class="sxs-lookup"><span data-stu-id="8b602-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="8b602-110">Caso contrário, a regra de normalização do Estacionamento de Chamada nunca será executado.</span><span class="sxs-lookup"><span data-stu-id="8b602-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8b602-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="8b602-111">See also</span></span>

[<span data-ttu-id="8b602-112">Criar ou modificar um plano de discagem no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8b602-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

