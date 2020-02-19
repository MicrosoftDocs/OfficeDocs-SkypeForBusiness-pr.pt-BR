---
title: 'Lync Server 2013: topologias e componentes para servidores front-end, mensagens instantâneas e presença'
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
ms.openlocfilehash: e2865d1a4169491751643e7b16601a5ed3efcded
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-10-24_

Os únicos componentes necessários para mensagem instantânea (IM) e presença são:

  - Os servidores do front-end da sua organização ou servidores do Standard Edition. As capacidades de IM e presença estão sempre habilitadas nestes servidores.

  - Um balanceador de carga, se você tiver um pool de front-ends Enterprise Edition. Para obter mais informações, consulte [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>Planejando a implantação de pools de Front Ends

No Lync Server 2013, a arquitetura do pool de front-ends foi alterada e essas alterações afetam o modo como você deve planejar e manter seus pools de front-ends.

Recomendamos que todos os pools de front-ends Enterprise Edition incluam pelo menos três servidores front-end. No Lync Server, a arquitetura dos pools de front-ends usa um modelo de sistemas distribuídos, com os dados de cada usuário mantidos em três servidores front-end no pool. Para obter mais informações sobre essa nova arquitetura, consulte [Topology Changes in Lync Server 2013](lync-server-2013-topology-changes.md).

Se você não quiser implantar três servidores de front-end Enterprise Edition e quiser a recuperação de desastres, recomendamos usar o Lync Server Standard Edition e criar dois pools com um relacionamento de backup emparelhado. Isso fornecerá uma solução de recuperação de desastres com apenas dois servidores. Para obter mais informações, sobre topologias e recursos de alta disponibilidade e recuperação de desastres, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>Planejando o gerenciamento de pool de Front Ends

Para pools de front-ends, siga as diretrizes desta seção.

<div>

## <a name="ensuring-that-pools-are-functional"></a>Garantir que os pools sejam funcionais

Com o novo modelo distribuído para pools de front-ends, determinados números de servidores de um pool devem estar em execução para que o pool funcione. Há dois modos de perda para um pool

  - Perda de quorum de nível de grupo de roteamento, causada por servidores de réplica insuficientes para um grupo de roteamento específico. Um grupo de roteamento é uma agregação de um conjunto de usuários hospedados no pool. Cada grupo de roteamento tem três réplicas no pool: uma principal e duas segundas.

  - Perda de quorum no nível do pool, causada quando não há servidores semente suficientes em execução no pool.

<div>

## <a name="routing-group-level-quorum-loss"></a>Perda de quórum no nível do grupo de roteamento

Na primeira vez que você iniciar um novo pool de front-ends, é essencial que 85% dos servidores estejam em funcionamento, conforme mostrado na tabela a seguir. Se menos servidores estiverem em execução, os serviços poderão estar presos no estado inicial e o pool pode não iniciar.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores no pool</th>
<th>Número de servidores que devem estar em execução para que o pool seja iniciado pela primeira vez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>duas</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3D</p></td>
<td><p>3D</p></td>
</tr>
<tr class="odd">
<td><p>quatro</p></td>
<td><p>3D</p></td>
</tr>
<tr class="even">
<td><p>0,5</p></td>
<td><p>quatro</p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>0,5</p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>0,5</p></td>
</tr>
<tr class="odd">
<td><p>8 </p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>9 </p></td>
<td><p>7 </p></td>
</tr>
<tr class="odd">
<td><p>10 </p></td>
<td><p>8 </p></td>
</tr>
<tr class="even">
<td><p>11 </p></td>
<td><p>9 </p></td>
</tr>
<tr class="odd">
<td><p>12</p></td>
<td><p>10 </p></td>
</tr>
</tbody>
</table>


Cada vez subsequente que o pool é iniciado, 85% dos servidores devem ser iniciados (conforme mostrado na tabela anterior). Se esse número de servidores não puder ser iniciado (mas servidores suficientes podem ser iniciados para que você não esteja em perda de quorum no nível do pool), você pode usar o cmdlet **Reset-CsPoolRegistrarState – resettype QuorumLossRecovery** para permitir que o pool se recupere dessa perda de quorum de nível do grupo de roteamento e faça o andamento. Para obter mais informações sobre como usar esse cmdlet, consulte [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).

<div>


> [!NOTE]  
> Como o Lync Server usa o banco de dados SQL principal como testemunha, se você desligar o banco de dados primário e alternar para a cópia espelho e desligar servidores front-end suficientes para que não sejam executados de acordo com a tabela anterior, todo o pool será desativado. Para obter mais informações, consulte <A href="https://go.microsoft.com/fwlink/?linkid=393672">testemunha de espelhamento de banco de dados</A>.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>Perda de quorum no nível do pool

Para que um pool de front-ends funcione, ele não pode ficar em perda de quorum no nível do pool. Se o número de servidores em execução estiver abaixo do nível funcional, conforme mostrado na tabela a seguir, os servidores restantes do pool serão interrompidos em todos os serviços do Lync Server. Observe que os números na tabela a seguir pressupõem que os servidores de back-end no pool estão em execução.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de Servidores de Front End no pool</th>
<th>Número de servidores que devem estar em execução para o pool ser funcional</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>duas</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>Qualquer 2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>Qualquer 3</p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>Qualquer 4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>Quatro dos primeiros sete servidores</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>Qualquer 5 dos primeiros 9 servidores</p></td>
</tr>
</tbody>
</table>


Na tabela anterior, os "primeiros servidores" são os servidores que foram inicialmente exibidos, cronologicamente, quando o pool foi iniciado pela primeira vez. Para determinar esses servidores, você pode usar o cmdlet **Get-CsComputer** com a opção **– PoolFqdn** . Este cmdlet mostrará os servidores na ordem em que eles aparecem na topologia e aqueles que estão na parte superior da lista são os primeiros servidores.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>Pool de Front-Ends com dois Servidores de Front End

Não recomendamos implantar um pool de Front Ends que contém apenas dois Servidores de Front End. Se você precisar implantar este tipo de pool, siga as seguintes orientações:

  - Se um dos dois Servidores de Front End ficar inativo, você deve ativá-lo assim que possível. Da mesma forma, se você precisar atualizar um dos dois servidores, ative-o assim que a atualização terminar.

  - Se por alguma razão você precisar desativar ambos os servidores ao mesmo tempo, realize o seguinte procedimento quando o tempo de inatividade do pool for concluído:
    
      - A prática recomendada é reiniciar ambos os servidores front-end ao mesmo tempo.
    
      - Se os dois servidores não podem ser reinicidos ao mesmo tempo, você deve ativá-los na ordem contrária em que foram desativados.
    
      - Se você não puder ativá-los nesta ordem, use o seguinte cmdlet antes de ativar o pool:
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>Etapas adicionais para garantir que os pools sejam funcionais

Você deve observar alguns outros fatores para garantir que seus pools de front-ends permaneçam funcionais.

  - Ao migrar usuários para o pool pela primeira vez, certifique-se de que pelo menos três dos Servidores de Front End estão em execução.

  - Se você estabelecer um relacionamento de emparelhamento entre este e um outro pool para fins de recuperação de desastres, após estabelecer esse relacionamento você deve garantir que o pool tenha três Servidores de Front End em execução simultânea em algum momento para sincronizar adequadamente os dados com o pool de backup. Para obter mais informações sobre emparelhamento de pool e recursos de recuperação de desastre, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>Melhorar a confiabilidade das atualizações de pool

Quando precisar atualizar ou corrigir os servidores em um pool de front-ends, siga o fluxo de trabalho mostrado em [atualizar ou atualizar servidores front-end no Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)e as seguintes diretrizes:

  - Quando você migra de um domínio de atualização para outro para atualizações (seguindo o fluxo de trabalho em [atualizar ou atualizar servidores front-end no Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), você usará o cmdlet **Get-CsPoolUpgradeReadinessState** e verificará se o estado está pronto. A adição de uma espera de 20 minutos entre cada domínio de atualização após o alcance de "pronto" tornará as atualizações mais confiáveis. Se ele **não estiver pronto** durante os 20 minutos, reinicie o timer de 20 minutos. Além disso, você pode executar o cmdlet **Get-CsPoolFabricState** antes e depois de iniciar o intervalo de 20 minutos e certificar-se de que não haja alterações nas primidades e nos secundários de grupos de roteamento.

  - Não vá para o próximo domínio de atualização se qualquer um dos servidores no último domínio de atualização corrigido estiver preso ou não for reiniciado. Isso também se aplica se não for possível iniciar qualquer um dos servidores de uma atualização. Execute **Get-CsPoolFabricState** para certificar-se de que todos os grupos de roteamento têm um primário e pelo menos um secundário; isso confirmará se todos os usuários possuem serviço.

  - Se alguns usuários tiverem serviços e outros não, execute **Get-CsPoolFabricState** com a opção – Verbose para verificar os grupos de roteamento que possuem réplicas ausentes. Não reinicia o pool inteiro como a primeira etapa de solução de problemas. Para obter mais informações sobre esse cmdlet, consulte [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Certifique-se de que todas as instâncias das janelas Visualizador de eventos ou monitor de desempenho estejam fechadas para instalar/desinstalar o Windows Fabric.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>Alterando a configuração de um Pool de Front Ends

Sempre que você adicionar ou remover Servidores de Front End de um pool, e depois publicar a nova topologia, siga essas orientações:

  - Após a publicação da nova topologia, você deve reiniciar cada servidor de front-end no pool. Reinicie todos eles, um de cada vez.

  - Se todo o pool ficou desativado durante a alteração nas configurações, execute o seguinte cmdlet depois de publicar a nova topologia:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Se um Servidor de Front End falhar e não puder ser substituído em alguns dias ou mais, remova o servidor da topologia. Adicione o novo Servidor de Front End à topologia quando estiver disponível novamente.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

