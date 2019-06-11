---
title: 'Lync Server 2013: relatório de registro do usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f56ffd05e677d5106552a9ebcf8a0718efbc100
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Relatório de registro de usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-21_

O relatório de registro de usuário fornece uma visão geral da atividade de logon do usuário, principalmente as informações sobre o número de usuários que se conectaram ao Microsoft Lync Server 2013 durante um período de tempo especificado (hora, diária, semanal, mensal). Lembre-se de que o relatório mostra apenas quantas pessoas fizeram logon. Ele não mostra *quais* pessoas fizeram logon. Os relatórios de monitoramento não fornecem informações sobre quais usuários específicos estão usando o Lync Server 2013 (e quais não são). No entanto, você pode obter uma estimativa aproximada de informações de usuário usando o Relatório de Atividades de Usuário.

Ao fornecer informações sobre logons de usuários, o Relatório de Registro de Usuário faz duas distinções importantes. Primeiro, ele desdobra os logons em duas categorias primárias: logons internos e logons externos. Logons internos representam usuários que fizeram logon de dentro do firewall de sua organização (isto é, enquanto estavam conectados à rede corporativa). Os logons externos representam os usuários que fizeram logon de fora do firewall por meio de um servidor de borda (por exemplo, um usuário que fez logon de um café da Internet conta como um logon externo). Caso precise saber quantos de seus usuários estão fazendo logon de fora do firewall, o Relatório de Registro de Usuário pode fornecer essa informação.

Além disso, o Relatório de Registro de Usuário indica quantos usuários *ativos* estavam presentes durante um dado período de tempo. Um usuário ativo é um usuário que fez parte de uma sessão de mensagens instantâneas (IM), participou em uma reunião do Lync, fez ou recebeu uma chamada telefônica ou, de outra forma, usava o Lync Server durante esse período de tempo. Isso é diferente de um usuário que fez logon mas nunca usou o sistema de fato.

<div>

## <a name="accessing-the-user-registration-report"></a>Acessando o Relatório de Registro de Usuário

Você acessa o Relatório de Registro de Usuário apenas a partir da home page de Relatórios de Monitoramento. O Relatório de Registro de Usuário não vincula nenhum outro relatório.

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>Usando o Relatório de Registro de Usuário da melhor maneira possível

Depois de implantar o Lync Server, uma pergunta comumente: como posso saber se meus usuários estão realmente usando essa nova tecnologia? Embora tenha algumas limitações neste sentido, o Relatório de Registro de Usuário ajuda você a responder essa pergunta. Para determinar se os usuários estão usando o Lync Server, você precisa fazer duas coisas. Primeiro, obtenha o valor da métrica de Usuários de logon exclusivos, do Relatório de Registro de Usuário. Esse valor informa quantos indivíduos distintos estão conectados ao Lync Server.

Por comparação, a métrica de logons totais mostra quantas vezes todos se conectaram ao Lync Server. Por exemplo, suponha que Ken Myer esteja conectado ao Lync Server cinco vezes diferentes em um único dia. Nesse caso, Ken Myer contaria como cinco sessões de logon separadas para a métrica de Total de logons, mas como apenas um usuário de logon para a métrica de Usuários de logon exclusivos. Do mesmo modo, não é incomum que um usuário faça logon de vários dispositivos ou locais. Por exemplo, um usuário pode fazer logon usando seu computador de mesa, computador laptop e ele pode ter um telefone IP que se conecta automaticamente ao Lync Server. Neste exemplo, temos um usuário exclusivo com três logons.

Para explicar de modo mais aprofundado a diferença entre total de logons e logons exclusivos, considere os logons em determinado período de tempo na tabela a seguir.


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
<td><p>7/7/2012 8:45 AM</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8:46 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:17 AM</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 9:22 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:31 AM</p></td>
</tr>
</tbody>
</table>


Observe que há um total de cinco logons; no entanto, há apenas dois usuários de logon exclusivo: Ken Myer (que fez logon três vezes) e Pilar Ackerman (que fez logon duas vezes). Essa é a diferença entre logons e usuários de logon exclusivos.

Além de saber o número de logons exclusivos, você precisa saber o número total de usuários que foram habilitados para o Lync Server. Esse valor pode ser recuperado abrindo o Shell de gerenciamento do Lync Server 2013 e executando o seguinte comando do Windows PowerShell:

    (Get-CsUser).Count

