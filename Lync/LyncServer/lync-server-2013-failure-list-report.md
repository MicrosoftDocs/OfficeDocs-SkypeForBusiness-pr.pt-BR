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
ms.openlocfilehash: 370008a5b33cc7eb45802fb02bdd9a873184ed5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Relatório lista de falhas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-07-02_

O Relatório da lista de falhas fornece informações sobre os participantes individuais de uma sessão de conferência ou ponto a ponto com falha. Essas informações incluem o URI do usuário que teve o problema, bem como o código de resposta SIP e o ID de diagnóstico associado à falha.

<div>

## <a name="accessing-the-failure-list-report"></a>Acessando o Relatório da lista de falhas

O relatório lista de falhas é acessado clicando em qualquer uma das seguintes métricas no [relatório distribuição de falha no Lync Server 2013](lync-server-2013-failure-distribution-report.md):

  - Principais motivos diagnósticos (sessões)

  - Principais modalidades (sessões)

  - Principais pools (sessões)

  - Principais fontes (sessões)

  - Principais componentes (sessões)

  - Principais usuários "De" (sessões)

  - Principais usuários "Para" (sessões)

  - Principais agentes do usuários "De" (sessões)

No relatório lista de falhas, você pode acessar o [relatório de detalhes da sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) clicando na métrica de detalhes da sessão de uma sessão ponto a ponto. Você também pode acessar o Relatório de detalhes da conferência clicando na métrica Conferência de uma conferência.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Aprimorando o uso do Relatório da lista de falhas

No Relatório da lista de falhas, é possível visualizar uma descrição para cada código de resposta ou cada ID de diagnóstico simplesmente passando o mouse sobre o valor em questão. Por exemplo, se você passar o mouse sobre o ID de diagnóstico 7025, verá a seguinte mensagem em uma dica de ferramenta:

Internal server error creating media for user.

É importante notar que o Relatório da lista de falhas não fornece uma maneira simples de recuperar diretamente uma lista de todos os usuários que participaram de pelo menos uma sessão com falha, nem fornece uma maneira de determinar quais usuários geralmente estavam envolvidos em uma sessão com falha. (Por um motivo, o relatório lista de falhas não tem funcionalidades de filtragem.) No entanto, se exportar os dados e convertê-los em um arquivo de valores separados por vírgula, você poderá usar o Windows PowerShell para encontrar as respostas a perguntas como essas. Por exemplo, suponha que você salve os dados em um. Arquivo CSV denominado C:\\lista\\de\_falhas de dados. csv. Com base nos dados salvos nesse arquivo, esse comando lista os usuários que estavam envolvidos em pelo menos uma sessão com falha:

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Esse comando retornará uma lista semelhante a esta:

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Esses dois comandos relatam o número total de sessões com falha em que cada usuário estava envolvido:

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Serão retornados dados semelhantes a estes:

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

## <a name="metrics"></a>Métricas

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
<th>Você pode classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Hora de relatório</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora do registro do relatório.</p></td>
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
<td><p>Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Join cost time (ms)</strong></p></td>
<td><p>Não</p></td>
<td><p>Tempo (em milissegundos) necessário para o usuário participar da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Usuário "De"</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do usuário que iniciou a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente do usuário de origem</strong></p></td>
<td><p>Não</p></td>
<td><p>Software usado pelo ponto de extremidade do usuário que iniciou a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Usuário "Para"</strong></p></td>
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

