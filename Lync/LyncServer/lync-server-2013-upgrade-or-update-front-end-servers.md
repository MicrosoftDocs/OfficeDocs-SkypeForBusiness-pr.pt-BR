---
title: 'Lync Server 2013: atualizar ou atualizar servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af1680da68299881fe94244969d44fce1900532b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Upgrade or update Front End Servers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-06-28_

Os servidores de front-end em um pool da edição Enterprise são organizados em *domínios de atualização*. Esses são subconjuntos de servidores front-end no pool. Os domínios de atualização são criados automaticamente pelo construtor de topologias.

Ao atualizar os servidores, você deve fazer um domínio de atualização de cada vez. Coloque cada servidor em um domínio de atualização abaixo, atualize-o e reinicie-o antes de passar para outro domínio de atualização. Certifique-se de acompanhar quais domínios e servidores de atualização você atualizou até agora. Use o diagrama de fluxograma a seguir ao atualizar cada servidor.

:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="Atualizar ou atualizar servidores front-end":::

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Para aplicar uma atualização aos servidores Front-End em um pool

1.  Em um servidor front-end do pool, execute o seguinte cmdlet:
    
    **Get-CsPoolUpgradeReadinessState**
    
    Se o valor de *PoolUpgradeState* estiver **ocupado**, aguarde 10 minutos e tente **Get-CsPoolUpgradeReadinessState** novamente. Se você vir **ocupado** pelo menos três vezes consecutivos, após esperar 10 minutos entre cada tentativa, ou se vir qualquer resultado de **InsufficientActiveFrontEnds** para **PoolUpgradeState,** há um problema com o pool. Se esse pool estiver emparelhado com outro pool de front-ends em uma topologia de recuperação de desastre, você deverá fazer failover do pool para o pool de backup e, em seguida, atualizar os servidores nesse pool. Para obter detalhes, consulte [falha em um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Se o valor de *PoolUpgradeState* estiver **pronto**, vá para a etapa 2.

2.  O cmdlet **Get-CsPoolUpgradeReadinessState** também retorna informações sobre cada domínio de atualização do pool e sobre quais servidores de front-end estão em cada domínio de atualização. Se o valor de **ReadyforUpgrade** for **verdadeiro** para o domínio de atualização que contém o servidor ou servidores que você deseja atualizar, você pode atualizar os servidores com segurança agora. Para fazer isso, faça o seguinte:
    
    1.  Pare as novas conexões com os servidores front end que você vai atualizar usando o `Stop-CsWindowsService -Graceful -Verbose` cmdlet.
        
        <div>
        

        > [!NOTE]  
        > Se você estiver executando essas atualizações do servidor durante um tempo de inatividade do servidor programado, poderá executar esse cmdlet sem o parâmetro '-<STRONG>normal</STRONG>', da seguinte maneira: <STRONG>Stop-CsWindowsService</STRONG>. Isso encerrará imediatamente os serviços, sem esperar que todas as solicitações de serviço existentes sejam preenchidas.

        
        </div>
    
    2.  Atualize os servidores associados a este domínio de atualização.
    
    3.  Reinicie os servidores e certifique-se de que eles estejam aceitando novas conexões.

3.  Repita as etapas 1 e 2 para cada outro domínio de atualização do pool, até que todos os servidores front end tenham sido atualizados.

</div>

</div>

<span> </span>

</div>

</div>

</div>

