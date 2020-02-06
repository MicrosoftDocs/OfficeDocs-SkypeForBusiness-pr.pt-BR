---
title: Planeje a alta disponibilidade e a recuperação de desastres no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastres com emparelhamento de pool e vários modos de alta disponibilidade de servidor back-end, incluindo grupos de disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL.
ms.openlocfilehash: 521ddaa9878ba660e509f248d2f2ffb944608d87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815919"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planeje a alta disponibilidade e a recuperação de desastres no Skype for Business Server
 
O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastres com emparelhamento de pool e vários modos de alta disponibilidade de servidor back-end, incluindo grupos de disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL. 
  
Alta disponibilidade refere-se a garantir que os serviços do Skype for Business Server estejam disponíveis mesmo se um ou mais servidores ficarem inativos. Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
Como nas versões anteriores do Lync Server, o principal recurso de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server é a redundância do servidor via pooling. Se um servidor que executa determinada função falhar, os demais servidores do pool que executam a mesma função assumirão a carga desse servidor. Isso se aplica a Servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.
  
O Skype for Business Server também fornece opções de recuperação de desastres para pools front-end. Você pode configurar dois pools em diferentes áreas geográficas para servirem de backup um do outro. Assim, se um local ou pool inteiro ficar inoperante, o pool de backup continuará fornecendo serviço aos usuários de ambos os locais.
  
O Skype for Business Server também oferece suporte a quatro modos de alta disponibilidade para seus servidores back-end: espelhamento do SQL, grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn (FCI) e cluster de failover do SQL.
  
> [!NOTE]
> O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, as instâncias de cluster de failover AlwaysOn (FCI) e os métodos de cluster de failover do SQL são preferidos com o Skype for Business Server 2019.

> [!NOTE]
> Os grupos de disponibilidade AlwaysOn não são compatíveis com servidores de chat persistentes. 
  
Esta seção explica esses recursos de alta disponibilidade e também detalha os passos que você pode tomar para ter alta disponibilidade e recuperação de desastres em algumas das demais funções de servidor. 
  
## <a name="see-also"></a>Confira também

[Alta disponibilidade e gerenciamento de Pool de Front-Ends](high-availability.md)
  
[Recuperação de desastre do pool de front-end no Skype for Business Server](disaster-recovery.md)
  
[Experiência do usuário durante uma falha de pool no Skype for Business Server](user-experience.md)
  
[Back-end Server alta disponibilidade no Skype for Business Server](back-end-server.md)
  
[Compartilhamento de arquivos com alta disponibilidade no Skype for Business Server](file-sharing.md)
