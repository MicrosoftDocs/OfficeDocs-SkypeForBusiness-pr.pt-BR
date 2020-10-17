---
title: 'Lync Server 2013: relatório de atividades do usuário'
description: 'Lync Server 2013: relatório de atividades do usuário.'
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
ms.openlocfilehash: 0e959020e6ace6c72ecd570039d30a9ecc174c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569827"
---
# <a name="user-activity-report-in-lync-server-2013"></a>Relatório de atividades do usuário no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-02-27_

O relatório de atividades do usuário fornece uma lista detalhada das sessões ponto a ponto e de conferência executadas pelos usuários em um determinado período de tempo. Ao contrário de muitos dos relatórios de monitoramento, o relatório de atividades do usuário vincula cada chamada a usuários individuais. Por exemplo, sessões ponto a ponto especificam os URIs SIP da pessoa que iniciou a chamada (o usuário de) e a pessoa que está sendo chamada (o para o usuário). Se você expandir as informações de uma conferência, verá uma lista de todos os participantes da conferência e a função que eles realizaram para a conferência.

O relatório de atividades do usuário às vezes é chamado de relatório "Help Desk". Isso ocorre porque o relatório é geralmente usado pela equipe de assistência técnica para recuperar informações de sessão de um usuário específico. Você pode filtrar por chamadas feitas ou feitas por um usuário individual simplesmente digitando o URI do SIP do usuário na caixa prefixo de URI do usuário.

Se você fizer isso, o relatório de atividades do usuário retornará informações para qualquer usuário cujo URI de SIP comece com a cadeia de caracteres especificada. Por exemplo, se você digitar **Ken** na caixa URI, o relatório de atividades do usuário localizará **Ken**. Myer@litwareinc.com. No entanto, ele também localizará estes usuários:

  - **ken**Azi@litwareinc.com

  - **ken**Burg@litwareinc.com

  - **Ken**. Sanchez@litwareinc.com

  - **Ken**Nedy@litwareinc.com

Para garantir que as informações somente para Ken Myer sejam retornadas, digite o URI completo (Ken.Myer@litwareinc.com) na caixa de pesquisa ou pelo menos o tipo de URI de Ken para distingui-lo exclusivamente de outros usuários em sua organização. Por exemplo:

Ken.my

<div>

## <a name="to-access-the-user-activity-report"></a>Para acessar o relatório de atividades do usuário

