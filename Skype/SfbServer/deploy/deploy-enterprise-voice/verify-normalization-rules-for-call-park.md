---
title: Verificar as regras de normalização para o estacionamento de chamadas no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Saiba mais sobre as regras de normalização para o parque de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 769d9f9becccf4df24a33a11e8814350cfb091e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766884"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificar as regras de normalização para o estacionamento de chamadas no Skype for Business
 
Saiba mais sobre as regras de normalização para o parque de chamadas no Skype for Business Server Enterprise Voice.
  
As órbitas do estacionamento de chamada não devem ser normalizadas. Verifique seus planos de discagem para garantir que seus números de órbita não estão normalizados. Se você deve criar uma regra de normalização adicional para impedir que as órbitas sejam normalizadas, siga o procedimento em [criar ou modificar um plano de discagem no Skype for Business Server](dial-plans.md) para definir uma nova regra de normalização, para que o **padrão correspondente** identifique o intervalo de órbita e o **padrão de tradução** seja **$1**. Por exemplo, se a faixa de texto do parque de chamadas for 7000-7999, o **padrão a ser correspondido** será **^{3}(7 \ d) $** e o **padrão de tradução** será **$1**.
  
> [!IMPORTANT]
> Certifique-se de que a regra de normalização padrão em seus planos de discagem não contenha **^ (\d\*)**. Caso contrário, sua regra de normalização do estacionamento de chamada nunca será executada.
  
## <a name="see-also"></a>Confira também

[Criar ou modificar um plano de discagem no Skype for Business Server](dial-plans.md)

