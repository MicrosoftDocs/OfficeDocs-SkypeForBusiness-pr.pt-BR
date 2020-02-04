---
title: 'Lync Server 2013: Topologias e componentes para Servidores Front-End, serviço de mensagens instantâneas e presença'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 181ae682ec5ee1352c5d4f4280b4164fbbcd91f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Topologias e componentes para Servidores Front-End, serviço de mensagens instantâneas e presença no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-10-24_

Os únicos componentes necessários para mensagem instantânea (IM) e presença são:

  - Servidores front-end da sua organização ou servidores Standard Edition. As capacidades de IM e presença estão sempre habilitadas nesses servidores.

  - Um balanceador de carga, se você tiver um pool de Front-Ends do Enterprise Edition. Para obter mais informações, consulte [requisitos de balanceamento de carga do Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>Planejando a implantação de pools de front-end

No Lync Server 2013, a arquitetura de pool de front-end mudou e essas alterações afetam como você deve planejar e manter seus pools de front-end.

Recomendamos que todos os seus pools do front-end da Enterprise Edition incluam pelo menos três servidores front end. No Lync Server, a arquitetura dos pools front-ends usa um modelo de sistema distribuído, com os dados de cada usuário mantidos em três servidores front-end no pool. Para obter mais informações sobre essa nova arquitetura, consulte [alterações de topologia no Lync Server 2013](lync-server-2013-topology-changes.md).

Se você não quiser implantar três servidores de front-end do Enterprise Edition e quiser a recuperação de desastres, recomendamos usar o Lync Server Standard Edition e criar dois pools com uma relação de backup emparelhada. Isso permitirá uma solução de recuperação de desastres com apenas dois servidores. Para obter mais informações, em topologias e recursos de alta disponibilidade e recuperação de desastres, consulte [planejando a alta disponibilidade e a recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>Planejamento para o gerenciamento de pools front-end

Para os pools front-end, siga as diretrizes desta seção.

<div>

## <a name="ensuring-that-pools-are-functional"></a>Garantindo que os pools sejam funcionais

Com o novo modelo distribuído para grupos de front-end, determinados números de servidores de um pool devem estar em execução para que o pool funcione. Há dois modos de perda para um pool

  - Perda de quórum no nível do grupo de roteamento, causada por servidores de réplica insuficientes para um grupo de roteamento em particular. Um grupo de roteamento é uma agregação de um conjunto de usuários hospedados no pool. Cada grupo de roteamento tem três réplicas no pool: uma primária e duas secundárias.

  - Perda de quórum no nível do pool, causada quando um número insuficiente de servidores de propagação está em execução no pool.

<div>

## <a name="routing-group-level-quorum-loss"></a>Perda de quórum no nível do grupo de roteamento

A primeira vez que você iniciar um novo Pool de Front-Ends, é essencial que 85% dos servidores estejam em execução, conforme exibido na tabela a seguir. Se menos servidores estiverem em execução, os serviços poderão ficar parados no estado inicial e o pool pode não iniciar.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores no pool</th>
<th>Número de servidores que devem estar em execução para que o pool seja iniciado na primeira vez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p>8</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>9</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>254</p></td>
<td><p>8</p></td>
</tr>
<tr class="even">
<td><p>11:00</p></td>
<td><p>9</p></td>
</tr>
<tr class="odd">
<td><p>12</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


Cada vez subsequente que o pool for iniciado, 85% dos servidores devem ser iniciados (conforme exibido na tabela anterior). Caso não seja possível iniciar esse número de servidores (mas servidores suficientes podem ser iniciados para que não haja perda de quórum no nível do pool), é possível usar o cmdlet **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** para permitir que o pool se recupere dessa perda de quórum no nível do grupo de roteamento e faça progresso. Para obter mais informações sobre como usar esse cmdlet, consulte [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).

<div>


> [!NOTE]  
> Como o Lync Server usa o banco de dados SQL principal como testemunha, se você desligar o banco de dados principal e alternar para a cópia espelhada e desligar servidores de front-end suficientes para que não sejam executados de acordo com a tabela anterior, todo o pool será desativado. Para obter mais informações, consulte <A href="http://go.microsoft.com/fwlink/?linkid=393672">testemunha de espelhamento de banco de dados</A>.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>Perda de quórum no nível do pool

Para que um pool de front-end funcione, ele não pode estar em perda de quorum no nível do pool. Se o número de servidores em execução ficar abaixo do nível funcional, conforme mostrado na tabela a seguir, os servidores restantes do pool pararão todos os serviços do Lync Server. Observe que os números na tabela a seguir pressupõem que os servidores back-end do pool estejam em execução.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores front-end no pool</th>
<th>Número de servidores que devem estar em execução para o pool ser funcional</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>Qualquer um dos 2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>Qualquer um dos 3</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>Qualquer um dos 4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>Qualquer um dos 4 dos 7 primeiros servidores</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>Qualquer um dos 5 dos 9 primeiros servidores</p></td>
</tr>
</tbody>
</table>


Na tabela anterior, os “primeiros servidores” são aqueles criados primeiro, cronologicamente, quando o pool foi iniciado pela primeira vez. Para determinar esses servidores, você pode usar o cmdlet **Get-CsComputer** com a opção **– PoolFqdn** . Esse cmdlet exibirá os servidores na ordem em que aparecem na topologia, e aqueles que aparecem no topo da lista são os primeiros servidores.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>Pools de front-end com dois servidores front end

Não recomendamos implantar um pool de front-end que contenha apenas dois servidores front-end. Se você precisar implantar tal pool, siga estas diretrizes:

  - Se um dos dois servidores front-ends ficar inativo, tente trazer o servidor com falha para o backup assim que possível. Da mesma forma, se você precisar atualizar um dos dois servidores, ative-o assim que a atualização terminar.

  - Se por alguma razão você precisar desativar ambos os servidores ao mesmo tempo, realize o seguinte procedimento quando o tempo de inatividade do pool for concluído:
    
      - A prática recomendada é reiniciar os dois servidores front-end ao mesmo tempo.
    
      - Se os dois servidores não podem ser reiniciados ao mesmo tempo, você deve ativá-los na ordem contrária em que foram desativados.
    
      - Se não for possível recolocá-los nesse pedido, use o cmdlet a seguir antes de trazer o pool para o backup:.
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>Etapas adicionais para garantir que os pools sejam funcionais

Observe alguns outros fatores para garantir que seus Pools de Front-Ends permaneçam funcionais.

  - Quando você mover usuários para o pool pela primeira vez, certifique-se de que pelo menos três dos servidores front-end estejam em execução.

  - Se você estabelecer uma relação de emparelhamento entre este pool e outro pool para fins de recuperação de desastre, depois de estabelecer essa relação, você deve ter certeza de que esse pool tem três servidores front-ends sendo executados simultaneamente em algum momento para sincronizar corretamente dados com o pool de backup. Para obter mais informações sobre emparelhamento de pool e recursos de recuperação de desastre, consulte [planejando alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>Melhorar a confiabilidade de atualizações de pool

Quando precisar atualizar ou corrigir os servidores em um pool Front-end, siga o fluxo de trabalho exibido em [atualizar ou atualizar servidores front-end no Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)e as seguintes diretrizes:

  - Quando você passa de um domínio de atualização para outro para obter atualizações (seguindo o fluxo de trabalho em [atualizar ou atualizar servidores front-end no Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), você usará o cmdlet **Get-CsPoolUpgradeReadinessState** e verificará o estado pronto. Adicionar uma espera de 20 minutos entre cada domínio de atualização depois que ele atinge "pronto" torna as atualizações mais confiáveis. Se ele **não estiver pronto** durante estes 20 minutos, reinicie o temporizador de 20 minutos. Além disso, você pode executar o cmdlet **Get-CsPoolFabricState** antes e depois de iniciar o intervalo de 20 minutos e verificar se não há alterações nas primrias e nos secundários dos grupos de roteamento.

  - Não vá para o próximo domínio de atualização se algum dos servidores no último domínio de atualização corrigido estiver preso ou não for reiniciado. Isso também se aplica se não for possível iniciar qualquer um dos servidores de uma atualização. Execute **Get-CsPoolFabricState** para garantir que todos os grupos de roteamento tenham um principal e pelo menos um secundário; Isso irá confirmar se todos os usuários têm serviço.

  - Se alguns usuários tiverem serviços e outros não, execute **Get-CsPoolFabricState** com a opção – Verbose para verificar se há grupos de roteamento com réplicas ausentes. Não reinicie o pool inteiro como a primeira etapa de solução de problemas. Para obter mais informações sobre esse cmdlet, confira [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Verifique se todas as instâncias das janelas Visualizador de eventos ou monitor de desempenho estão fechadas para instalações/desinstalações da malha do Windows.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>Alterar a configuração de um pool de front-end

Sempre que você adicionar servidores front-end a um pool ou removê-los do pool e depois publicar a nova topologia, siga estas diretrizes:

  - Após a publicação da nova topologia, você deve reiniciar cada servidor front-end no pool. Reinicie todos, um de cada vez.

  - Se o pool inteiro estiver inoperante durante a alteração de configuração, execute o seguinte cmdlet após a publicação da nova topologia:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Se um servidor front-end falhar e for improvável de ser substituído por alguns dias ou mais, remova o servidor da topologia. Adicione o novo servidor front-end à topologia quando ele estiver disponível novamente.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

