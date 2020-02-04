---
title: 'Lync Server 2013: back-end servidor back-up alta disponibilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Back-end Server alta disponibilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-08-12_

Para garantir alta disponibilidade para seus servidores back-end, você pode usar o espelhamento do SQL síncrono ou o agrupamento do SQL. Usar uma dessas soluções opcional, mas é recomendável manter a continuidade de negócios da sua organização. O espelhamento SQL assíncrono não é compatível com o back-end do servidor back-end no Lync Server 2013. No restante deste documento, o espelhamento do SQL significa o espelhamento síncrono do SQL, a menos que explicitamente declarado de outra forma.

Você pode facilmente configurar o espelhamento do SQL com o construtor de topologias. Para o cluster de failover SQK, você deve usar o SQL Server para a configuração.

Se você usa o SQL Mirroring ou SQL cluster em um pool que está emparelhado com outro pool de front-end para recuperação de desastres, você deve usar a mesma solução de alta disponibilidade de back-end nos dois pools. Você não deve emparelhar um pool usando o espelhamento do SQL com um pool usando o agrupamento do SQL.

Quando você implanta o espelhamento do SQL, todos os bancos de dados do Lync Server no pool são espelhados, incluindo o repositório de gerenciamento central, se estiverem localizados nesse pool, bem como o banco de dados de aplicativo do grupo de resposta e o banco de dados do aplicativo de estacionamento de chamadas, se esses aplicativos estão em execução no pool.

Com o espelhamento do SQL, você não precisa usar o armazenamento compartilhado para os servidores. Cada servidor mantém sua cópia dos bancos de dados no armazenamento local.

Você pode optar por implantar o espelhamento do SQL com ou sem uma testemunha. Recomendamos usar uma testemunha porque isso habilita o failover do Servidor Back-End como automático. Caso contrário, um administrador terá que invocar manualmente o failover. Observe que mesmo se uma testemunha for implantada, um administrador pode invocar manualmente o failover do Servidor Back-End, se necessário.

Se você usar uma testemunha, poderá utilizar uma única testemunha para vários pares de Servidores Back-End. Não há correspondência exata entre testemunhas e pares de Servidores Back-End. As implantações que usam uma única testemunha para vários pares de Servidores Back-End não são tão resilientes quanto as topologias com uma testemunha separada para cada par de Servidores Back-End.

Para obter mais informações sobre o suporte a agrupamento do SQL, consulte [suporte a software de banco de dados no Lync Server 2013](lync-server-2013-database-software-support.md). Para obter detalhes sobre a implantação do SQL clustering, consulte [Configurar o cluster do SQL Server para o Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>Tempo de recuperação para failover automático do servidor back-end com espelhamento do SQL

Para failover automático de back-end com o espelhamento do SQL, o objetivo da engenharia do RTO do tempo de recuperação (RTO) é de cinco minutos. Devido ao espelhamento síncrono do SQL, não antecipamos a perda de dados durante falhas de servidor back-end, exceto em raras ocasiões em que os servidores front-end e o back-end do servidor back-end simultaneamente enquanto os dados estão sendo movidos entre os servidores. A meta de engenharia para o objetivo do ponto de recuperação (RPO) é de 5 minutos.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>Experiência do usuário durante a falha do servidor back-end com o espelhamento do SQL

A experiência do usuário durante uma falha depende da natureza da falha e da topologia.

Se você usar o espelhamento do SQL e tiver uma testemunha configurada, e o principal falhar, o failover do servidor back-end ocorrerá de forma automática e rápida. Os usuários ativos não devem notar a interrupção em suas sessões contínuas.

Se não houver uma testemunha configurada, pode levar algum tempo para o administrador invocar manualmente o failover. Durante este tempo, os usuários ativos podem ser afetados. Eles continuam suas sessões normalmente por cerca de 30 minutos. Se o principal ainda não for restaurado ou se um administrador não tiver failover para o backup, os usuários terão alternado para o modo de resiliência, o que significa que eles não poderão executar tarefas que exijam uma alteração persistente no Lync Server (como adicionar um contato).

Se o servidor principal e o Servidor Back-End espelho falharem ou se um desses servidores e a testemunha falharem, o Servidor Back-End se tornará indisponível (mesmo se o servidor principal ainda estiver funcionando). Nesse caso, os usuários ativos serão transferidos para o modo de Resiliência após um certo tempo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

