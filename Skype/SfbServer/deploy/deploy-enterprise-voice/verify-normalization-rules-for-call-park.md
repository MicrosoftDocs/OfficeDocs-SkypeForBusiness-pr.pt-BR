---
title: Verifique se as regras de normalização para estacionamento de chamada no Skype para negócios
ms.author: kenwith
author: kenwith
manager: serdars
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
ms.openlocfilehash: e45e438f0abf4527f84f51a8be81606b024d4685
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983522"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verifique se as regras de normalização para estacionamento de chamada no Skype para negócios
 
Saiba mais sobre as regras de normalização para estacionamento de chamada no Skype para Business Server Enterprise Voice.
  
Órbitas de estacionamento de chamada não devem ser normalizadas. Verifique seus planos de discagem para garantir que seus números de órbita não estão normalizados. Se for preciso criar uma regra de normalização adicional para evitar que seu Órbitas que está sendo normalizado, siga o procedimento em [criar ou modificar um plano de discagem no Skype para Business Server](dial-plans.md) para definir uma nova regra de normalização, então esse **padrão para corresponder** identifica o intervalo de órbita e **padrão de conversão** é de **US $1**. Por exemplo, se o intervalo de órbita de estacionamento de chamada for 7000-7999, o **padrão para corresponder** é **^(7\d{3})$** e **padrão de conversão** é de **US $1**.
  
> [!IMPORTANT]
> Certifique-se de que a regra de normalização padrão em seus planos de discagem não contém **^(\d\*)**. Caso contrário, a regra de normalização de estacionamento de chamada nunca será executado.
  
## <a name="see-also"></a>Consulte também

[Criar ou modificar um plano de discagem no Skype para Business Server](dial-plans.md)

