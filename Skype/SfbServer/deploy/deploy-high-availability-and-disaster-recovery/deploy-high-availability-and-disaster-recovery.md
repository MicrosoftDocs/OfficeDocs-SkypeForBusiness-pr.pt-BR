---
title: Implantar alta disponibilidade e recuperação de desastre
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype para Business Server oferece alta disponibilidade com servidor pooling de recuperação de desastres com pareamento do pool e vários modos de alta disponibilidade servidor Back-End, incluindo grupos de disponibilidade do AlwaysOn, espelhamento de banco de dados e o cluster de failover do SQL.
ms.openlocfilehash: 96e1f0614aac72197f0b34b8432b65d2c859c4ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894588"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Implantar alta disponibilidade e recuperação de desastre
 
Skype para Business Server oferece alta disponibilidade com servidor pooling de recuperação de desastres com pareamento do pool e vários modos de alta disponibilidade servidor Back-End, incluindo grupos de disponibilidade do AlwaysOn, espelhamento de banco de dados e o cluster de failover do SQL. 
  
Alta disponibilidade refere-se ao certificando-se de que o Skype para serviços de Business Server estão disponíveis, mesmo se um ou mais servidores cair. Recuperação de desastres refere-se aos serviços keeping indo em caso de um desastre natural ou causado por humanos e preservação de todos os dados antes do desastre possível.
  
Esta seção explica como implantar esses recursos e também aborda as etapas que você pode seguir para assegurar alta disponibilidade e recuperação de desastre para algumas das outras funções de servidor.

> [!NOTE]
> Espelhamento do SQL está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. Os métodos de cluster de failover de grupos de disponibilidade AlwaysOn, instâncias de Cluster de Failover AlwaysOn (FCI) e SQL terão preferência com Skype para Business Server 2019.
  
## <a name="related-sections"></a>Seções relacionadas

[Planejar para alta disponibilidade e recuperação de desastres no Skype Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Confira também

[Implantar um grupo de disponibilidade do AlwaysOn em um servidor de Back-End no Skype para Business Server](alwayson-availability-group.md)

[Implantar pools de Front-End pareados para recuperação de desastres em Skype para Business Server](front-end-pools-for-disaster-recovery.md)
  
[Implantar espelhamento de SQL para alta disponibilidade do servidor back-end no Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
