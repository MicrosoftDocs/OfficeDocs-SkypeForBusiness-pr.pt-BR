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
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificar regras de normalização para Estacionamento de Chamadas no Skype for Business
 
Saiba mais sobre as regras de normalização para Estacionamento de Chamada no Skype for Business Server Enterprise Voice.
  
Órbitas do Estacionamento de Chamada não devem ser normalizadas. Verifique seus planos de discagem para garantir que seus números de órbita não sejam normalizados. Se você tiver que criar uma regra de normalização adicional para impedir que suas órbitas seja normalizada, siga o procedimento  em Criar ou modificar um  plano de discagem no [Skype for Business Server](dial-plans.md) para definir uma nova regra de normalização, de modo que Pattern para corresponder identifique o intervalo de órbitas e o padrão de conversão é de **US$ 1.** Por exemplo, se o intervalo de órbita do Estacionamento de Chamada  for de 7000 a 7999, o padrão a ser corresponder será **^(7\d {3} )$** e o padrão de conversão será **$1.** 
  
> [!IMPORTANT]
> Certifique-se de que a regra de normalização padrão em seus planos de discagem não contenha **^(\d \* )**. Caso contrário, a regra de normalização do Estacionamento de Chamada nunca será executado.
  
## <a name="see-also"></a>Confira também

[Criar ou modificar um plano de discagem no Skype for Business Server](dial-plans.md)

