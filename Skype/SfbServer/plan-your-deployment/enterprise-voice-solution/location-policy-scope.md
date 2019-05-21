---
title: Atribuir o escopo da política de localização no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planejando políticas de localização para uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 04eb04733649e2967980e0121d17cf71221f5387
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276737"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Atribuir o escopo da política de localização no Skype for Business Server
 
Planejando políticas de localização para uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
  
Assim como em outras políticas do Skype for Business Server, as políticas de localização podem ser atribuídas em vários níveis de escopo: global, site e usuário. No entanto, o escopo das políticas de localização em nível de usuário tem um pouco diferente do que com outras políticas do Skype for Business Server. Não apenas as políticas de localização por usuário podem ser aplicadas a objetos de ponto de extremidade (como usuários e objetos de contato de telefone comum), também podem ser aplicadas a sites de rede do Skype for Business Server. Os sites de rede são agrupamentos de subredes de cliente associadas com um local geográfico (mas não necessariamente deve ser todas as subredes em um site central ou site de filial). Qualquer cliente conectado às subredes de um site de rede obtém automaticamente a política de local atribuída a este site de rede. Em casos onde uma política de local a nível de usuário é atribuída ao usuário e a um site de rede, a política de local baseada em site de rede substitui qualquer configuração de política por usuário.
  
Cada local de rede possui uma política de rede atribuída e cada política possuirá diferentes valores de Usos de PSTN, URIs de notificação e URIs de conferência atribuídos.
  
> [!NOTE]
> O motivo para esta política especial se comportar desta forma é porque quando um usuário hospedado em um pool em um local de escritório visita outro local e precisa fazer uma chamada de emergência, as configurações de roteamento de chamada E9-1-1 adequadas para este local de rede serão aplicadas não importando a qual pool ou local o usuário está atribuído. 
  

