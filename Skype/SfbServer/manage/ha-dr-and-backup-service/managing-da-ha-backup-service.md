---
title: Gerenciamento de recuperação de desastres, alta disponibilidade e serviço de backup
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Saiba mais sobre os procedimentos para operações de recuperação de desastres, bem como para manter o serviço de backup, que sincroniza os dados em pools front-ends emparelhados.
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303895"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Gerenciamento de recuperação de desastres do Skype for Business Server, alta disponibilidade e serviço de backup

Esta seção contém procedimentos para operações de recuperação de desastres, bem como para manter o serviço de backup, que sincroniza os dados em pools front-ends emparelhados.

Procedimentos de recuperação de desastre, failover e failback, são manuais. Se houver um desastre, o administrador deve invocar manualmente os procedimentos de failover. O mesmo se aplica a failback após o rereparo do pool.

Os procedimentos de recuperação de desastres nesta seção pressupõem o seguinte:

  - Você tem uma implantação com pools front-end emparelhados, localizada em sites diferentes, conforme descrito em [planejar a alta disponibilidade e a recuperação de desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). O serviço de backup está em execução nesses pools emparelhados para mantê-los sincronizados.

  - Se o repositório de gerenciamento central estiver hospedado em qualquer um dos pools, ele será instalado e executado em ambos os pools emparelhados, com um desses pools que hospeda o mestre ativo e o outro pool que hospeda o modo de espera.

> [!IMPORTANT]
> Nos procedimentos a seguir, o parâmetro *PoolFQDN* refere-se ao FQDN do pool afetado pelo desastre, e não ao pool em que os usuários afetados estão sendo redirecionados. Para o mesmo conjunto de usuários afetados, ele se refere ao mesmo pool em cmdlets de failover e failback (ou seja, o pool que primeiro hospeda os usuários antes do failover).<BR><br>Por exemplo, suponha que um caso em que todos os usuários hospedados em um pool P1 tivessem falhado para o pool de backup, P2. Se o administrador quiser mover todos os usuários atualmente atendidos pelo P2 a serem atendidos pelo P1, o administrador deve executar as seguintes etapas: 
> <OL>
> <LI>
> <P>Faça o failback de todos os usuários originalmente hospedados no P1 do P2 para P1 usando o cmdlet failback. Nesse caso, o *PoolFQDN* é P1's FQDN.</P>
> <LI>
> <P>Fazer failover de todos os usuários originalmente hospedados no P2 do P1 usando o cmdlet de failover. Nesse caso, o PoolFQDN é P2's FQDN.</P>
> <LI>
> <P>Se o administrador mais tarde quiser fazer failback desses usuários de P2 de volta para P2, o PoolFQDN será P2's FQDN.</P></LI></OL><br>Observe que a etapa 1 acima deve ser realizada antes da etapa 2 para preservar a integridade do pool. Se você tentar a etapa 2 antes da etapa 1, o cmdlet etapa 2 falhará.


## <a name="see-also"></a>Confira também

[Planejar alta disponibilidade e recuperação de desastre](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
