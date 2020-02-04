---
title: Experiência do usuário do Lync Server 2013 durante falha de pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6506ac67415ca19b33ee968d698d0ed574df8d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Experiência do usuário durante uma falha de pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

Se um pool tiver failover, todos os usuários do pool afetado serão forçados a se desconectarem e entrarem no pool de backup. Por um curto período os usuários que entram no pool de backup podem estar no modo de resiliência. No modo de resiliência, os usuários não conseguem executar tarefas que poderiam causar uma alteração persistente no Lync Server, como adicionar um contato. Após a conclusão do failover, todos os usuários podem obter todos os serviços do pool de backup.

Todas as sessões que um usuário tenha quando o pool falhar, e o usuário deve restabelecer essas sessões após o failover para continuar.

Os usuários não são hospedados novamente durante o failover ou o failback. Os usuários que são hospedados em um pool que falha serão atendidos temporariamente pelo pool de backup. Quando o pool inicial é restaurado, o administrador pode fazer failback para que esses usuários sejam atendidos pelo pool inicial original.

Observação no Lync 2013, o banco de dados do servidor de informações de localização não é replicado para o pool de backup. Como prática recomendada, o administrador deve efetuar regularmente o backup do banco de dados LIS e usar a cópia de backup mais recente para restaurar o banco de dados LIS no pool de backup depois do failover.

<div>

## <a name="user-experience-during-failover"></a>Experiência do usuário durante o failover

Quando um usuário está em um pool que falha, o usuário é desconectado. Qualquer sessão ponto a ponto na qual o usuário estava participando foi encerrada, assim como as conferências organizadas por esse usuário. o usuário não pode se conectar até o temporizador de resiliência do registrador expirar ou o administrador iniciar procedimentos de failover, o que ocorrer primeiro. Quando o usuário entrar novamente, isso ocorrerá no pool de backup. Se entrarem antes da conclusão do failover, estarão no modo Resiliência até a conclusão do failover. Somente o usuário poderá estabelecer novas sessões ou restabelecer sessões anteriores.

</div>

<div>

## <a name="user-experience-during-failback"></a>Experiência do usuário durante o failback

O failback de pool pode ocorrer enquanto um usuário afetado é conectado ao pool de backup e o usuário permanece conectado e trabalhando durante o failback. Observe que o processo de failback demora vários minutos para ser concluído.Para referência, a expectativa é de até 60 minutos para um pool de 20.000 usuários.

As tabelas a seguir mostram mais detalhes sobre como um usuário com um cliente do Lync 2013 ou um cliente do Microsoft Lync 2010 é afetado durante e após o failback, e também como os usuários em outros pools vêem e interagem com um usuário em um pool com falha de volta. Os usuários com os clientes do Microsoft Office Communicator 2007 R2 não podem entrar até que o pool de front-end tenha falhado completamente novamente.)

O termo *usuários afetado* se refere a qualquer usuário que sofreu failover no pool de hospedagem e está sendo atendido pelo pool de backup. Por definição, qualquer usuário originalmente hospedado no pool de backup não é um usuário afetado.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>Experiência do usuário para um usuário afetado em um pool em failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Estado do usuário ou tarefa</th>
<th>Durante o failback</th>
<th>Após a conclusão do failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Estado do usuário do usuário já conectado</p></td>
<td><p>O usuário permanece conectado e conectado ao pool de backup. Em algum usuário, o usuário será desconectado e se conectará novamente ao pool inicial original, no modo de resiliência.</p></td>
<td><p>O usuário permanece conectado e entra no modo normal.</p></td>
</tr>
<tr class="even">
<td><p>Novo logon de usuário</p></td>
<td><p>O usuário pode entrar no pool de Home no modo de resiliência.</p></td>
<td><p>O usuário pode entrar no pool inicial original em modo normal.</p></td>
</tr>
<tr class="odd">
<td><p>Conferências em andamento organizadas por um usuário afetado</p></td>
<td><p>Todas as modalidades de conferência são encerradas. Botão reingressar aparecerá, mas nenhum usuário poderá se reconectar enquanto o usuário afetado estiver no modo de resiliência.</p></td>
<td><p>Todas as modalidades agora funcionam. Todos os participantes devem clicar para reingressar na conferência.</p></td>
</tr>
<tr class="even">
<td><p>Conferências em andamento organizadas por um usuário não afetado</p></td>
<td><p>A conferência continua e o usuário afetado pode permanecer na conferência. O usuário afetado está restrito ao que ele/ela pode fazer no modo de resiliência.</p></td>
<td><p>A conferência continua, e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam após o usuário sair do modo de resiliência.</p></td>
</tr>
<tr class="odd">
<td><p>Agendando ou modificando reuniões agendadas, criando conferências ad hoc</p></td>
<td><p>Não é possível enquanto o usuário está no modo de resiliência.</p></td>
<td><p>Disponível para todas as modalidades.</p></td>
</tr>
<tr class="even">
<td><p>Presença como vista por outros usuários no mesmo pool</p></td>
<td><p>Presença desconhecida enquanto o usuário está conectado ao pool de backup durante o modo de resiliência.</p></td>
<td><p>Mostra o último estado de presença definido pelo usuário e as alterações de presença agora serão refletidas.</p></td>
</tr>
<tr class="odd">
<td><p>Lista de contatos e disponibilidade do serviço de catálogo de endereços</p></td>
<td><p>Não disponível</p></td>
<td><p>Disponível</p></td>
</tr>
<tr class="even">
<td><p>Todas as sessões ponto a ponto e modalidades</p></td>
<td><p>Disponível</p></td>
<td><p>Disponível</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>Experiência do usuário para um usuário hospedado em um pool não afetado durante o failback de outro pool

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarefa do usuário</th>
<th>Durante o failback</th>
<th>Após a conclusão do failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Visualizando a presença de um usuário afetado</p></td>
<td><p>Mostra o último estado de presença definido pelo usuário afetado.</p></td>
<td><p>Trabalhando. Usuários não afetados Veja as atualizações feitas por usuários afetados.</p></td>
</tr>
<tr class="even">
<td><p>Conferências em andamento organizadas por um usuário afetado</p></td>
<td><p>Todas as modalidades de conferência são encerradas.</p></td>
<td><p>Todas as modalidades agora funcionam. Todos os participantes devem clicar para reingressar na conferência.</p></td>
</tr>
<tr class="odd">
<td><p>Conferências em andamento organizadas por um usuário não afetado</p></td>
<td><p>A conferência continua, e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.</p></td>
<td><p>A conferência continua, e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.</p></td>
</tr>
<tr class="even">
<td><p>Todas as sessões ponto a ponto e modalidades</p></td>
<td><p>Disponível</p></td>
<td><p>Disponível</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

