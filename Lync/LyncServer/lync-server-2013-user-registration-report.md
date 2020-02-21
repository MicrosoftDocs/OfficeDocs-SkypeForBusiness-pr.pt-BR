---
title: 'Lync Server 2013: relatório de registro do usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd7ff808b766d7366e39595a46d1a2d7dfb75996
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Relatório de registro de usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-21_

O relatório de registro de usuário fornece uma visão geral da atividade de logon do usuário, mais notavelmente informações sobre o número de usuários que fizeram logon no Microsoft Lync Server 2013 durante um período de tempo especificado (por hora, diariamente, semanalmente, mensalmente). Lembre-se de que o relatório mostra apenas quantas pessoas fizeram logon. Ele não mostra *quais* pessoas fizeram logon. Os relatórios de monitoramento não fornecem informações sobre quais usuários específicos estão usando o Lync Server 2013 (e quais não são). No entanto, você pode obter uma estimativa aproximada de informações de usuário usando o Relatório de Atividades de Usuário.

Ao fornecer informações sobre logons de usuários, o Relatório de Registro de Usuário faz duas distinções importantes. Primeiro, ele desdobra os logons  em duas categorias primárias: logons internos e logons externos. Logons internos representam usuários que fizeram logon de dentro da firewall de sua organização (isto é, enquanto contectados à rede corporativa). Os logons externos representam usuários que fizeram logon de fora do firewall por meio de um servidor de borda (por exemplo, um usuário que fez logon a partir de um café da Internet, conta como um logon externo). Caso precise saber quantas de seus usuários estão fazendo logon de fora da firewall, o Relatório de Registro de Usuário pode fornecer essa informação a você.

Além disseo, o Relatório de Registro de Usuário indica quantos usuários *ativos* estavam presentes durante um dado período de tempo. Um usuário ativo é um usuário que fez parte de uma sessão de mensagens instantâneas (IM), participou de uma reunião do Lync, fez ou recebeu uma chamada telefônica, ou então usava o Lync Server durante esse período de tempo. Isso é diferente de um usuário que fez logon mas nunca realmente usou o sistema.

<div>

## <a name="accessing-the-user-registration-report"></a>Acessando o Relatório de Registro de Usuário

Você acessa o Relatório de Registro de Usuário apenas a partir da página inicial de Relatórios de Monitoramento. O Relatório de Registro de Usuário não leva a qualquer outro relatório.

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>Usando o Relatório de Registro de Usuário da melhor maneira possível

Depois de implantar o Lync Server uma pergunta frequente é esta: como saber se meus usuários estão realmente usando essa nova tecnologia? Embora tenha algumas limitações neste sentido, o Relatório de Registro de Usuário pode ajudar você a responder esta pergunta. Para determinar se os usuários estão usando o Lync Server, você precisa fazer duas coisas. Primeiro, obtenha o valor da métrica de Usuários de logon exclusivos, do Relatório de Registro de Usuário. Esse valor informa quantas pessoas distintas fizeram logon no Lync Server.

Por comparação, a métrica total de logons mostra quantas vezes o total de alguém fez logon no Lync Server. Por exemplo, suponha que Ken Myer fez logon no Lync Server cinco vezes diferentes em um único dia. Nesse caso, Ken Myer contaria como cinco sessões de logon separadas para a métrica de Total de logons, mas como apenas um usuário de logon para a métrica de Usuários de logon exclusivos. Do mesmo modo, não é incomum que um usuário faça logon de vários dispositivos ou locais. Por exemplo, um usuário pode fazer logon usando seu computador desktop, seu computador laptop e pode ter um telefone IP que faz logon automaticamente no Lync Server. Neste exemplo, existe um usuário exclusivo com três logons.

Para explicar de modo mais aprofundado a diferença entre total de logons e logons exclusivos, considere os logons para um dado período de tempo na tabela a seguir.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Usuário</th>
<th>Horário de logon</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>07/07/2012 08:45</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>07/07/2012 08:46</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>07/07/2012 09:17</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>07/07/2012 09:22</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>07/07/2012 09:31</p></td>
</tr>
</tbody>
</table>


Observe que há um total de cinco logons; no entanto, existem apenas dois usuários de logon exclusivos: Ken Myer (que fez logon três vezes) e Pilar Ackerman (que fez logon duas vezes). Essa é a diferença entre logons e usuários de logon exclusivos.

Além de saber o número de logons exclusivos, você precisa saber o número total de usuários que foram habilitados para o Lync Server. Esse valor pode ser recuperado abrindo o Shell de gerenciamento do Lync Server 2013 e executando o seguinte comando do Windows PowerShell:

    (Get-CsUser).Count

Se o comando anterior retornar um valor de 1.236 e a métrica de usuários de logon exclusivos retornar um valor médio de 667, isso indica que uma pequena parte dos seus usuários permite que o Lync esteja realmente fazendo logon no sistema por dia (ou seja, 667 dividido por 1.236 , que é de aproximadamente 54%).

<div>