Se o comando anterior retornar um valor de 1.236 e os usuários de logon exclusivos retornarem um valor médio de 667, isso indica que uma pequena parte da metade dos usuários habilitada para o Lync está realmente fazendo logon no sistema por dia (ou seja, 667 dividido por 1.236 , que é de aproximadamente 54%).

<div>


> [!WARNING]  
> Lembre-se de que as métricas de logon registram usuários que realmente fizeram logons durante o período de tempo especificado. Elas não rastreiam os usuários que já estão logados no sistema. Por exemplo, se a sua métrica de Usuários de logon exclusivos mostrar 667 logons e você tiver 1.236 usuários, isso sugere que metade de seus usuários estão fazendo logon no sistema. No entanto, suponhamos que 300 usuários já estavam logados no sistema no momento em que você começou a verificar os dados de logon. Isso significa que você realmente tinha quase 1.000 usuários conectados ao Lync Server, o que significa que mais perto do 80% dos seus usuários estavam conectados.



</div>

Você também deve comparar o valor de Usuários de logon exclusivos com o valor da métrica de Usuários ativos exclusivos. A métrica de usuários ativos exclusivos informa quantos usuários exclusivos realmente usaram o Lync Server: ele fez uma chamada telefônica, ele ingressou em uma reunião do Lync ou ele participou em uma sessão de mensagens instantâneas. Isso é uma informação útil, porque o Microsoft Lync 2013 pode ser configurado para ser iniciado automaticamente sempre que um usuário iniciar o Windows. Por isso, você pode ter um grande número de usuários que fazem logon automaticamente no Lync quando eles fazem logon no Windows todos os dias, mas nunca usam realmente o Lync Server durante esse período de tempo.

A métrica de usuários ativos exclusivos também fornece dados mais significativos em uma organização, onde os usuários geralmente não fazem logoff do Windows no final do dia. Em vez disso, eles simplesmente bloqueiam seus computadores e deixam o Windows e o Lync em execução. Em uma situação assim, você pode acabar com poucos logons por dia, pois seus usuários fizeram logon vários dias atrás e nunca fizeram o logoff. No entanto, usuários ativos exclusivos informa se os usuários estão ativamente usando o Lync ou outro cliente do Lync Server.

</div>

<div>

## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o relatório de registro de usuário permite que você exiba dados de todos os seus servidores de registro de registradores e de borda ou exiba dados de um pool individual. Você também pode escolher como os dados devem ser agrupados. Nesse caso, registros agrupados por hora, dia, semana ou mês.

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
<td><p>Data e hora de início do intervalo de tempo. Para ver os dados por hora, insira a data e hora de início desta forma:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Até</strong></p></td>
<td><p>Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tempo. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Por hora (é possível exibir no máximo 25 horas)</p></li>
<li><p>Diariamente (é possível exibir no máximo 31 dias)</p></li>
<li><p>Semanalmente (é possível exibir no máximo 12 semanas)</p></li>
<li><p>Mensalmente (é possível exibir no máximo 12 meses)</p></li>
</ul>
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, apenas o número máximo de valores (começando pela data de início) será exibido. Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>FQDN (Nome de domínio totalmente qualificado) do pool de Registradores Avançados ou Servidores de Borda. Você pode selecionar um pool individual ou escolher <strong>[Todos]</strong> para visualizar os dados de todos os pools. Essa lista suspensa é automaticamente preenchida com base nos registros no banco de dados.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Registro de Usuário.

### <a name="user-registration-report-metrics"></a>Métrica do Relatório de Registro de Usuário

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Você pode classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Por hora</strong></p>
<p><strong>Diário</strong></p>
<p><strong>Semanal</strong></p>
<p><strong>Mensal</strong></p></td>
<td><p>Não</p></td>
<td><p>Indica o intervalo de tempo selecionado na barra de ferramentas de filtro. Quando aplicável, é possível clicar em determinado intervalo de tempo para exibir informações detalhadas sobre ele. Por exemplo, se você estiver usando o intervalo diário e clicar em 7/7/2012, verá um detalhamento por hora da atividade de registro do usuário para essa data.</p></td>
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

