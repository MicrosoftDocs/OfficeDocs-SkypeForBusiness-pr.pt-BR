---
title: Planejar para alta disponibilidade e recuperação de desastres no Skype Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype para Business Server oferece alta disponibilidade com servidor pooling de recuperação de desastres com pareamento do pool e vários modos de alta disponibilidade servidor Back-End, incluindo grupos de disponibilidade do AlwaysOn, espelhamento de banco de dados e o cluster de failover do SQL.
ms.openlocfilehash: 8ab0d41b93a47782fce4a44acf1e8305a9ad13e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910330"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Planejar para alta disponibilidade e recuperação de desastres no Skype Business Server
 
Skype para Business Server oferece alta disponibilidade com servidor pooling de recuperação de desastres com pareamento do pool e vários modos de alta disponibilidade servidor Back-End, incluindo grupos de disponibilidade do AlwaysOn, espelhamento de banco de dados e o cluster de failover do SQL. 
  
Alta disponibilidade refere-se ao certificando-se de que o Skype para serviços de Business Server estão disponíveis, mesmo se um ou mais servidores cair. Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
Como nas versões anteriores do Microsoft Lync Server, o recurso de alta disponibilidade principal para a maioria das funções de servidor em Skype para Business Server é redundância de servidor por meio do pool. Se um servidor que executa determinada função falhar, os demais servidores do pool que executam a mesma função assumirão a carga desse servidor. Isso se aplica a Servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.
  
Skype para Business Server também oferece desastres opções de recuperação para pools de Front-End. Você pode configurar dois pools em diferentes áreas geográficas para servirem de backup um do outro. Assim, se um local ou pool inteiro ficar inoperante, o pool de backup continuará fornecendo serviço aos usuários de ambos os locais.
  
Skype para Business Server também oferece suporte a quatro modos de alta disponibilidade para seus servidores Back-End: espelhamento, clustering de failover do SQL, instâncias de Cluster de Failover AlwaysOn (FCI) e grupos de disponibilidade AlwaysOn do SQL.
  
> [!NOTE]
> Espelhamento do SQL está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. Os métodos de cluster de failover de grupos de disponibilidade AlwaysOn, instâncias de Cluster de Failover AlwaysOn (FCI) e SQL terão preferência com Skype para Business Server 2019.

> [!NOTE]
> Não há suporte para grupos de disponibilidade do AlwaysOn com servidores de Chat persistente. 
  
Esta seção explica esses recursos de alta disponibilidade e também detalha os passos que você pode tomar para ter alta disponibilidade e recuperação de desastres em algumas das demais funções de servidor. 
  
## <a name="see-also"></a>Confira também

[Alta disponibilidade e gerenciamento de Pool de Front-Ends](high-availability.md)
  
[Front-End pool disaster recovery no Skype para Business Server](disaster-recovery.md)
  
[Experiência do usuário durante falha do pool no Skype para Business Server](user-experience.md)
  
[Back End alta disponibilidade do servidor no Skype para Business Server](back-end-server.md)
  
[Alta disponibilidade de compartilhamento de arquivos no Skype para Business Server](file-sharing.md)
