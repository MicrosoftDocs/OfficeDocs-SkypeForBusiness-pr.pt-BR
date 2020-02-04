---
title: 'Lync Server 2013: relatório de atividade do usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 583c647ac3cdab290f1833539abbbd033ea89410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a>Relatório de atividade do usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-02-27_

O Relatório de Atividades do Usuário oferece uma lista detalhada das sessões ponto a ponto e de conferência realizadas pelos usuários em um determinado período. Diferente de muitos dos Relatórios de Monitoramento, o Relatório de Atividades do Usuário vincula cada chamada a usuários individuais. Por exemplo, as sessões ponto a ponto especificam URIs do SIP da pessoa que iniciou a chamada (o usuário de origem) e a pessoa que está sendo chamada (o usuário de destino). Se as informações forem ampliadas para uma conferência, será possível ver uma lista de todos os participantes da conferência e a função que desempenham na conferência.

O Relatório de Atividades do Usuário é referenciado algumas vezes como o relatório do "suporte técnico". Isso se deve ao fato de o relatório ser sempre usado pela equipe do suporte técnico para recuperar informações sobre a sessão para um usuário específico. É possível filtrar chamadas feitas para ou por um usuário individual simplesmente digitando o URI do SIP do usuário na caixa URI do usuário.

Se você fizer isso, o relatório de atividade do usuário retornará informações para qualquer usuário cujo URI SIP comece com a cadeia de caracteres especificada. Por exemplo, se você digitar **ken** na caixa URI, o Relatório de Atividades do usuário localizará **Ken**.Myer@litwareinc.com. No entanto, ele localizará também esses usuários:

  - **ken**azi@litwareinc.com

  - **ken**burg@litwareinc.com

  - **Ken**.Sanchez@litwareinc.com

  - **Ken**nedy@litwareinc.com

Para garantir que somente informações sobre Ken Myer sejam retornadas, digite sua URI completa (Ken.Myer@litwareinc.com) na caixa de pesquisa ou, pelo menos, digite a URl do Ken o bastante para distingui-lo de outros usuários na organização. Por exemplo:

Ken.my

<div>

## <a name="to-access-the-user-activity-report"></a>Para acessar o Relatório de Atividades do Usuário

