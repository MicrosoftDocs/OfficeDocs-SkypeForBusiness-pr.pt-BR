---
title: 'Lync Server 2013: alta disponibilidade do servidor back-end'
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
ms.openlocfilehash: 7abdbfef9aefb556646c8221ee54e699e3f46e3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Alta disponibilidade de servidor back-end no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-08-12_

Para garantir a alta disponibilidade para seus servidores de back-end, você pode usar o espelhamento síncrono do SQL ou o cluster SQL. Usando uma dessas soluções opcional, mas é recomendável manter a continuidade de negócios da sua organização. O espelhamento SQL assíncrono não tem suporte para alta disponibilidade do servidor back-end no Lync Server 2013. No resto deste documento, o espelhamento SQL significa espelhamento SQL sincronizado, a não ser explicitamente declarado.

Você pode configurar facilmente o espelhamento do SQL com o construtor de topologias. Para o cluster de failover do SQL, você deve usar o SQL Server para configuração.

Se você usar o espelhamento de SQL ou SQL em um pool que esteja emparelhado com outro pool de front-ends para recuperação de desastres, deverá usar a mesma solução de alta disponibilidade de back-end em ambos os pools. Você não deve emparelhar um pool usando o espelhamento SQL com um pool usando o cluster do SQL.

Quando você implanta o espelhamento do SQL, todos os bancos de dados do Lync Server no pool são espelhados, incluindo o repositório de gerenciamento central, se ele estiver localizado nesse pool, bem como o banco de dados de aplicativo do grupo de resposta e o banco de dados do aplicativo de estacionamento de chamada, se esses aplicativos estão em execução no pool.

Com o espelhamento SQL, você não precisa usar o armazenamento compartilhado para servidores. Cada servidor mantém sua cópia dos bancos de dados no armazenamento local.

Você pode escolher implantar espelhamento SQL com ou sem uma testemunha. Recomendamos usar uma testemunha porque habilita o failover do Servidor de Back-End como automático. De outra forma, um administrador deve invocar manualmente o failover. Observe que mesmo se uma testemunha é implantada, um administrador pode invocar manualmente o failover do Servidor de Back-End, se necessário.

Se você usar uma testemunha, é possível utilizar uma única testemunha para vários pares de Servidores de Back-End. Não há correspondência exata entre testemunhas e pares de Servidores de Back-End. As implantações usam uma única testemunha para vários pares de Servidores de Back-End não são tão resilientes quanto topologias com uma testemunha separada para cada par de Servidor de Back-End.

Para obter mais informações sobre o suporte a agrupamento do SQL, confira [suporte a software de banco de dados no Lync Server 2013](lync-server-2013-database-software-support.md). Para obter detalhes sobre como implantar o cluster SQL, consulte [Configure SQL Server clustering for Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>Tempo de recuperação para failover automático do servidor back-end com espelhamento SQL

Para failover automático de back-end com espelhamento de SQL, o objetivo da engenharia para o objetivo de tempo de recuperação (RTO) é de 5 minutos. Como o espelhamento SQL sincronizado, não antecipamos a perda de dados durante as falhas do Servidor de Back-End, exceto em raras ocasiões quando os Servidores de Front-End e Servidor de Back-End saem simultaneamente enquanto os dados estão sendo movidos entre os servidores. A meta de engenharia para o objetivo de ponto de recuperação (RPO) é de 5 minutos.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>Experiência do usuário durante falha do servidor back-end com espelhamento de SQL

Experiência do usuário durante uma falha depende da natureza falha e da sua topologia.

Se você usar o espelhamento SQL e tiver uma testemunha configurada e a entidade falhar, o failover do servidor back-end ocorrerá de forma automática e rápida. Os usuários ativos não devem observar muita interrupção em suas sessões contínuas.

Se não há uma testemunha configurada, pode levar algum tempo para o administrador invocar manualmente o failover. Durante este tempo, os usuários ativos podem ser afetados. Eles continuam suas sessões normalmente por cerca de 30 minutos. Se o principal ainda não for restaurado ou se um administrador não tiver feito failover para o backup, os usuários serão alternados para o modo de resiliência, significando que eles não podem executar tarefas que exijam uma alteração persistente no Lync Server (como adicionar um contato).

Se o diretor e o Servidor de Back-End espelho falharem ou se um destes servidores e a testemunha falharem, o Servidor de Back-End se tornará indisponível (mesmo se o diretor ainda estiver funcionando). Neste caso, os usuários ativos são mudados para o modo Resiliência após algum tempo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