> [!WARNING]  
> Lembre-se de que as métricas de logon registram usuários que realmente fizeram logons durante o período de tempo especificado. Elas não rastreiam os usuários que já estão logados no sistema. Por exemplo, se a sua métrica de Usuários de logon exclusivos mostra 667 logons e você possui 1.236 usuários, isso sugere que quase a metade de seus usuários estão fazendo logon no sistema. No entanto, suponha que 300 usuários já estavam logados no sistema no momento em que você começou a verificar os dados de logon. Isso significa que, na verdade, você tinha quase 1.000 usuários conectados ao Lync Server, o que significaria que mais perto de 80% dos seus usuários fizeram logon.



</div>

Você também deve comparar o valor de Usuários de logon exclusivos com o valor da métrica de Usuários ativos exclusivos. A métrica de usuários ativos exclusivos informa quantos usuários exclusivos realmente usavam o Lync Server: eles fizeram uma chamada telefônica, ingressaram em uma reunião do Lync ou participaram de uma sessão de IM. Essa é uma informação útil, pois o Microsoft Lync 2013 pode ser configurado para iniciar automaticamente cada vez que um usuário iniciar o Windows. Por isso, você pode ter um grande número de usuários que fazem logon automaticamente no Lync quando fazem logon no Windows a cada dia, mas nunca usa o Lync Server durante esse período de tempo.

A métrica de usuários ativos exclusivos também fornece dados mais significativos em uma organização onde os usuários normalmente não fazem logoff do Windows no final do dia. Em vez disso, eles simplesmente bloqueiam seus computadores e deixam o Windows e o Lync em execução. Em uma situação assim, você pode acabar com poucos logons por dia, pois seus usuários fizeram logon vários dias atrás e nunca fizeram o logoff. No entanto, os usuários ativos exclusivos informam se os usuários estão ativamente usando o Lync ou outro cliente do Lync Server.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o relatório de registro de usuário permite que você visualize os dados de todos os seus servidores de registro de registradores e de borda ou para exibir dados de um pool individual. Você também pode escolher como os dados devem ser agrupados. Nesse caso, registros agrupados por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que você pode usar com o Relatório de registro do usuário.

### <a name="user-registration-report-filters"></a>Filtros do Relatório de registro do usuário

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>De</strong></p></td>
<td><p>Data e hora de início para o intervalo de tempo. Para ver os dados por hora, digite a data e hora de início no seguinte formato:</p>
<p>7/7/2012 13:00 horas</p>
<p>Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre são de Domingo a Sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data e hora de término para o dia intervalo de tempo. Para ver os dados por hora, digite a data e a hora de término no seguinte formato:</p>
<p>07/07/2012 13:00</p>
<p>Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas são sempre de domingo a sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tempo. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Por hora (é possível exibir no máximo 25 horas)</p></li>
<li><p>Diariamente (é possível exibir no máximo 31 dias)</p></li>
<li><p>Semanalmente (é possível exibir no máximo 12 semanas)</p></li>
<li><p>Por mês (um máximo de 12 meses pode ser exibido)</p></li>
</ul>
<p>Se as datas iniciais e finais excedem o número máximo de valores permitidos para o intervalo selecionado, apenas o número de valores máximos (começando pela data inicial) é exibido. Por exemplo, se você selecionar o intervalo Diário com uma data inicial em 07.07.12 e data final em 28.02.12, os dados são exibidos pelo intervalo de 07.08.12 12:00 AM a 07.09.12 12:00 AM (isto é, um total de 31 dias de dados).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>FQDN do pool do Registrador ou Servidor de Borda. Você pode tanto selecionar um pool individual ou escolher <strong>[Todos]</strong> para visualizar os dados de todos os pools. Essa lista suspensa é automaticamente preenchida por você com base nos registros no banco de dados.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de registro do usuário.

### <a name="user-registration-report-metrics"></a>Métrica do Relatório de registro do usuário

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>É possível classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>A cada hora</strong></p>
<p><strong>Diariamente</strong></p>
<p><strong>Semanalmente</strong></p>
<p><strong>Mensal</strong></p></td>
<td><p>Não</p></td>
<td><p>Indica o intervalo de tempo selecionado na barra de ferramentas do filtro. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 07.07.12, você verá uma divisão por hora da atividade de registro do usuário para essa data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de logons</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões de logon bem-sucedidas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Logons internos</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de logons dentro da rede interna.</p></td>
</tr>
<tr class="even">
<td><p><strong>Logons externos</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total logons de fora da rede interna, usando o Servidor de Borda.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Usuários de logon exclusivo</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de usuário com ao menos uma sessão de logon. Um usuário com várias sessões de logon conta como um usuário, da mesma forma que uma pessoa que teve uma única sessão de logon.</p></td>
</tr>
<tr class="even">
<td><p><strong>Usuários ativos exclusivos</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de usuários envolvidos em uma sessão ponto a ponto ou de conferência. Um usuário com várias sessões de logon conta como um usuário, da mesma forma que uma pessoa que teve uma única sessão.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

