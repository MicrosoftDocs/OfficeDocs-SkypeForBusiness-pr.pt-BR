---
title: Implantar alta disponibilidade e recuperação de desastre
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastres com emparelhamento de pool e vários modos de alta disponibilidade de servidor back-end, incluindo grupos de disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL.
ms.openlocfilehash: cb4d39df7f6a12a14c25533d8c6fb1ae95da24d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240058"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Implantar alta disponibilidade e recuperação de desastre
 
O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastres com emparelhamento de pool e vários modos de alta disponibilidade de servidor back-end, incluindo grupos de disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL. 
  
Alta disponibilidade refere-se a garantir que os serviços do Skype for Business Server estejam disponíveis mesmo se um ou mais servidores ficarem inativos. A recuperação de desastres refere-se à manutenção de serviços em caso de desastres naturais ou naturais, e preservando o máximo de dados de antes do desastre possível.
  
Esta seção explica como implantar esses recursos e também aborda as etapas que você pode seguir para assegurar alta disponibilidade e recuperação de desastre para algumas das outras funções de servidor.

> [!NOTE]
> O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, as instâncias de cluster de failover AlwaysOn (FCI) e os métodos de cluster de failover do SQL são preferidos com o Skype for Business Server 2019.
  
## <a name="related-sections"></a>Seções relacionadas

[Planeje a alta disponibilidade e a recuperação de desastres no Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>Confira também

[Implantar um grupo de disponibilidade AlwaysOn em um servidor back-end no Skype for Business Server](alwayson-availability-group.md)

[Implantar pools de front-end emparelhados para recuperação de desastres no Skype for Business Server](front-end-pools-for-disaster-recovery.md)
  
[Implantar espelhamento de SQL para alta disponibilidade do servidor back-end no Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
