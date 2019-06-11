---
title: 'Lync Server 2013: relatório de lista de chamadas em grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf2c45167b5e5c437a3ff755115aa54d34c74a87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a>Relatório de lista de chamadas em grupo de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

O aplicativo grupo de resposta fornece uma maneira para que o Microsoft Lync Server 2013 atenda e encaminhe chamadas telefônicas com base no número que foi discado e, opcionalmente, nas respostas do chamador para uma série de perguntas. Geralmente, as chamadas do Grupo de Resposta não são encaminhadas a uma pessoa específica, mas sim para uma equipe de pessoas referida como grupo de agentes. Por exemplo, se alguém ligar para o número de telefone de seu suporte técnico, o Lync Server 2013 poderá direcionar automaticamente essa chamada para o primeiro agente de suporte técnico disponível. Ou, se preferir, o Lync Server pode fazer uma série de perguntas ("Pressione 1 se estiver com problemas de hardware). Pressione 2 se tiver problemas de software. Pressione 3 se você estiver tendo problemas de rede. ") e, em seguida, encaminhar a chamada para o agente de suporte técnico mais apropriado com base na resposta a essas perguntas.

O Relatório da Lista de Chamadas de Grupo de Resposta representa uma coleção de chamadas feitas por um período específico de tempo e para um tipo específico de chamada. O Relatório de Uso do Grupo de Resposta (que deve ser aberto primeiro, antes de abrir o Relatório da Lista de Chamadas de Grupo de Resposta) reconhece os seguintes tipos de chamadas:

  - **Chamadas recebidas**. Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta.

  - **Chamadas bem-sucedidas**. Número total de chamadas atendidas pelo aplicativo Grupo de Resposta.

  - **Chamadas oferecidas**. Número total de chamadas transferidas para um agente do Grupo de Resposta.

  - **Chamadas atendidas**. Número total de chamadas atendidas por um agente do Grupo de Resposta.

  - Porcentagem de chamadas abandonadas. Porcentagem de chamadas recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Esse valor é calculado subtraindo as Chamadas atendidas das Chamadas recebidas e dividindo esse valor pelo número de Chamadas recebidas. Por exemplo, se você receber 10 chamadas e 7 forem atendidas, subtraia 7 de 10, deixando 3 chamadas não atendidas. Esse valor seria dividido por 10, proporcionando uma porcentagem de chamadas abandonadas de 30%.

  - **Chamadas transferidas**. Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou estouro de fila.

<div>

## <a name="accessing-the-response-group-call-list-report"></a>Como acessar o Relatório da Lista de Chamadas de Grupo de Resposta

O relatório de lista de chamadas em grupo de resposta só pode ser acessado clicando em uma das seguintes métricas encontradas no [relatório de uso do grupo de resposta no Lync Server 2013](lync-server-2013-response-group-usage-report.md):

  - Chamadas recebidas

  - Chamadas bem-sucedidas

  - Chamadas oferecidas

  - Chamadas atendidas

  - Chamadas transferidas

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Como usar o Relatório da Lista de Chamadas de Grupo de Resposta da melhor maneira possível

O Relatório da Lista de Chamadas de Grupo de Resposta permite que você limite os dados exibidos para chamadas que envolvem um fluxo de trabalho específico de Grupo de Resposta. Para fazer isso, você precisa inserir o URI do fluxo de trabalho (o endereço SIP do fluxo de trabalho) na caixa URI do Fluxo de Trabalho. Antes que você possa fazer isso, no entanto, é necessário realmente poder ver a caixa URI do Fluxo de Trabalho. Para exibir as opções de filtragem do Relatório da Lista de Chamadas de Grupo de Resposta, clique no botão Exibir/Ocultar Parâmetros, na parte superior esquerda da janela do relatório.

Observe que a Lista de Chamadas de Grupo de Resposta não exibe informações sobre o Código de resposta nem da ID do Diagnóstico se você manter o mouse sobre uma dessas métricas. Se precisar de mais informações, você pode observar o código de resposta e/ou a identificação de diagnóstico e, em seguida, procurar por esses valores no [relatório de falhas principais no Lync Server 2013](lync-server-2013-top-failures-report.md).

uma pergunta como esta: "Qual é o fluxo de trabalho individual que recebeu a maioria das chamadas?", é possível fazer o seguinte:

1.  No Relatório de Uso do Grupo de Resposta, defina o período desejado de tempo e depois clique na métrica Chamadas Recebidas. Isso abrirá o Relatório da Lista de Chamadas de Grupo de Resposta.

2.  Exporte os dados exibidos no Relatório da Lista de Chamadas de Grupo de Resposta. Por exemplo, você poderá exportar os dados em formato Microsoft Excel, e depois usar o Excel para converter esses dados a um arquivo de valores separados por vírgula.

3.  Execute suas análises usando o Windows PowerShell.

Por exemplo, se você salvou os dados em um arquivo denominado C\\: relatório de\\lista\_\_\_de chamadas\_em grupo de resposta a dados. csv, você pode usar o comando a seguir para retornar o número total de chamadas recebidas para cada fluxo de trabalho listado no relatório:

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

As informações serão similares a estas:

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. A tabela a seguir lista os filtros que podem ser usados com o Relatório da Lista de Chamadas de Grupo de Resposta.

### <a name="response-group-call-list-report-filters"></a>Filtros do Relatório da Lista de Chamadas de Grupo de Resposta

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
<td><p><strong>URI do Fluxo de Trabalho</strong></p></td>
<td><p>Permite limitar os dados retornados ao fluxo de trabalho do Grupo de Resposta especificado. Para usar esse filtro, insira o endereço SIP do Fluxo de Trabalho. Por exemplo:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>Chamadas</strong></p></td>
<td><p>Você pode selecionar um dos seguintes tipos de chamadas:</p>
<ul>
<li><p>Chamadas Recebidas</p></li>
<li><p>Chamadas Bem-sucedidas</p></li>
<li><p>Chamadas Oferecidas</p></li>
<li><p>Chamadas Atendidas</p></li>
<li><p>Chamadas Transferidas</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório da Lista de Chamadas de Grupo de Resposta para cada chamada recebida pelo aplicativo Grupo de Resposta.

### <a name="response-group-call-list-report-metrics"></a>Métricas do Relatório da Lista de Chamadas de Grupo de Resposta

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
<td><p><strong>Chamador</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do chamador.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fluxo de Trabalho</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do fluxo de trabalho do Grupo de Resposta.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de início</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e horário em que a chamada teve início.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de término</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e horário em que a chamada terminou.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código de resposta</strong></p></td>
<td><p>Não</p></td>
<td><p>Código da resposta SIP enviado quando a sessão falhou.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID do Diagnóstico</strong></p></td>
<td><p>Não</p></td>
<td><p>Identificador exclusivo (na forma de cabeçalho ms-diagnostics) anexado a uma mensagem SIP que fornece informações úteis para solucionar erros.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

