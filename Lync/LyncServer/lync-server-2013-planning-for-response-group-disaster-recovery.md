---
title: 'Lync Server 2013: Planejamento para recuperação de desastre de grupos de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3a196a258198fe0bc65b533841544decd96aa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Planejamento para recuperação de desastre de grupos de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Esta seção descreve algumas maneiras de preparar grupos de resposta para recuperação de desastres e fornece uma visão geral do processo de recuperação de desastres.

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>Preparando-se para recuperação de desastre do grupo de resposta

Lembre-se do seguinte ao preparar-se para e realizar procedimentos de recuperação de desastres.

<div>


> [!NOTE]  
> Em um ambiente de coexistência, somente os grupos de resposta do Lync Server 2013 são compatíveis com os procedimentos de recuperação de desastre descritos neste documento.



</div>

  - Planeje a recuperação de desastres quando você fizer o planejamento da capacidade. Para a capacidade de recuperação de desastres, cada pool em um pool emparelhado deve ser capaz de manipular as cargas de trabalho de todos os grupos de resposta em ambos os pools. Para obter detalhes sobre o planejamento da capacidade do grupo de resposta, consulte [planejamento de capacidade para o grupo de resposta no Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).

  - Faça cópias regulares de backup de todas as configurações do grupo de resposta em todos os pools de front-ends nos quais você implantou o aplicativo de grupo de resposta usando o procedimento de exportação descrito neste documento. Para obter detalhes, consulte [procedimentos de recuperação de desastres de grupo de resposta no Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md). Mantenha as cópias de backup em um local seguro.

  - Mantenha uma cópia de backup separada de todos os arquivos de áudio originais que você usou para o aplicativo do grupo de resposta, incluindo qualquer gravação e arquivos de música em espera. Mantenha os arquivos de backup em um local seguro.

  - Para a recuperação de desastre do Lync Server 2013, todas as configurações de grupo de resposta devem ter nomes exclusivos em toda a sua implantação. Esse requisito se aplica a fluxos de trabalho, filas, grupos de agente, conjuntos de feriados e horas de negócios. Você deve verificar se esse requisito é atendido quando os pools primário e de backup ainda estão ativos e antes de você precisar iniciar qualquer procedimento de failover. Se você encontrar conflitos de nome ao importar dados do grupo de resposta para o pool de backup, a importação falhará. Para concluir o procedimento de importação e failover, você precisa resolver os conflitos de nome renomeando o objeto do grupo de resposta no pool de backup ou usando o cmdlet **Import-CsRgsConfiguration** com o parâmetro – ResolveNameConflicts para resolver automaticamente o conflito, acrescentando um número exclusivo de identificação ao objeto do grupo de resposta.

  - Em geral, recomendamos que você realize backups diários, mas se você tiver um grande volume de alterações, talvez queira agendar backups mais frequentes. A quantidade de informações que você pode perder no caso de um desastre depende da frequência dos backups, bem como da frequência e do volume das alterações.

  - É possível importar grupos de resposta para um pool de backup antes que ocorra um desastre ou operação de failover. A importação de grupos de resposta com antecedência reduz o tempo de inatividade, pois o serviço do grupo de resposta do Lync Server pode ser restaurado no pool de backup assim que as chamadas são roteadas para o pool de backup.
    
    <div>
    

    > [!NOTE]  
    > O aplicativo de grupo de resposta não pode alcançar nenhum agente hospedado em um pool inativo até que o failover seja concluído. Durante esse período, o aplicativo do grupo de resposta processa chamadas como se esses agentes não estiverem disponíveis.

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>Processo de recuperação de desastre do grupo de resposta

Em caso de desastre, você pode recuperar grupos de resposta usando um dos seguintes métodos de recuperação:

  - Faça failover para um pool de backup e, em seguida, faça failback para o pool original.

  - Failover para um pool de backup, crie um novo pool com um nome de domínio totalmente qualificado (FQDN) diferente e, em seguida, importe os grupos de resposta para o novo pool.

Durante a fase de failover da recuperação de desastres, os grupos de resposta residem em vários pools: no pool primário (que não está disponível) e no pool de backup. Os grupos de resposta em ambos os pools têm o mesmo nome e o mesmo proprietário (o pool primário), mas têm pais diferentes.

Ao recuperar criando um novo pool com um FQDN diferente, você precisa atribuir o novo pool como o proprietário dos grupos de resposta quando importá-los. A propriedade dos grupos de resposta permanece com o pool original, a menos que você reatribua explicitamente a propriedade usando o parâmetro – OverwriteOwner com o cmdlet **Import-CsRgsConfiguration** .

<div>


> [!NOTE]  
> Você também precisará usar o parâmetro – OverwriteOwner se reconstruiu o pool durante a recuperação (isto é, o banco de dados do grupo de resposta está vazio), seja ou não use o mesmo FQDN. Você não precisará usar o parâmetro – OverwriteOwner se você não reconstruou o pool, mas ele é permitido para usar esse parâmetro sempre que você importar grupos de resposta de volta para o pool primário.



</div>

Você pode definir apenas um conjunto de configurações de grupo de resposta em nível de aplicativo por pool. Essas configurações incluem a configuração de música em espera padrão, o arquivo de áudio de música em espera padrão, o período de cortesia do agente e a configuração do contexto de chamada. Para exibir essas definições de configuração, execute o cmdlet **Get-CsRgsConfiguration** . Para obter detalhes sobre o cmdlet **Get-CsRgsConfiguration** , consulte [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).