O Relatório de Atividades do Usuário é acessado pela home page dos Relatórios de Monitoramento. Você também pode acessar o relatório de atividade do usuário clicando na métrica de URI de usuário no [relatório de inventário de telefone IP do Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md). No Relatório de Atividades do Usuário, ao clicar em URI da Conferência (para uma conferência), você será levado para o Relatório Detalhado de Conferências. Da mesma forma, clicar na métrica de detalhes de uma chamada ponto a ponto leva você ao [relatório de detalhes da sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a>Fazendo o melhor uso do relatório de atividades do usuário

Embora haja muitas informações relevantes no Relatório de Atividades do Usuário, essas informações podem, por vezes, ser difíceis de localizar. Por exemplo, todas as atividades do usuário que ocorrem em sua organização durante um período especificado são incluídas no relatório de atividades do usuário; Isso significa que, em seguida, incluído no relatório há informações sobre quais usuários realmente usaram o Microsoft Lync Server 2013 de alguma maneira.

<div>


> [!WARNING]  
> Tecnicamente, é possível que algumas atividades do usuário possam estar desgravadas: enquanto o Lync Server se empenha para manter as informações sobre todas as chamadas telefônicas, é possível que uma chamada tenha sido feita sem as informações sobre essa chamada sendo gravada no banco de dados. O Lync Server foi projetado para fornecer uma visão extremamente precisa, mas não necessariamente perfeita sobre como o Lync Server 2013 está sendo usado. (O fato não há nenhuma garantia de que 100% de todas as chamadas sejam registradas explica por que o monitoramento do Lync Server não deve ser usado como um sistema de cobrança.)<BR>Segundo, um relatório de relatório de monitoramento só pode exibir, no máximo, 1.000 registros. Dependendo da quantidade de usuários que você tem e também de período com o qual está trabalhado, isso significa que sua consulta pode não retornar todos os dados realmente armazenados no banco de dados.



</div>

  - Quais usuários usaram realmente o sistema durante este período?

  - Quais dentre meus usuários foram os mais ativos durante este período?

  - Os usuários que fazem a maioria das chamadas são também aqueles que participam da maioria das sessões de mensagens instantâneas?

Se precisar responder a essas perguntas, será possível exportar os dados recuperados pelos Relatórios de Monitoramento para uma planilha do Excel. Utilize essa planilha e/ou um arquivo de valores separados por vírgulas para analisar os dados como faz o Relatório de Atividades do Usuário. Por exemplo, suponha que os dados do relatório tenham sido exportados para o Excel e depois para um arquivo de valores separados por vírgulas. Nesse ponto, você pode importar os dados do. CSV para o Windows PowerShell usando um comando semelhante a este:

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

Depois que os dados forem importados, você poderá usar comandos simples do Windows PowerShell para ajudar a responder suas perguntas. Por exemplo, este comando retorna uma lista de usuários exclusivos que atuaram como "usuário de origem" em pelo menos uma sessão:

    $x | Group-Object "From user" | Select Name | Sort-Object Name

Em outras palavras:

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

Este comando lista os usuários exclusivos (com base no número total de sessões das quais participaram:

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Este retorna dados semelhantes a estes:

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

Este comando limita as sessões reportadas àquelas que incluíram áudio como modalidade:

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Se você pousar o mouse sobre qualquer ID do diagnóstico mostrado no relatório, uma dica de ferramenta será exibida descrevendo o ID.

</div>

<div>

## <a name="filters"></a>Filtros

O filtro é uma maneira de retornar um conjunto de dados mais refinado e direcionado, ou ver os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Atividades do Usuário permite filtrar os dados retornados com base em itens como tipo de atividade (isto é, sessão ponto a ponto ou de conferência) ou pelo endereço SIP do usuário (permitindo exibir as atividades para um usuário). Você também pode escolher como os dados serão agrupados; neste caso, os usos são agrupados por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que você pode usar com o Relatório de Atividades do Usuário.

### <a name="user-activity-report-filters"></a>Filtros do relatório de atividades do usuário

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
<p>7/17/12012 1:00 PM</p>
<p>Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/17/12012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/13/2012</p>
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Até</strong></p></td>
<td><p>Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</p>
<p>7/17/12012 1:00 PM</p>
<p>Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/17/12012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/13/2012</p>
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
<td><p>A Modalidade disponível para você varia de acordo com o Tipo de Atividade selecionado. Se o tipo de atividade for ponto a ponto, você poderá selecionar mensagens instantâneas; Transferência de arquivos; Compartilhamento de aplicativos; Voz ou vídeo como a modalidade.</p>
<p>Se o Tipo de Atividade for Conferência, você poderá selecionar conferência Telefônica de Mensagem Instantânea; conferência da Web; Compartilhamento de Aplicativos; conferência de Voz/Vídeo; ou conferência Telefônica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Categoria da sessão</strong></p></td>
<td><p>Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Sucesso</p></li>
<li><p>Falha esperada</p></li>
<li><p>Falha inesperada</p></li>
</ul>
<p>Uma &quot;falha&quot; esperada é uma falha que se espera que aconteça; por exemplo, se um usuário tiver definido seu status como não incomodar, você esperaria qualquer chamada para esse usuário falhar. Uma &quot;falha&quot; inesperada é uma falha que ocorre em que parece ser um sistema de outra forma saudável. Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera. Se isso ocorrer, será sinalizado como uma falha inesperada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prefixo de URI do usuário</strong></p></td>
<td><p>Endereço SIP para o usuário. Para exibir registros somente para o usuário Ken Myer, digite o endereço SIP de Ken Myer. Por exemplo:</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para a sessões ponto a ponto (isto é, as que envolvem apenas dois participantes).

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
<th>Você pode classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Detalhe</strong></p></td>
<td><p>Não</p></td>
<td><p>Quando você clica neste item, é mostrado o Relatório de Detalhes de Sessão Ponto a Ponto para a sessão selecionada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Usuário "De"</strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP do usuário que iniciou a sessão ponto a ponto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Usuário "Para"</strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP do usuário que entrou na sessão ponto a ponto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalidades</strong></p></td>
<td><p>Sim</p></td>
<td><p>Tipo de comunicação usado na sessão. Por exemplo, IM, áudio ou transferência de arquivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora do convite</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que o convite inicial para entrar na sessão ponto a ponto foi enviado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora da resposta</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que &quot;o&quot; usuário para aceitou o convite da sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de término</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que a sessão ponto a ponto terminou.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID do Diagnóstico</strong></p></td>
<td><p>Sim</p></td>
<td><p>Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que fornece informações úteis para resolução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não os incluem), e as IDs de diagnóstico são relatadas somente em sessões com algum tipo de problema.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Métricas para sessões de conferência

A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para a sessões de conferência (isto é, as que envolvem três ou mais participantes).

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
<th>Você pode classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>URI de conferência</strong></p></td>
<td><p>Sim</p></td>
<td><p>Identificador exclusivo da conferência. Quando você clica neste item, é mostrado o Relatório de Detalhes da Conferência para a sessão selecionada. Quando você expande esse item, o relatório mostra as informações sobre os participantes. Para obter detalhes, consulte &quot;a seção métricas para&quot; participantes da conferência mais adiante neste tópico.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizador</strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP do usuário que organizou a conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Sim</p></td>
<td><p>Nome do Servidor de Borda (se houver) usado na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora inicial</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que a conferência começou.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora final</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que a conferência terminou.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a>Métricas para participantes da conferência

A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para cada participante de uma conferência.

### <a name="metrics-for-conference-participants"></a>Métricas para participantes da conferência

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
<td><p><strong>Função</strong></p></td>
<td><p>Não</p></td>
<td><p>Função do usuário na conferência (por exemplo, Apresentador).</p></td>
</tr>
<tr class="even">
<td><p><strong>Participante</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do usuário.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conectividade</strong></p></td>
<td><p>Não</p></td>
<td><p>Tipo de conexão da rede. Por exemplo &quot;, de&quot; interno para conexão interna &quot;ou da&quot; PSTN para usuários de discagem.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora da ingresso</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora em que o usuário entrou na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora da saída</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora em que o usuário saiu da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID do Diagnóstico</strong></p></td>
<td><p>Não</p></td>
<td><p>Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

