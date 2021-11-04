---
title: Verificar regras de normalização para Estacionamento de Chamada no Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Saiba mais sobre regras de normalização para Estacionamento de Chamada Skype for Business Server Enterprise Voice.
ms.openlocfilehash: ca76c15d7f71afa75e9b9247eab9cd96e5baedb0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771526"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificar regras de normalização para Estacionamento de Chamada no Skype for Business
 
Saiba mais sobre regras de normalização para Estacionamento de Chamada Skype for Business Server Enterprise Voice.
  
Órbitas do Estacionamento de Chamada não devem ser normalizadas. Verifique seus planos de discagem para ter certeza de que seus números de órbita não estão normalizados. Se você deve criar uma regra de normalização adicional para impedir que suas órbitas seja normalizada, siga o procedimento em Criar ou modificar um plano de discagem em [Skype for Business Server](dial-plans.md) para definir uma nova regra de normalização, de modo que **Pattern** para corresponder identifique o intervalo de órbitas e **o** padrão de tradução é **$1**. Por exemplo, se o intervalo de órbitas do Estacionamento de Chamada for 7000 - 7999, o **padrão** a ser corresponder será **^(7\d {3} )$ e** o padrão de conversão é **$1**. 
  
> [!IMPORTANT]
> Certifique-se de que a regra de normalização padrão em seus planos de discagem não contenha **^(\d \* )**. Caso contrário, a regra de normalização do Estacionamento de Chamada nunca será executado.
  
## <a name="see-also"></a>Confira também

[Criar ou modificar um plano de discagem Skype for Business Server](dial-plans.md)

