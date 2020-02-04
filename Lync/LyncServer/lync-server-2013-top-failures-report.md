---
title: 'Lync Server 2013: relatório de falhas principais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a62dce5d074b19c2bc8958715ced61bb54a4c8e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a>Relatório de falhas principais no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

O Relatório de Falhas Principais apresenta uma noção das falhas mais frequentemente relatadas e suas tendências ao longo do tempo. As falhas são baseadas em uma combinação das seguintes métricas:

  - **ID de Diagnóstico**. Identificador único (na forma de um cabeçalho ms-diagnostics) que é anexado a uma mensagem SIP. As IDs de Diagnóstico fornecem informações úteis na solução de problemas relacionados a chamadas.

  - **Código de resposta**. Os códigos de resposta são utilizados nas sessões de comunicação SIP para responder solicitações SIP. Por exemplo, suponha que Ken envie a solicitação INVITE a Pilar Ackerman (isto é, suponha que Ken Myer ligue para Pilar Ackerman). Se Pilar responder, o telefone enviará o código de resposta 200 (OK), permitindo que o telefone de Ken saiba que Pilar atendeu. O relatório de falhas principais inclui apenas códigos de resposta que foram enviados em resposta a uma falha de chamada; O Lync Server não mantém o controle de todos os códigos de resposta emitidos durante o curso de uma chamada.

A informação é relatada não apenas para o número total de sessões quando uma falha ocorre, mas também para o número total de usuários que foram impactados pela falha.

<div>

## <a name="accessing-the-top-failures-report"></a>Acessando o Relatório de Falhas Principais

O Relatório de Falhas Principais é acessado a partir da home page Relatórios de Monitoramento. Clicar na métrica de sessões informadas levará você ao [relatório de distribuição de falha no Lync Server 2013](lync-server-2013-failure-distribution-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>Fazendo o melhor uso do Relatório de Falhas Principais

O Relatório de Falhas Principais é incomum quanto a uma coisa: ele permite a filtragem de até 5 IDs de diagnóstico de uma vez. (Normalmente, você só pode filtrar um item, como o endereço SIP de usuário, por vez.) Para filtrar várias IDs de diagnóstico, basta inserir cada ID na caixa de ID de Diagnóstico, separando as IDs com vírgula. (Se você quiser, pode deixar um espaço em branco após cada vírgula.) Por exemplo:

1011, 2412, 1033, 52116, 1008

Faça isso e apenas chamadas que falharam e foram reportadas pelo menos em uma dessas cinco IDs de diagnóstico serão exibidas.

Ao passar o mouse sobre um Código de Resposta, você verá uma dica que diz o que um Código de Resposta em questão significa. Por exemplo, se você passar o mouse sobre o Código de Resposta 486, verá esta mensagem:

Ocupado.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou exibir os dados retornados de diferentes maneiras. Por exemplo, o Relatório de Falhas Principais permite filtrar os dados retornados com base, por exemplo, no tipo de atividade (sessão ponto a ponto ou sessão de conferência), ou com base no código de resposta SIP que acompanhava a sessão com falha. Você também pode escolher como os dados devem ser agrupados. Nesse caso, os usos são agrupados por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que você pode usar com o Relatório de Falhas Principais.

### <a name="top-failures-report-filters"></a>Filtros de Relatório de Falhas Principais

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
<td><p><strong>Tipo de atividade</strong></p></td>
<td><p>Tipo de atividade. Selecione uma das seguintes opções:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Ponto a ponto</p></li>
<li><p>Conferência</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalidade</strong></p></td>
<td><p>Neste momento, a única opção disponível é <strong>[Todos]</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>O FQDN (nome de domínio totalmente qualificado) do pool Registrador Avançado ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Todos]</strong> para ver os dados de todos os pools. Essa lista suspensa é preenchida automaticamente com base nos registros no banco de dados.</p></td>
</tr>
<tr class="even">
<td><p><strong>Categoria</strong></p></td>
<td><p>Tipo de falha ocorrido. Selecione um dos seguintes:</p>
<ul>
<li><p>Falha inesperada e esperada</p></li>
<li><p>Falha inesperada</p></li>
</ul>
<p>Uma &quot;falha&quot; esperada é uma falha que espera acontecer. Por exemplo, se um usuário tiver definido seu status como Não perturbe, é esperado que qualquer chamada para esse usuário falhe. Uma &quot;falha&quot; inesperada é uma falha que ocorre em que parece ser um sistema de outra forma saudável. Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera. Se isso ocorrer, a situação será sinalizada como falha inesperada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código de resposta</strong></p></td>
<td><p>O código de resposta enviado quando a conferência falhou. Digite o código de resposta inteiro. Por exemplo:</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>ID do Diagnóstico</strong></p></td>
<td><p>Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que fornece informações úteis para resolução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não os incluem), e as IDs de diagnóstico são relatadas somente em sessões com algum tipo de problema.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Falhas Principais.

### <a name="top-failures-report-metrics"></a>Métricas do Relatório de Falhas Principais

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
<td><p><strong>Classificação</strong></p></td>
<td><p>Sim</p></td>
<td><p>Classificação relativa com base no número de sessões relatadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões relatadas</strong></p></td>
<td><p>Sim</p></td>
<td><p>Número total de sessões com falha com base na ID de diagnóstico e no código de resposta SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Usuários afetados</strong></p></td>
<td><p>Sim</p></td>
<td><p>Número total de usuários afetados pela sessão com falha.</p></td>
</tr>
<tr class="even">
<td><p><strong>Informações da falha</strong></p></td>
<td><p>Não</p></td>
<td><p>Informações detalhadas sobre a falha, incluindo a ID de diagnóstico, o código de resposta SIP e a descrição do motivo da falha na sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tendência no passado</strong></p></td>
<td><p>Não</p></td>
<td><p>Representa graficamente as sessões com falha ao longo do tempo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

