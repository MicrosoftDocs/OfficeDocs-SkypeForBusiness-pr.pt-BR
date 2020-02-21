---
title: Lync Server 2013 experiência do usuário durante falha do pool
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
ms.openlocfilehash: 63bef718af5664c18ccedca7482e4ca0a0a7f95e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Experiência do usuário durante falha do pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

Se um pool falhar, todos os usuários do pool afetado serão forçados a sair e entrar no pool de backup. Para um breve período, os usuários que entram no pool de backup podem estar no modo resiliência. No modo resiliência, os usuários não podem executar tarefas que poderiam causar uma alteração persistente no Lync Server, como adicionar um contato. Após a conclusão do failover, todos os usuários podem obter todos os serviços do pool de backup.

Todas as sessões que um usuário tem quando o pool falha são interrompidas, e o usuário deve restabelecer essas sessões após o failover para continuar.

Os usuários não são hospedados durante o failover ou o failback. Os usuários hospedados em um pool que falharão serão temporariamente atendidos pelo pool de backup. Quando o pool inicial é restaurado, o administrador pode fazer o failback desses usuários para serem atendidos pelo pool inicial original.

Observação no Lync 2013, o banco de dados do local Information Server não é replicado para o pool de backup. Para obter uma prática recomendada, o administrador deve fazer o backup do banco de dados LIS regularmente e usar a cópia de backup mais recente para restaurar o banco de dados LIS no pool de backup após o failover.

<div>

## <a name="user-experience-during-failover"></a>Experiência do usuário durante o failover

Quando um usuário está em um pool que falha, o usuário está desconectado. Qualquer sessão ponto a ponto na qual o usuário estava participando foi encerrada, assim como as conferências organizadas por esse usuário. O usuário não pode fazer logon novamente até que o timer de resiliência do registrador expire ou o administrador inicie procedimentos de failover, o que vier primeiro. Quando o usuário fizer logon novamente, ele fará logon no pool de backup. Se eles fizerem logon antes da conclusão do failover, eles estarão no modo de resiliência até que o failover seja concluído. Somente o usuário poderá estabelecer novas sessões ou restabelecer sessões anteriores.

</div>

<div>

## <a name="user-experience-during-failback"></a>Experiência do usuário durante o failback

O failback do pool pode acontecer enquanto um usuário afetado está conectado ao pool de backup e o usuário permanece conectado e funcionando durante o failback. O processo de failback leva vários minutos para ser concluído.Como referência, espera-se que leve até 60 minutos para um pool de 20 mil usuários.

As tabelas a seguir mostram mais detalhes sobre como um usuário com um cliente do Lync 2013 ou o Microsoft Lync 2010 é afetado durante e após o failback, e também como os usuários em outros pools vêem e interagem com um usuário em um pool que está sendo reprovado. Os usuários com o Microsoft Office Communicator 2007 R2 clients não podem entrar até que o pool de front-ends tenha falhado completamente novamente.

O termo *usuário afetado* refere-se a qualquer usuário que tenha falhado do pool local e está sendo atendido pelo pool de backup. Por definição, qualquer usuário hospedado originalmente no pool de backup não é um usuário afetado.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>Experiência do usuário para um usuário afetado em um pool de failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Estado ou tarefa do usuário</th>
<th>Durante o failback</th>
<th>Após a conclusão do failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Estado do usuário já conectado</p></td>
<td><p>O usuário permanece conectado e conectado ao pool de backup. Em algum momento, o usuário será desconectado e entrará novamente no pool local original, no modo resiliência.</p></td>
<td><p>O usuário permanece conectado e entra no modo normal.</p></td>
</tr>
<tr class="even">
<td><p>Novo logon de usuário</p></td>
<td><p>O usuário pode entrar no pool de Home no modo de resiliência.</p></td>
<td><p>O usuário pode entrar no pool local original no modo normal.</p></td>
</tr>
<tr class="odd">
<td><p>Conferências em andamento organizadas pelo usuário afetado</p></td>
<td><p>Todas as modalidades de conferência são encerradas. O botão reingressar será exibido, mas nenhum usuário poderá se reingressar enquanto o usuário afetado estiver no modo de resiliência.</p></td>
<td><p>Todas as modalidades agora funcionam. Todo participante precisa clicar para reingressar na conferência.</p></td>
</tr>
<tr class="even">
<td><p>Conferências em andamento organizadas pelo usuário não afetado</p></td>
<td><p>A conferência continua e o usuário afetado pode permanecer na conferência. O usuário afetado está restrito ao que ele pode fazer no modo resiliência.</p></td>
<td><p>A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam depois que o usuário sai do modo de resiliência.</p></td>
</tr>
<tr class="odd">
<td><p>Agendando ou modificando reuniões agendadas, criando conferências ad-hoc</p></td>
<td><p>Não é possível enquanto o usuário está no modo de resiliência.</p></td>
<td><p>Disponível para todas as modalidades.</p></td>
</tr>
<tr class="even">
<td><p>Presença como vista por outros usuários no mesmo pool</p></td>
<td><p>Presença desconhecida enquanto o usuário está conectado ao pool de backup durante o modo de resiliência.</p></td>
<td><p>Mostra o último estado de presença definido pelo usuário e as alterações de presença serão refletidas agora.</p></td>
</tr>
<tr class="odd">
<td><p>Disponibilidade de serviço de catálogo de endereços e lista de contatos</p></td>
<td><p>Não disponível</p></td>
<td><p>Disponível</p></td>
</tr>
<tr class="even">
<td><p>Todas as sessões e modalidades ponto a ponto</p></td>
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
<td><p>Exibindo a presença do usuário afetado</p></td>
<td><p>Mostra o último estado de presença definido pelo usuário afetado.</p></td>
<td><p>Trabalhando. Usuários não afetados Confira as atualizações feitas por usuários afetados.</p></td>
</tr>
<tr class="even">
<td><p>Conferências em andamento organizadas pelo usuário afetado</p></td>
<td><p>Todas as modalidades de conferência são encerradas.</p></td>
<td><p>Todas as modalidades agora funcionam. Todo participante precisa clicar para reingressar na conferência.</p></td>
</tr>
<tr class="odd">
<td><p>Conferências em andamento organizadas pelo usuário não afetado</p></td>
<td><p>A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.</p></td>
<td><p>A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.</p></td>
</tr>
<tr class="even">
<td><p>Todas as sessões e modalidades ponto a ponto</p></td>
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

