---
title: Atribuir escopo de política de local Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planejando políticas de local para uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 2b3733df7e03f9f66b836a889732a023bddb18de
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770139"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Atribuir escopo de política de local Skype for Business Server
 
Planejando políticas de local para uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
  
Assim como em outras Skype for Business Server políticas de Skype for Business Server, as políticas de local podem ser atribuídas em vários níveis de escopo: global, site e usuário. No entanto, o escopo das políticas de localização no nível do usuário se comporta um pouco diferente das outras Skype for Business Server políticas. Não só as políticas de localização por usuário podem ser aplicadas a objetos de ponto de extremidade (como usuários e objetos de contato Telefone área comum), como também podem ser aplicadas Skype for Business Server sites de rede. Os sites de rede são agrupamentos de sub-redes de clientes associados a uma localidade geográfica (mas podem não ser necessariamente todas as sub-redes em todo o site central ou site de filial). Quaisquer clientes conectados às sub-redes em um site de rede automaticamente selecionam a política de local designada para o site de rede. Nos casos em que uma política de local no nível do usuário é atribuída a um usuário e a um site de rede, a política de local baseada em site de rede substitui qualquer configuração de política por usuário.
  
Cada site de rede possui uma política de local atribuída a ele e cada política terá diferentes valores para Usos do PSTN, URIs de Notificação e URIs da Conferência atribuídos a ela.
  
> [!NOTE]
> O motivo para esse comportamento especial de escoamento de política é para que, quando um usuário em um pool em um site do office visita outro site e precisa fazer uma chamada de emergência, as configurações de roteamento de chamadas do E9-1-1 apropriadas a esse site de rede serão aplicadas independentemente do pool ou do site ao qual o usuário é atribuído. 
  