O relatório de atividades do usuário é acessado a partir da Home Page de relatórios de monitoramento. Você também pode acessar o relatório de atividades do usuário clicando na métrica URI do sistema de [telefonia IP no Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md). No relatório de atividades do usuário, clicar no URI da conferência (para uma conferência) leva você para o relatório de detalhes da conferência. Da mesma forma, clicar na métrica de detalhes de uma chamada ponto a ponto leva você para o [relatório de detalhes de sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a>Fazendo o melhor uso do relatório de atividades do usuário

Embora haja muitas informações boas no relatório de atividades do usuário, essas informações podem, às vezes, ser difíceis de localizar. Por exemplo, toda a atividade do usuário que ocorre na sua organização durante um período especificado é incluída no relatório de atividades do usuário; Isso significa que, neste caso, as informações sobre quais usuários realmente usaram o Microsoft Lync Server 2013 de alguma forma.

<div>


> [!WARNING]  
> Tecnicamente, é possível que alguma atividade de usuário seja não gravada: enquanto o Lync Server se esforça para manter as informações sobre todas as chamadas telefônicas, é possível que uma chamada tenha sido feita sem que as informações sobre a chamada sejam gravadas no banco de dados. O Lync Server foi projetado para fornecer uma visão extremamente precisa, mas não necessariamente perfeita, como o Lync Server 2013 está sendo usado. (O fato de não haver garantia de que 100% de todas as chamadas são registradas explica por que o monitoramento do Lync Server não deve ser usado como um sistema de cobrança.)<BR>Segundo, um relatório de relatório de monitoramento só pode exibir, no máximo, 1.000 registros. Dependendo da quantidade de atividade do usuário que você tem e, dependendo do período de tempo com o qual você está trabalhando, isso significa que a consulta pode não retornar todos os dados realmente armazenados no banco de dados.



</div>

  - Quais usuários usaram realmente o sistema durante esse período de tempo?

  - Quais dos meus usuários foram os mais ativos durante esse período de tempo?

  - Os usuários que fazem a maioria das chamadas são também aqueles que participam da maioria das sessões de mensagens instantâneas?

Se você precisar responder a perguntas como esta, é possível exportar os dados recuperados pelos relatórios de monitoramento para uma planilha do Excel. Em seguida, você usa essa planilha e/ou um arquivo de valores separados por vírgulas para analisar os dados de forma que o relatório de atividades do usuário. Por exemplo, suponha que você tenha exportado os dados do relatório para o Excel e, em seguida, para um arquivo de valores separados por vírgulas. Nesse ponto, você pode importar os dados do. CSV para o Windows PowerShell usando um comando semelhante a este:

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

Depois que os dados forem importados, você poderá usar comandos simples do Windows PowerShell para ajudar a responder suas perguntas. Por exemplo, este comando retorna uma lista de usuários exclusivos que serviam como "de usuário" em pelo menos uma sessão:

    $x | Group-Object "From user" | Select Name | Sort-Object Name

Em outras palavras:

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

Este comando lista os usuários exclusivos (com base no número total de sessões nas quais participaram:

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Ele retorna dados semelhantes a isto:

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

Este comando limita as sessões relatadas àquelas que incluíram áudio como modalidade:

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Se você mantiver o mouse sobre qualquer ID de diagnóstico mostrado no relatório, uma dica de ferramenta será exibida descrevendo essa ID.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. Por exemplo, o relatório de atividades do usuário permite que você filtre os dados retornados com base em coisas como o tipo de atividade (ou seja, sessões ponto a ponto ou sessões de conferência) ou pelo endereço SIP do usuário (permitindo que você exiba as atividades de um usuário). Também é possível escolher como os dados devem ser agrupados. Nesse caso, os usos são agrupados por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o relatório de atividades do usuário.

### <a name="user-activity-report-filters"></a>Filtros de relatórios de atividades do usuário

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
<td><p><strong>Tipo de atividade</strong></p></td>
<td><p>Tipo de atividade. Selecione um dos seguintes:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Ponto a ponto</p></li>
<li><p>Conferência</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalidade</strong></p></td>
<td><p>A modalidade disponível para você varia de acordo com o tipo de atividade SELECT. Se o tipo de atividade for ponto a ponto, você poderá selecionar IM; Transferência de arquivos; Compartilhamento de aplicativos; Voice ou vídeo como a modalidade.</p>
<p>Se o tipo de atividade for conferência, você poderá selecionar conferência telefônica de mensagens instantâneas; Conferência da Web; Compartilhamento de aplicativos; Conferência de voz/vídeo; ou conferência telefônica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Categoria da sessão</strong></p></td>
<td><p>Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Sucesso</p></li>
<li><p>Falha esperada</p></li>
<li><p>Falha inesperada</p></li>
</ul>
<p>Uma &quot; falha esperada &quot; é uma falha que deve ocorrer; por exemplo, se um usuário tiver definido seu status como não incomodar, você esperaria que qualquer chamada para esse usuário falhe. Uma &quot; falha inesperada &quot; é uma falha que ocorre no que parece ser um sistema saudável de outra forma. Por exemplo, uma chamada não deveria ser terminada se o chamador for colocado em espera. Se isso ocorrer, será sinalizado como uma falha inesperada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prefixo URI do usuário</strong></p></td>
<td><p>Endereço SIP para o usuário. Para exibir registros apenas para o usuário Ken Myer, você precisa inserir o endereço SIP de Ken Myer. Por exemplo:</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para sessões ponto a ponto (ou seja, sessões que envolvem apenas dois participantes).

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
<td><p>Quando você clica nesse item, o relatório mostra o relatório de detalhes de sessão ponto a ponto da sessão selecionada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Do usuário </strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP do usuário que iniciou a sessão ponto a ponto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Para usuário</strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP do usuário que ingressou na sessão ponto a ponto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalidades</strong></p></td>
<td><p>Sim</p></td>
<td><p>Tipo de comunicação usada na sessão. Por exemplo, IM, áudio ou transferência de arquivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora do convite</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que o convite inicial para entrar na sessão ponto a ponto foi enviado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora da resposta</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que &quot; o &quot; usuário deve aceitar o convite da sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de término</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que a sessão ponto a ponto terminou.</p></td>
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

A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).

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
<td><p>Identificador de conferência exclusivo. Quando você clica nesse item, o relatório mostra o relatório de detalhes da conferência da sessão selecionada. Quando você expande esse item, o relatório mostra informações sobre os participantes da conferência. Para obter detalhes, consulte a &quot; seção métricas para participantes da conferência &quot; mais adiante neste tópico.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizador</strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP do usuário que organizou a conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Sim</p></td>
<td><p>Nome do servidor de borda (se houver) usado na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de início</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que a conferência começou.</p></td>
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

## <a name="metrics-for-conference-participants"></a>Métricas para participantes da conferência

A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para cada participante de uma conferência.

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
<th>É possível classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Função</strong></p></td>
<td><p>Não</p></td>
<td><p>Função de conferência (por exemplo, apresentador) para o usuário.</p></td>
</tr>
<tr class="even">
<td><p><strong>Participante</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do usuário.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conectividade</strong></p></td>
<td><p>Não</p></td>
<td><p>Tipo de conexão de rede. Por exemplo, &quot; de interno &quot; para conexão interna ou &quot; da PSTN &quot; para usuários de discagem.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de ingresso</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora em que o usuário entrou na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de saída</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora em que o usuário saiu da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnóstico</strong></p></td>
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