Você pode transferir essas configurações no nível do aplicativo de um pool para outro usando o cmdlet **Import-CsRgsConfiguration** com o parâmetro – ReplaceExistingSettings, mas fazer isso substitui as configurações no pool de destino.

<div>


> [!IMPORTANT]  
> Essa restrição sobre a transferência de configurações para outro pool é verdadeira apenas para as configurações no nível do aplicativo e o arquivo de áudio padrão de música em espera. Ele não se aplica a grupos de agente, filas, fluxos de trabalho, horários comerciais e conjuntos de feriados.



</div>

Se você não quiser substituir as configurações no nível do aplicativo no pool de backup durante um desastre e se o pool primário não puder ser recuperado, as configurações do nível do aplicativo do pool primário serão perdidas. Se você precisar criar um novo pool para substituir o pool primário durante a recuperação, seja com o mesmo FQDN ou com um FQDN diferente, não será possível recuperar as configurações originais do nível do aplicativo. Nesse caso, você precisará configurar o novo pool com essas configurações e incluir o arquivo de áudio de música em espera.

Se você decidir usar o cmdlet **Import-CsRgsConfiguration** para transferir configurações em nível de aplicativo do pool primário para o pool de backup durante um desastre, poderá transferir as configurações do pool de backup para o novo pool durante a recuperação da mesma forma que as transferiu do pool primário para o pool de backup.

A tabela a seguir mostra uma visão geral das etapas envolvidas na recuperação de grupos de resposta.

Para obter detalhes sobre como executar essas etapas, consulte [procedimentos de recuperação de desastres de grupo de resposta no Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).

### <a name="response-group-disaster-recovery-steps"></a>Etapas de recuperação de desastre do grupo de resposta

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Grupos e funções necessários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Antes da interrupção</p></td>
<td><p>Com base em rotina, execute o cmdlet <strong>Export-CsRgsConfiguration</strong> para criar backups de todas as configurações do grupo de resposta em todos os pools front-ends em que o aplicativo do grupo de resposta é implantado.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Durante a interrupção</p></td>
<td><p>Execute o cmdlet <strong>Import-CsRgsConfiguration</strong> para importar o backup da configuração do serviço de grupo de resposta do Lync Server do pool primário para o pool de backup.</p>
<div>

> [!NOTE]  
> Use o parâmetro – ReplaceExistingSettings se você deseja substituir as configurações de grupo de resposta no nível do aplicativo no pool de backup com as configurações do pool primário. Se você não transferir as configurações no nível do aplicativo do pool primário para o pool de backup e o pool primário não puder ser recuperado, as configurações do pool primário serão perdidas.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>Após a importação</p></td>
<td><p>Execute cmdlets do grupo de resposta com o parâmetro – ShowAll (para exibir todos os grupos de resposta) ou o parâmetro – Owner (para exibir somente os grupos de resposta importados) para verificar se todas as configurações do grupo de resposta foram importadas para o pool de backup.</p>
<div>

> [!IMPORTANT]  
> Se você não usar o parâmetro – ShowAll ou o parâmetro – Owner, os grupos de resposta que você importou para o pool de backup não serão listados nos resultados retornados pelos cmdlets.


</div>
<p>Execute os seguintes cmdlets:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Após o failover</p></td>
<td><ul>
<li><p>Faça uma chamada de teste para um grupo de resposta que foi importado para o pool de backup e verifique se a chamada está manipulada corretamente.</p></li>
<li><p>Todos os agentes formais devem entrar novamente em seus grupos formais no pool de backup.</p></li>
<li><p>Gerenciar alterações de configuração:</p>
<p>Grupos de resposta no pool de backup, sejam importados para o pool de backup ou pertencentes ao pool de backup, podem ser modificados normalmente durante a interrupção.</p>
<div>

> [!IMPORTANT]  
> Você deve usar o Shell de gerenciamento do Lync Server para gerenciar os grupos de resposta importados para o pool de backup. Você não pode usar o painel de controle do Lync Server para gerenciar esses grupos de resposta enquanto eles estiverem no pool de backup.


</div></li>
</ul></td>
<td><p>Não disponível</p></td>
</tr>
<tr class="odd">
<td><p>Após a recuperação, antes do failback</p></td>
<td><p>Execute o cmdlet <strong>Export-CsRgsConfiguration</strong> especificando o parâmetro-source como o pool de backup e o parâmetro – Owner como o pool primário para exportar os grupos de resposta pertencentes ao pool primário do pool de backup.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Após o failback</p></td>
<td><ul>
<li><p>Execute o cmdlet <strong>Import-CsRgsConfiguration</strong> para importar os grupos de resposta de volta para o pool primário.</p>
<div>

> [!NOTE]  
> Se o pool primário não puder ser recuperado e você implantar um novo pool para substituí-lo, use o parâmetro – ReplaceExistingSettings para transferir as configurações no nível do aplicativo do pool de backup para o novo pool. Se você não transferir as configurações do pool de backup, o novo pool vai usar as configurações padrão.


</div></li>
<li><p>Execute os seguintes cmdlets com o parâmetro – ShowAll (para exibir todos os grupos de resposta) ou o parâmetro – Owner (para exibir somente os grupos de resposta importados) para verificar se todas as configurações do grupo de resposta foram importadas com êxito de volta para o pool primário:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>Faça uma chamada de teste para um grupo de resposta que foi importado de volta para o pool primário e verifique se a chamada está manipulada corretamente.</p></li>
<li><p>Opcionalmente, execute o cmdlet <strong>Export-CsRgsConfiguration</strong> no pool de backup com o parâmetro – RemoveExportedConfiguration para remover os grupos de resposta pertencentes ao pool primário do pool de backup.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

