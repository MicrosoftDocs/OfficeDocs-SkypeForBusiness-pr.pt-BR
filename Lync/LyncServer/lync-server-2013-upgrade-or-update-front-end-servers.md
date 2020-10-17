---
title: 'Lync Server 2013: atualizar ou atualizar servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a537dc701f7b3e613cc9364c786cb561cadb50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530318"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Atualizar ou atualizar servidores front-end no Lync Server 2013

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-06-28_

Os Servidores de Front-End em um pool do Enterprise Edition são organizados nos *domínios de atualização*. Estes são subconjuntos de Servidores de Front-End no pool. Os domínios de atualização são criados automaticamente pelo construtor de topologias.

Ao atualizar servidores, você deve fazer isso um domínio de atualização por vez. Coloque cada servidor em um domínio de atualização para baixo, atualize-o e reinicie-o antes de passar para outro domínio de atualização. Certifique-se de acompanhar quais domínios e servidores de atualização foram atualizados até o momento. Use o diagrama de fluxograma a seguir ao atualizar cada servidor.

![Atualizar servidores Front End](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar uma atualização aos servidores front-end em um pool

1.  Em um Servidor de Front-End no pool, execute o seguinte cmdlet:
    
    **Get-CsPoolUpgradeReadinessState**
    
    Se o valor de *PoolUpgradeState* estiver **ocupado**, aguarde 10 minutos e tente **Get-CsPoolUpgradeReadinessState** novamente. Se você vir **ocupado** por pelo menos três vezes consecutivas, após aguardar 10 minutos entre cada tentativa ou se vir qualquer resultado de **InsufficientActiveFrontEnds** para **PoolUpgradeState,** haverá um problema com o pool. Se este pool está emparelhado com outro pool de Front-End em uma topologia de recuperação de desastres, deve falhar o pool sobre o pool de backup e atualizar os servidores neste pool. Para obter detalhes, consulte [failover de um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Se o valor de *PoolUpgradeState* é **Pronto**, vá para a etapa 2.

2.  O cmdlet **Get-CsPoolUpgradeReadinessState** também retorna informações sobre cada domínio de atualização no pool e sobre quais servidores front-end estão em cada domínio de atualização. Se o valor **ReadyforUpgrade** for **true** para o domínio de atualização que contém o servidor ou os servidores que você deseja atualizar, você pode atualizar esses servidores com segurança agora. Para fazer isso, execute:
    
    1.  Interrompa novas conexões com os servidores front-end que você vai atualizar usando o `Stop-CsWindowsService -Graceful -Verbose` cmdlet.
        
        <div>
        

        > [!NOTE]  
        > Se estiver executando essas atualizações de servidor durante um tempo de inatividade do servidor agendado, você pode executar esse cmdlet sem o parâmetro '-<STRONG>normal</STRONG>', da seguinte maneira: <STRONG>Stop-CsWindowsService</STRONG>. Isso fechará imediatamente os serviços, sem esperar que todas as solicitações de serviço existentes sejam preenchidas.

        
        </div>
    
    2.  Atualize os servidores associados a este domínio de atualização.
    
    3.  Reinicie os servidores e verifique se eles estão aceitando novas conexões.

3.  Repita as etapas 1 e 2 para cada outro domínio de atualização no pool, até que todos os servidores front-end tenham sido atualizados.

</div>

</div>

<span> </span>

</div>

</div>

</div>

