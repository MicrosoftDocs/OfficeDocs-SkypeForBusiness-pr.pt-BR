---
title: Gerenciamento de recuperação de desastres, alta disponibilidade e Serviço de Backup
ms.reviewer: ''
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Saiba mais sobre procedimentos para operações de recuperação de desastres, bem como para manter o Serviço de Backup, que sincroniza os dados em pools front-end emparelhados.
ms.openlocfilehash: 6d3eb3356c48a99974390f43bc0114d7d6507353
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849934"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Gerenciamento Skype for Business Server recuperação de desastres, alta disponibilidade e Serviço de Backup

Esta seção contém procedimentos para operações de recuperação de desastres, bem como para manter o Serviço de Backup, que sincroniza os dados em pools de Front-End emparelhados.

Os procedimentos de recuperação de desastres, o failover e o failback, são manuais. Se ocorrer um desastre, o administrador deve chamar manualmente os procedimentos de failover. O mesmo se aplica ao failback após a reparação do pool.

Os procedimentos de recuperação de desastres nesta seção assumem o seguinte:

  - Você tem uma implantação com pools front-end emparelhados, localizados em sites diferentes, conforme descrito em [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). O Serviço de Backup é executado nestes pools emparelhados para mantê-los sincronizados.

  - Se o armazenamento de Gerenciamento Central estiver hospedado em um dos pools, ele será instalado e executado em ambos os pools emparelhados, com um desses pools hospedando o mestre ativo e o outro pool hospedando o modo de espera.

> [!IMPORTANT]
> Nos procedimentos a seguir, o parâmetro *PoolFQDN* se refere ao FQDN do pool afetado pelo desastre, e não o pool para o qual os usuários afetados foram redirecionados. Para o mesmo conjunto de usuários afetados, ele se refere ao mesmo pool em ambos os cmdlets de failover e failback (ou seja, o pool que primeiramente hospedou os usuários antes do failover).<BR><br>Por exemplo, pressuponha um caso em que todos os usuários hospedados no pool P1 foram transferidos para o pool de backup, o P2. Se o administrador deseja mover todos os usuários que utilizam os serviços de P2 para utilizarem os serviços de P1, o administrador deve executar as seguintes etapas: 
> <OL>
> <LI>
> <P>Retorne do P2 para o P1 todos os usuários originalmente hospedados em P1 utilizando o cmdlet de failback. Nesse caso, *PoolFQDN* é o FQDN de P1.</P>
> <LI>
> <P>Transfira todos os usuários originalmente hospedados em P2 para o P1 utilizando o cmdlet de failover. Nesse caso, a propriedade PoolFQDN é o FQDN de P2.</P>
> <LI>
> <P>Se o administrador desejar retornar posteriormente os usuários para o P2, o PoolFQDN é o FQDN do P2.</P></LI></OL><br>Observe que a etapa 1 acima deve ser realizada antes da etapa 2 para preservar a integridade do pool. Se você executar a etapa 2 antes da etapa 1, o cmdlet da etapa 2 falhará.


## <a name="see-also"></a>Confira também

[Planejar alta disponibilidade e recuperação de desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
