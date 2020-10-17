---
title: 'Lync Server 2013: relatório de controle de admissão de chamada'
description: 'Lync Server 2013: relatório de controle de admissão de chamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8764e51603e7097095894bc1230c2a2bb1126b9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572357"
---
# <a name="call-admission-control-report-in-lync-server-2013"></a>Relatório de controle de admissão de chamadas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-29_

O Relatório de Controle de Admissão de Chamadas fornece informações sobre sessões de conferência e ponto a ponto que eram conduzidas sob restrições impostas pelo Controle de Admissão de Chamadas. Call Admission Control, introduzido no Microsoft Lync Server 2010, oferece uma maneira de os administradores permitirem (ou não permitirem) sessões de comunicação com base nas restrições de largura de banda. Por exemplo, os administradores podem criar políticas que impõe um limite na quantidade de banda disponível para chamadas de voz e vídeo. Caso o limite de banda tenha sido alcançado, novas chamadas de voz ou vídeo não poderão ser feitas até que uma das chamadas atuais termine e libere os recursos de rede necessários.

<div>

## <a name="accessing-the-call-admission-control-report"></a>Acessando o Relatório de Controle de Admissão de Chamadas

O Relatório de Controle de Admissão de Chamadas é acessado através da página de Relatórios de Monitoramento. A partir do Relatório de Controle de Admissão de Chamadas você pode buscar mais detalhes em um dos seguintes relatórios:

  - Relatório de Detalhes de Conferência – Para acessar este relatório, clique na métrica Detalhes em uma sessão de conferência.

  - Relatório de Detalhe de Sessão Ponto a Ponto – Para acessar este relatório, clique na métrica Detalhes para uma sessão ponto a ponto.

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Usando o Relatório de Controle de Admissão de Chamadas da melhor maneira possível

Para obter uma lista de chamadas que falharam por causa de largura de banda insuficiente, selecione Chamadas rejeitadas por causa do controle de admisssão de chamadas, na lista suspensa de categoria de Chamadas. A maioria das chamadas retornadas provavelmente terão a ID de diagnóstico 5:

Largura de banda insuficiente para estabelecer sessão. Tente reencaminhamento PSTN.

Isso indica que as limitações do Controle de Admissão de Chamadas estavam impedidndo a chamada de ser feita na rede VoIP.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Controle de Admissão de Chamada permite que você filtre as chamadas de acordo com o usuário que iniciou a chamada ou com o usuário que está sendo chamado. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as chamadas são agrupadas por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o Relatório de Controle de Admissão de Chamada.

### <a name="call-admission-control-report-filters"></a>Filtros do Relatório de Controle de Admissão de Chamadas

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
<td><p>Data/hora de início para o intervalo de tempo. Para exibir os dados por horas, digite a data e a hora de início da seguinte maneira:</p>
<p>17/07/2012 13:00</p>
<p>Se você não digitar um horário de início, o relatório começará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</p>
<p>7/17/12012</p>
<p>Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/13/2012</p>
<p>As semanas sempre correm do domingo até sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/hora de término para o intervalo de tempo. Para exibir os dados por horas, digite a data e hora de término da seguinte maneira:</p>
<p>17/07/12012 13:00</p>
<p>Se você não digitar um horário de término, o relatório terminará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</p>
<p>7/17/12012</p>
<p>Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/13/2012</p>
<p>As semanas sempre correm do domingo até sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de atividade </strong></p></td>
<td><p>Tipo de atividade. Selecione uma das seguintes atividades:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Ponto a ponto</p></li>
<li><p>Conferência</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Categoria da chamada</strong></p></td>
<td><p>Indica o motivo de o CAC ter sido usado para a chamada. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Chamada rejeitada devido ao controle de admissão de chamada</p></li>
<li><p>Chamadas reencaminhadas por PSTN devido ao controle de admissão de chamada</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamada para sessões ponto a ponto (ou seja, sessões que envolvem apenas dois participantes).

### <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

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
<td><p><strong>Ver os detalhes</strong></p></td>
<td><p>Não</p></td>
<td><p>Quando você clica nesse item, o relatório mostra o Relatório de Detalhes da Sessão Ponto a Ponto para a sessão especificada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Do usuário </strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP do usuário que iniciou a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Para usuário</strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP do usuário convidado para ingressar na sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalidades</strong></p></td>
<td><p>Sim</p></td>
<td><p>Modalidades de comunicação (como áudio e vídeo) usadas durante a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora do convite</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora de envio do convite inicial da sessão para o usuário De.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora da resposta</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora de recebimento da aceitação do convite.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de término</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora de encerramento da sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID do Diagnóstico</strong></p></td>
<td><p>Sim</p></td>
<td><p>Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Métricas para sessões de conferência

A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamada para sessões de conferência (ou seja, sessões que envolvem três ou mais participantes).

### <a name="metrics-for-conferencing-sessions"></a>Métricas para sessões de conferência

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
<td><p><strong>URI de conferência</strong></p></td>
<td><p>Sim</p></td>
<td><p>Identificador exclusivo para a conferência. Quando você clica nesse item, o relatório mostra os participantes individuais da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizador</strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP do usuário que organizou a conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Sim</p></td>
<td><p>Servidor de Borda usado na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de início</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora de início da sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de término</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora de encerramento da conferência.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a>Métricas para participantes individuais de conferência

A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamada para participantes individuais da conferência.

### <a name="metrics-for-individual-conference-participants"></a>Métricas para participantes individuais de conferência

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
<td><p><strong>Função</strong></p></td>
<td><p>Não</p></td>
<td><p>Função (por exemplo, Apresentador) desempenhada pelo participante da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Participante</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do participante de conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conectividade</strong></p></td>
<td><p>Não</p></td>
<td><p>Conectividade de rede (normalmente Interna ou Externa) para o participante.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalidade</strong></p></td>
<td><p>Não</p></td>
<td><p>Tipo de conferência (por exemplo, conferência A/V).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de ingresso</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora de ingresso do participante na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de saída</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora de saída do participante da conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID do Diagnóstico</strong></p></td>
<td><p>Não</p></td>
<td><p>Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

