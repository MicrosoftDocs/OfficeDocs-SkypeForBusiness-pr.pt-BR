---
title: Gerenciando recuperação de desastre, alta disponibilidade e serviço de backup do Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89c18076a2bbc34386872a7fbee92c26b8084598
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Gerenciando recuperação de desastre, alta disponibilidade e serviço de backup do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-12_

Esta seção contém os procedimentos para operações de recuperação de desastres, bem como para realizar a manutenção do Serviço de Backup, que sincroniza os dados de pools de Front Ends emparelhados.

Os procedimentos de recuperação de desastres, o failover e o failback, são manuais. Se ocorrer um desastre, o administrador deve chamar manualmente os procedimentos de failover. O mesmo se aplica ao failback após a reparação do pool.

Os procedimentos de recuperação de desastres no restante dessa seção pressupõem que:

  - Você tem uma implantação com pools de front-ends emparelhados, localizados em diferentes sites, conforme descrito em [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). O Serviço de Backup é executado nestes pools emparelhados para mantê-los sincronizados.

  - Se o repositório de gerenciamento central estiver hospedado em um dos pools, ele será instalado e executado nos dois pools emparelhados, com um desses pools hospedando o mestre ativo e o outro pool que hospeda o modo de espera.

<div>


> [!IMPORTANT]
> Nos procedimentos a seguir, o parâmetro <EM>PoolFQDN</EM> se refere ao FQDN do pool afetado pelo desastre, e não o pool para o qual os usuários afetados foram redirecionados. Para o mesmo conjunto de usuários afetados, ele se refere ao mesmo pool em ambos os cmdlets de failover e failback (ou seja, o pool que primeiramente hospedou os usuários antes do failover).<BR>Por exemplo, pressuponha um caso em que todos os usuários hospedados no pool P1 foram transferidos para o pool de backup, o P2. Se o administrador deseja mover todos os usuários que utilizam os serviços de P2 para utilizarem os serviços de P1, o administrador deve executar as seguintes etapas: 
> <OL>
> <LI>
> <P>Retorne do P2 para o P1 todos os usuários originalmente hospedados em P1 utilizando o cmdlet de failback. Nesse caso, <EM>PoolFQDN</EM> é o FQDN de P1.</P>
> <LI>
> <P>Transfira todos os usuários originalmente hospedados em P2 para o P1 utilizando o cmdlet de failover. Nesse caso, a propriedade <EM>PoolFQDN</EM> é o FQDN de P2.</P>
> <LI>
> <P>Se o administrador desejar retornar posteriormente os usuários para o P2, o <EM>PoolFQDN</EM> é o FQDN do P2.</P></LI></OL>Observe que a etapa 1 acima deve ser realizada antes da etapa 2 para preservar a integridade do pool. Se você executar a etapa 2 antes da etapa 1, o cmdlet da etapa 2 falhará.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando e monitorando o serviço de backup no Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Failover de um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Failback de um pool no Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Failover de um banco de dados espelhado no Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Failover do pool de borda usado para Federação do Lync Server no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Failover do pool de borda usado para Federação XMPP no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Failback do pool de borda usado para Federação do Lync Server ou Federação XMPP no Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Alterar o pool de borda associado a um pool de front-ends no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Restaurando o conteúdo da conferência usando o serviço de backup no Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

