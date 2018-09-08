---
title: Atribuir o escopo da política de local no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planejando as políticas de local para uma implantação do E9-1-1 em Skype Business Server Enterprise Voice.
ms.openlocfilehash: 28759d88be1586149b0dd482d934c5bbc89a1853
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881878"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Atribuir o escopo da política de local no Skype para Business Server
 
Planejando as políticas de local para uma implantação do E9-1-1 em Skype Business Server Enterprise Voice.
  
Como com outra Skype para políticas de Business Server, as políticas de local podem ser atribuídas nos vários níveis de escopo: global, site e usuário. No entanto, o escopo de políticas de nível de usuário local se comporta um bit de forma diferente com outro Skype para políticas de Business Server. Não apenas políticas de local por usuário podem ser aplicadas a objetos de ponto de extremidade (por exemplo, usuários e objetos de contato de telefone de área comum), eles também podem ser aplicados a Skype para sites de rede do servidor de negócios. Os sites de rede são agrupamentos de subredes de cliente associadas com um local geográfico (mas não necessariamente deve ser todas as subredes em um site central ou site de filial). Qualquer cliente conectado às subredes de um site de rede obtém automaticamente a política de local atribuída a este site de rede. Em casos onde uma política de local a nível de usuário é atribuída ao usuário e a um site de rede, a política de local baseada em site de rede substitui qualquer configuração de política por usuário.
  
Cada local de rede possui uma política de rede atribuída e cada política possuirá diferentes valores de Usos de PSTN, URIs de notificação e URIs de conferência atribuídos.
  
> [!NOTE]
> O motivo para esta política especial se comportar desta forma é porque quando um usuário hospedado em um pool em um local de escritório visita outro local e precisa fazer uma chamada de emergência, as configurações de roteamento de chamada E9-1-1 adequadas para este local de rede serão aplicadas não importando a qual pool ou local o usuário está atribuído. 
  

