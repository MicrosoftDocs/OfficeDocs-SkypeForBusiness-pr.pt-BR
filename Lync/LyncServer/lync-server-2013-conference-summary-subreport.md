---
title: 'Lync Server 2013: sub relatório Resumo da conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2537cbe959639baee6f0f986b3faea1ebd79b5a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a>Sub-relatório de Resumo de conferências no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-06_

O Sub-relatório de Resumo de Conferências oferece uma visão geral de sessões de conferências com falha. Estas sessões com falha são detalhadas pelo tipo de sessão: sessões de Foco e sessões MCU.

<div>

## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou para exibir os dados retornados de formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Sub-relatório de Resumo de Conferências.

### <a name="conference-summary-subreport-filters"></a>Filtros do Sub-relatório de Resumo de Conferências

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
<td><p>Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Até</strong></p></td>
<td><p>Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>O FQDN (nome de domínio totalmente qualificado) do pool Registrador Avançado ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Todos]</strong> para ver os dados de todos os pools. Essa lista suspensa é preenchida automaticamente com base nos registros no banco de dados.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Sub-relatório de Resumo de Conferências.

### <a name="conference-summary-subreport-metrics"></a>Métricas do Sub-relatório de Resumo de Conferências

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
<td><p><strong>Conferências totais</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências realizadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sessões de conferência</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões de conferência. Uma única conferência pode ter várias sessões; por exemplo, uma conferência pode incluir uma sessão Foco e uma sessão MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa geral de falha de sessão</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem de todas as conferências que falharam.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões de Foco</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões de Foco.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de falha de Foco</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem das sessões de Foco que falharam.</p></td>
</tr>
<tr class="even">
<td><p>Sessões MCU</p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de falha de MCU</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem de sessões MCU que falharam.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões MCU por modalidade</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões MCU, agrupado por modalidade (por exemplo, conferência de IM).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de falha por modalidade</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem de sessões MCU que falharam, agrupadas por modalidade (por exemplo, conferência de IM).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

