---
title: Gerenciando o serviço de Backup, alta disponibilidade e recuperação de desastres
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Saiba mais sobre os procedimentos para operações de recuperação de desastres, bem como para manter o serviço de Backup, que sincroniza os dados nos pools de Front-Ends emparelhados.
ms.openlocfilehash: 1f0a8980e1b883f505a0ba5a5492f3e9edfff90a
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222909"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Gerenciando Skype para o serviço de Backup, alta disponibilidade e recuperação de desastres Business Server

Esta seção contém procedimentos para operações de recuperação de desastres, bem como para manter o serviço de Backup, que sincroniza os dados nos pools de Front-Ends emparelhados.

Procedimentos de recuperação de desastres, failover e failback, são manuais. Se houver um desastre, o administrador deve chamar manualmente os procedimentos de failover. O mesmo se aplica a failback depois que o pool for reparado.

Os procedimentos de recuperação de desastres nesta seção supõem o seguinte:

  - Você possuir uma implantação com emparelhados pools de Front-End, localizado em diferentes sites, conforme descrito em [plano para alta disponibilidade e recuperação de desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). O serviço de Backup está sendo executado nesses pools emparelhados para mantê-los sincronizados.

  - Se o repositório de gerenciamento Central está hospedado em um pool, é instalado e em execução em ambos os pools emparelhados, com um desses pools que hospedam o mestre ativo e outro pool hospedando em espera.

> [!IMPORTANT]
> Nos procedimentos a seguir, o parâmetro *PoolFQDN* se refere ao FQDN do pool que é afetado por desastre, não o pool que afetaram os usuários são redirecionadas a partir do. Para o mesmo conjunto de usuários afetados, ele se refere ao mesmo pool nos cmdlets de failover e failback (ou seja, o pool que primeiro hospedados os usuários antes do failover).<BR><br>Por exemplo, suponha que um caso em que todos os usuários hospedados em um pool P1 sofreram failover para o pool de backup, P2. Se o administrador deseja mover todos os usuários atualmente atendidos pelo P2 sejam atendidas pelo P1, o administrador deve executar as seguintes etapas: 
> <OL>
> <LI>
> <P>Fazer o fail todos os usuários originalmente hospedados no P1 de P2 a P1 usando o cmdlet de failback. Nesse caso, o *PoolFQDN* é P1 FQDN.</P>
> <LI>
> <P>Failover de todos os usuários originalmente hospedados no P2 a P1 usando o cmdlet de failover. Nesse caso, o PoolFQDN é do P2 FQDN.</P>
> <LI>
> <P>Se o administrador deseje posteriormente failback esses usuários P2 para o P2, o PoolFQDN é do P2 FQDN.</P></LI></OL><br>Observe que essa etapa 1 acima deve ser executada antes da etapa 2 para preservar a integridade do pool. Se você tentar etapa 2 antes da etapa 1, o cmdlet de etapa 2 falhará.


## <a name="see-also"></a>Consulte Também

[Planejar alta disponibilidade e recuperação de desastre](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
