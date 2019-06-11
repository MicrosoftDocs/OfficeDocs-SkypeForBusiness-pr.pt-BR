---
title: Gerenciamento de recuperação de desastres do Lync Server, alta disponibilidade e serviço de backup
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cada393fca28895ee5f23a12fdd55eabd211128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Gerenciando recuperação de desastre, alta disponibilidade e Serviço de Backup do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-12_

Esta seção contém procedimentos para operações de recuperação de desastres, bem como para manter o serviço de backup que sincroniza os dados em pools front-ends emparelhados.

Procedimentos de recuperação de desastre, failover e failback, são manuais. Se houver um desastre, o administrador deve invocar manualmente os procedimentos de failover. O mesmo se aplica a failback após o rereparo do pool.

Os procedimentos de recuperação de desastre no restante desta seção pressupõem o seguinte:

  - Você tem uma implantação com pools front-end emparelhados, localizada em sites diferentes, conforme descrito em [planejamento para alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). O serviço de backup está em execução nesses pools emparelhados para mantê-los sincronizados.

  - Se o repositório de gerenciamento central estiver hospedado em qualquer um dos pools, ele será instalado e executado em ambos os pools emparelhados, com um desses pools que hospeda o mestre ativo e o outro pool que hospeda o modo de espera.

<div>


> [!IMPORTANT]
> Nos procedimentos a seguir, o parâmetro <EM>PoolFQDN</EM> refere-se ao FQDN do pool afetado pelo desastre, e não ao pool em que os usuários afetados estão sendo redirecionados. Para o mesmo conjunto de usuários afetados, ele se refere ao mesmo pool em cmdlets de failover e failback (ou seja, o pool que primeiro hospeda os usuários antes do failover).<BR>Por exemplo, suponha que um caso em que todos os usuários hospedados em um pool P1 tivessem falhado para o pool de backup, P2. Se o administrador quiser mover todos os usuários atualmente atendidos pelo P2 a serem atendidos pelo P1, o administrador deve executar as seguintes etapas: 
> <OL>
> <LI>
> <P>Faça o failback de todos os usuários originalmente hospedados no P1 do P2 para P1 usando o cmdlet failback. Nesse caso, o <EM>PoolFQDN</EM> é P1's FQDN.</P>
> <LI>
> <P>Fazer failover de todos os usuários originalmente hospedados no P2 do P1 usando o cmdlet de failover. Nesse caso, o <EM>PoolFQDN</EM> é P2's FQDN.</P>
> <LI>
> <P>Se o administrador mais tarde quiser fazer failback desses usuários de P2 de volta para P2, o <EM>PoolFQDN</EM> será P2's FQDN.</P></LI></OL>Observe que a etapa 1 acima deve ser realizada antes da etapa 2 para preservar a integridade do pool. Se você tentar a etapa 2 antes da etapa 1, o cmdlet etapa 2 falhará.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando e monitorando o Serviço de Backup no Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Fazendo failover de um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Failback de pool no Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Failover de banco de dados espelhado no Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Failover do pool de Borda usado para federação do Servidor Lync no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Failover do pool de Borda usado para federação de XMPP no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Failback do pool de Borda usado para federação do Lync Server ou federação XMPP no Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Alterando o Pool de borda associado ao pool Front-End no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Restaurando conteúdos de conferência usando o Serviço de Backup no Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

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

