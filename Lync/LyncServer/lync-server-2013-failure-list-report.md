---
title: 'Lync Server 2013: relatório de lista de falhas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 467dbfe14cbcbe7a032439fd437d3ce2c58c6d46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515378"
---
# <a name="failure-list-report-in-lync-server-2013"></a>Relatório de lista de falhas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-07-02_

The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.

<div>

## <a name="accessing-the-failure-list-report"></a>Accessing the Failure List Report

O relatório de lista de falhas é acessado clicando em qualquer uma das seguintes métricas no [relatório de distribuição de falha no Lync Server 2013](lync-server-2013-failure-distribution-report.md):

  - Principais motivos diagnósticos (sessões)

  - Principais modalidades (sessões)

  - Principais pools (sessões)

  - Principais fontes (sessões)

  - Principais componentes (sessões)

  - Principais usuários de origem (sessões)

  - Principais usuários de destino (sessões)

  - Principais agentes de usuários de origem (sessões)

No relatório de lista de falhas, é possível acessar o [relatório de detalhes de sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) clicando na métrica de detalhes da sessão para uma sessão ponto a ponto. You can also access the Conference Detail Report by clicking the Conference metric for a conference.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Making the Best Use of the Failure List Report

In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:

Internal server error creating media for user.

It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session. (Por um motivo, o relatório de lista de falhas não tem recursos de filtragem.) No entanto, se você exportar os dados e convertê-los em um arquivo de valores separados por vírgula, você poderá usar o Windows PowerShell para encontrar as respostas a perguntas como essas. Por exemplo, suponha que você salve os dados em um. Arquivo CSV chamado C: \\ falha de dados \\ \_List.csv. Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

That command will return a list similar to this:

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

These two commands report back the total number of failed sessions that each user was involved in:

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

That will return data similar to this:

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o Relatório de Lista de Falhas.

</div>

<div>

## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Lista de Falhas para cada chamada mal-sucedida.

### <a name="failure-list-report-metrics"></a>Métricas do Relatório de Lista de Falhas

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
<td><p><strong>Hora de relatório</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora em que o relatório foi gravado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Solicitação</strong></p></td>
<td><p>Não</p></td>
<td><p>Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR ou ATÉ LOGO.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código da resposta</strong></p></td>
<td><p>Não</p></td>
<td><p>Código da resposta SIP enviado quando a conferência falhou.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID do Diagnóstico</strong></p></td>
<td><p>Não</p></td>
<td><p>Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Join cost time (ms)</strong></p></td>
<td><p>Não</p></td>
<td><p>Amount of time (in milliseconds) required for the user to join the conference.</p></td>
</tr>
<tr class="even">
<td><p><strong>Do usuário </strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do usuário que iniciou a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Representante do usuário de origem</strong></p></td>
<td><p>Não</p></td>
<td><p>Software usado pelo ponto de extremidade do usuário que iniciou a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Para usuário</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do usuário que estava recebendo a chamada.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

