---
title: 'Lync Server 2013: relatório de Resumo de conferência PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b531d0e8d7d4fe5de6d1598cf557096ebff8a90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Relatório de Resumo de conferência PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

No Microsoft Lync Server 2013, uma conferência PSTN é qualquer conferência na qual pelo menos um participante disca para a parte de áudio usando um telefone PSTN (rede telefônica pública comutada). (Um telefone PSTN é um "fixa", um telefone celular ou qualquer outro telefone que não usa voz sobre IP.) Embora sejam conhecidas como conferências PSTN nos relatórios de monitoramento, essas conferências provavelmente são mais conhecidas como conferências discadas.

O relatório de Resumo de conferência PSTN fornece informações sobre todas as conferências PSTN mantidas em sua organização (ou seja, todas as conferências que tiveram pelo menos um usuário de discagem). O relatório inclui informações sobre o número total de conferências PSTN, o número total de pessoas que participaram dessas conferências e, talvez, a maioria importante, o número total de usuários de discagem (a métrica total de participantes PSTN).

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>Acessando o relatório de Resumo de conferência PSTN

O relatório de Resumo de conferência PSTN só pode ser acessado na página inicial de relatórios de monitoramento. Este relatório não está vinculado a outros relatórios. Observe que você não pode recuperar informações de chamada detalhadas para uma conferência PSTN, em parte porque os pontos de extremidade individuais são responsáveis por enviar essas informações. Telefones PSTN não são capazes de controlar ou enviar informações de detalhes de chamada.

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Fazendo o melhor uso do relatório de Resumo de conferência PSTN

Para determinar a porcentagem de todas as conferências que incluem usuários de discagem, compare o valor da métrica total de conferências PSTN com a métrica total de conferências encontrada no [relatório de Resumo de conferências no Lync Server 2013](lync-server-2013-conference-summary-report.md).

Se você não vir tantas conferências PSTN quanto as esperadas, tenha em mente que a capacidade de organizar uma conferência que permite que os usuários de discagem dependam da política de conferência que foi atribuída a um usuário: se poucos usuários tiverem permissão para manter o PS Conferências do TN você certamente veria muito poucas conferências PSTN. Você pode verificar rapidamente quais políticas de conferência (se houver) permitem que os usuários agendem conferências PSTN executando o seguinte comando no Shell de gerenciamento do Lync Server:

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

Isso retornará dados semelhantes a estes:

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

That will return data similar to this:

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. Por exemplo, o relatório de Resumo de conferência PSTN permite que você escolha como os dados devem ser agrupados. Nesse caso, as conferências são agrupadas por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o relatório de Resumo de conferência PSTN.

### <a name="pstn-conference-summary-report-filters"></a>Filtros do relatório de Resumo de conferência PSTN

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
<td><p>Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</p>
<p>7/7/2012 13:00 horas</p>
<p>Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre são de Domingo a Sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</p>
<p>7/7/2012 13:00 horas</p>
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
<li><p>Mensalmente (é possível exibir no máximo 12 meses)</p></li>
</ul>
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 7/7/12 e uma data de término de 28/2/12, os dados serão exibidos para os dias 7/8/2 00:00 horas até 7/9/12 00:00 horas (ou seja, um total de 31 dias de dados).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações no relatório de Resumo de conferência PSTN.

### <a name="pstn-conference-summary-report-metrics"></a>Métricas do relatório de Resumo de conferência PSTN

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
<td><p>Indica o intervalo de tempo selecionado. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se estiver usando o intervalo Diário e clicar em 7/7/12, você verá uma divisão por hora da atividade de registro do usuário para essa data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de conferências PSTN</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências que permitiram acesso discado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de participantes</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de pessoas que participaram de conferências que permitiram acesso discado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de minutos da conferência A/V</strong></p></td>
<td><p>Não</p></td>
<td><p>Quantidade total de tempo de áudio/conferência Visual.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos do participante da conferência A/V</strong></p></td>
<td><p>Não</p></td>
<td><p>Quantidade total de tempo de áudio/do participante Visual. Por exemplo, se um participante gastou cinco minutos em uma conferência de A/V e outro participante gastou três minutos na mesma conferência, o tempo de participante da Conferência A/V deve ser de oito minutos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de participantes PSTN</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de usuários que discaram para conferências que permitiram acesso discado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de participantes PSTN</strong></p></td>
<td><p>Não</p></td>
<td><p>Quantidade total de tempo de conferência gasto por usuários discados. Por exemplo, se um participante de discagem gastou cinco minutos em uma conferência e outro participante gastou três minutos na mesma conferência, o tempo de participante PSTN total será de oito minutos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizadores de conferência exclusivos</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de usuários que organizaram pelo menos uma conferência que permitia acesso de discagem. Os usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como os usuários que só organizaram uma única conferência.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

