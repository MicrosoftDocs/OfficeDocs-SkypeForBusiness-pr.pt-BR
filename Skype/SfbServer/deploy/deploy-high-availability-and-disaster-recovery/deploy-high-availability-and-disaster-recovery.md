---
title: Implantar alta disponibilidade e recuperação de desastres
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
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 'O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastre com emparelhamento de pool e vários modos de alta disponibilidade do Servidor #A0, incluindo grupos de Disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover sql.'
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830611"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Implantar alta disponibilidade e recuperação de desastres
 
O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastre com emparelhamento de pool e vários modos de alta disponibilidade do Servidor #A0, incluindo grupos de Disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover sql. 
  
Alta disponibilidade refere-se a garantir que os serviços do Skype for Business Server estão disponíveis mesmo que um ou mais servidores caiam. A recuperação de desastre refere-se a manter os serviços em caso de desastre natural ou causado por humanos e preservar o máximo de dados de antes do desastre possível.
  
Esta seção mostra como implantar esses recursos e também aborda quais etapas você pode seguir para alta disponibilidade e recuperação de desastres para algumas de suas outras funções de servidor.

> [!NOTE]
> O espelhamento sql está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn (FCI) e métodos de cluster de failover SQL são preferenciais com o Skype for Business Server 2019.
  
## <a name="related-sections"></a>Seções relacionadas

[Planejar alta disponibilidade e recuperação de desastre no Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Confira também

[Implantar um grupo de disponibilidade AlwaysOn em um servidor back-end no Skype for Business Server](alwayson-availability-group.md)

[Implantar pools de front-end emparelhados para recuperação de desastre no Skype for Business Server](front-end-pools-for-disaster-recovery.md)
  
[Implantar espelhamento SQL para alta disponibilidade do Servidor #A0 no Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
