---
title: Atribuir escopo de política de local no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planejamento de políticas de local para uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825521"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Atribuir escopo de política de local no Skype for Business Server
 
Planejamento de políticas de local para uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
  
Assim como com outras políticas do Skype for Business Server, as políticas de local podem ser atribuídas em vários níveis de escopo: global, site e usuário. No entanto, o escopo das políticas de local no nível do usuário se comporta um pouco diferente de outras políticas do Skype for Business Server. Não só as políticas de local por usuário podem ser aplicadas a objetos de ponto de extremidade (como objetos de contato usuários e telefone de área comum), como também podem ser aplicadas aos sites de rede do Skype for Business Server. Os sites de rede são agrupamentos de sub-redes de clientes associados a uma localidade geográfica (mas podem não ser necessariamente todas as sub-redes em todo o site central ou site de filial). Quaisquer clientes conectados às sub-redes em um site de rede automaticamente selecionam a política de local designada para o site de rede. Nos casos em que uma política de local no nível do usuário é atribuída a um usuário e a um site de rede, a política de local baseada em site de rede substitui qualquer configuração de política por usuário.
  
Cada site de rede possui uma política de local atribuída a ele e cada política terá diferentes valores para Usos do PSTN, URIs de Notificação e URIs da Conferência atribuídos a ela.
  
> [!NOTE]
> O motivo para esse comportamento especial de scoping de política é que, quando um usuário que está em um pool em um site do escritório visita outro site e precisa fazer uma chamada de emergência, as configurações de roteamento de chamada E9-1-1 apropriadas para esse local de rede serão aplicadas independentemente do pool ou site ao qual o usuário está atribuído. 
  

