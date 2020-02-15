---
title: 'Lync Server 2013: relatório detalhado de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dce868d90d2811b36a4f11c159b4e7d9d29b5ffa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a>Relatório de detalhes de conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

O Relatório de Detalhe da Conferência oferece informações detalhadas sobre todos os usuários que participaram de uma conferência. Por exemplo, você pode ver tal informação como a data e hora que um usuário participou da conferência, a data e hora que o usuário saiu da conferência e o agente do usuário do ponto de extremidade que foi usado para conectar o usuário à conferência. Também é possível ver informações da função do usuário em cada conferência (por exemplo, Apresentador ou Participante). Talvez, o mais importante, você pode ver rapidamente quais usuários participaram com sucesso e concluíram a conferência e quais usuários não puderam participar e concluir a conferência.

<div>

## <a name="accessing-the-conference-detail-report"></a>Acessar o Relatório de Detalhe da Conferência

O Relatório de Detalhe da Conferência pode ser acessado pelos seguintes relatórios:

  - O [relatório de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-call-admission-control-report.md) (clicando na métrica detalhe de uma conferência)

  - O [relatório de lista de falhas no Lync Server 2013](lync-server-2013-failure-list-report.md) (clicando na métrica conferência)

  - O [relatório de atividades do usuário no Lync Server 2013](lync-server-2013-user-activity-report.md) (clicando na métrica URI da conferência)

No relatório de detalhe da conferência, é possível acessar o [relatório de diagnóstico no Lync Server 2013](lync-server-2013-diagnostic-report.md) clicando na métrica relatório de diagnóstico (detalhe).

</div>

<div>

## <a name="filters"></a>Filtros

Nenhum. Você não pode filtrar o Relatório de Detalhe da Conferência.

</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas na seção Informação da Conferência do Relatório de Detalhe da Conferência.

### <a name="conference-information-metrics"></a>Métricas de Informação da Conferência

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
<td><p><strong>URI de Conferência</strong></p></td>
<td></td>
<td><p>URI atribuído à conferência. Por exemplo:</p>
<p>SIP: kmyer@litwareinc. com; GRUU; opaco = App: conf: Focus: ID: drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDN do Pool</strong></p></td>
<td></td>
<td><p>Nome de domínio totalmente qualificado do pool do Registrador ou Servidor de Borda envolvido em uma sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora inicial</strong></p></td>
<td></td>
<td><p>Data e hora que a conferência iniciou.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizador</strong></p></td>
<td></td>
<td><p>Endereço SIP do usuário que organizou a conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora final</strong></p></td>
<td></td>
<td><p>Data e hora que a conferência terminou.</p></td>
</tr>
</tbody>
</table>


A tabela a seguir lista a informação oferecida na Seção de Participação da Conferência do Relatório de Detalhe da Conferência.

### <a name="conference-participation-metrics"></a>Métricas de Participação da Conferência

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
<td><p><strong>Usuário</strong></p></td>
<td></td>
<td><p>Endereço SIP do usuário que participou da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Função</strong></p></td>
<td></td>
<td><p>Função (por exemplo, Apresentador) do participante da conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conectividade</strong></p></td>
<td></td>
<td><p>Conectividade de rede (geralmente Externa ou Interna) do participante.</p></td>
</tr>
<tr class="even">
<td><p>Hora de participação</p></td>
<td></td>
<td><p>Data e hora de ingresso do participante na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de saída</strong></p></td>
<td></td>
<td><p>Data e hora que o participante saiu da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente do usuário</strong></p></td>
<td></td>
<td><p>Identificador do software usado pelo ponto de extremidade do participante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relatórios de diagnóstico</strong></p></td>
<td></td>
<td><p>Oferece informação de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de participação da conferência e IDs de diagnósticos para sessões em falha.</p></td>
</tr>
</tbody>
</table>


A tabela a seguir lista as informações fornecidas na seção modalidades de conferência do relatório de detalhe da conferência.

### <a name="conference-modalities-metrics"></a>Métricas das Modalidades da Conferência

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
<td><p><strong>Usuário</strong></p></td>
<td></td>
<td><p>Endereço SIP do usuário que participou da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de participação</strong></p></td>
<td></td>
<td><p>Data e hora que o participante entrou na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de saída</strong></p></td>
<td></td>
<td><p>Data e hora que um participante deixou a conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI do servidor de conferência</strong></p></td>
<td></td>
<td><p>URI para o servidor de Conferência usado na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relatórios de diagnóstico</strong></p></td>
<td></td>
<td><p>Oferece informação de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de participação da conferência e IDs de diagnósticos para sessões em falha.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

