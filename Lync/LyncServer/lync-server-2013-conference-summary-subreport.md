---
title: 'Lync Server 2013: sub-relatório de Resumo de conferências'
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
ms.openlocfilehash: 9cc0e61333b491a4d28e42167a9e60823e0331d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a>Sub-relatório de Resumo de conferências no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-06_

O Subrelatório de Resumo da Conferência oferece uma visão geral das sessões de conferência em falha. Estas sessões em falha são detalhadas pelo tipo de sessão: Sessão de foco e sessões MCU.

<div>

## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou para exibir os dados retornados de formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Subrelatório de Resumo da Conferência.

### <a name="conference-summary-subreport-filters"></a>Filtros do Subrelatório de Resumo da Conferência

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
<p>As semanas são sempre de domingo a sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</p>
<p>7/7/2012 13:00 horas</p>
<p>Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre correm do domingo até sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>FQDN do pool do Registrador ou Servidor de Borda. É possível selecionar um pool individual ou clicar em <strong>[Todos]</strong> para exibir os dados de todos os pools. Esta lista suspensa é preenchida automaticamente para você com base nos registros do banco de dados.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Subrelatório de Resumo de Conferência.

### <a name="conference-summary-subreport-metrics"></a>Métricas do Subrelatório de Resumo da Conferência

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
<td><p><strong>Total de conferências</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências realizadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sessões de conferência</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões de conferência. Uma única conferência pode ter várias sessões; por exemplo, uma conferência pode incluir uma sessão Foco e uma sessão MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de falha de sessão geral</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem de todas as conferências que falharam.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões de foco</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões de Foco.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de falha do foco</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem das sessões de Foco que falharam.</p></td>
</tr>
<tr class="even">
<td><p>Sessões MCU</p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões MCU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de falha MCU</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem de sessões MCU que falharam.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões MCU por modalidade</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões MCU, agrupado por modalidade (por exemplo, conferência IM).</p></td>
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

