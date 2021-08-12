---
title: Verificar regras de normalização para Estacionamento de Chamada no Skype for Business
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
description: Saiba mais sobre regras de normalização para Estacionamento de Chamada Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 5c357a9ff9b2174ae414e1e4511cb7ebf267e19787091e19ce27f75f90b8a51e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298611"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificar regras de normalização para Estacionamento de Chamada no Skype for Business
 
Saiba mais sobre regras de normalização para Estacionamento de Chamada Skype for Business Server Enterprise Voice.
  
Órbitas do Estacionamento de Chamada não devem ser normalizadas. Verifique seus planos de discagem para ter certeza de que seus números de órbita não estão normalizados. Se você deve criar uma regra de normalização adicional para impedir que suas órbitas seja normalizada, siga o procedimento em Criar ou modificar um plano de discagem em [Skype for Business Server](dial-plans.md) para definir uma nova regra de normalização, de modo que **Pattern** para corresponder identifique o intervalo de órbitas e **o** padrão de tradução é **$1**. Por exemplo, se o intervalo de órbitas do Estacionamento de Chamada for 7000 - 7999, o **padrão** a ser corresponder será **^(7\d {3} )$ e** o padrão de conversão é **$1**. 
  
> [!IMPORTANT]
> Certifique-se de que a regra de normalização padrão em seus planos de discagem não contenha **^(\d \* )**. Caso contrário, a regra de normalização do Estacionamento de Chamada nunca será executado.
  
## <a name="see-also"></a>Confira também

[Criar ou modificar um plano de discagem Skype for Business Server](dial-plans.md)

