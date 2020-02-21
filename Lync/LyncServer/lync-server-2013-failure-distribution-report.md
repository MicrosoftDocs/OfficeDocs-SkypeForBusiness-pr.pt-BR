---
title: 'Lync Server 2013: relatório de distribuição de falhas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1531b7b103e3df6f2d165a4fd6fcd3abf100132
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a>Relatório de distribuição de falhas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-21_

O Relatório de Distribuição de Falhas classifica sessões com falha nas seguintes categorias:

  - Principais motivos diagnósticos

  - Principais modalidades

  - Principais pools

  - Principais fontes

  - Principais componentes

  - Principais usuários de origem

  - Principais usuários de destino

  - Principal usuário de origem

É possível usar essas categorias para determinar exatamente onde está ocorrendo um problema e, em alguns casos, porque o problema está ocorrendo. Por exemplo, suponha que você tenha registrado 242 sessões de áudio/vídeo com falha durante um determinado dia. Se você observar o Relatório de Distribuição de Falhas, ele poderá mostrar que 237 das sessões com falha ocorreram no pool de Dublin. Isso fornece um ótimo ponto inicial para rastrear e diagnosticar as causas por trás dessas falhas. Se você clicar no pool de Dublin na categoria **Principais pools**, você verá um Relatório de Distribuição de Falhas exclusivo desse pool. Será possível então começar a analisar por que o pool de Dublin enfrentou tantas dificuldades.

<div>

## <a name="viewing-the-failure-distribution-report"></a>Exibindo o Relatório de Distribuição de Falhas

É possível acessar o Relatório de Distribuição de Falhas a partir de qualquer um dos seguintes relatórios clicando nas medidas **Volume de falhas esperado** ou **Volume de falhas não esperado**:

  - [Relatório de falhas principais no Lync Server 2013](lync-server-2013-top-failures-report.md)

  - [Relatório de diagnóstico de conferência no Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)

  - [Relatório de diagnóstico de atividade ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

No relatório de distribuição de falhas, você pode clicar em qualquer uma das métricas a seguir para exibir o [relatório de lista de falhas no Lync Server 2013](lync-server-2013-failure-list-report.md):

  - Principais motivos diagnósticos (sessões)

  - Principais modalidades (sessões)

  - Principais pools (sessões)

  - Principais fontes (sessões)

  - Principais componentes (sessões)

  - Principais usuários de origem (sessões)

  - Principais usuários de destino (sessões)

  - Principais agentes de usuários de origem (sessões)

</div>

<div>

## <a name="using-the-failure-distribution-report"></a>Usando o Relatório de Distribuição de Falhas

Dependendo do tamanho de seu monitor e da resolução da tela, é possível que alguns dos dados apresentados no Relatório de Distribuição de Falhas sejam truncados que exibidos na tela. Por exemplo, um agente de usuário com o nome "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" poderá aparecer apenas parcialmente na tela:

UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...

Felizmente, é possível ver o nome completo mantendo o mouse sobre o valor truncado.

Um medida interessante que pode ser filtrada usando o Relatório de Distribuição de Falhas é o ID do diagnóstico. Se vir o mesmo ID do diagnóstico surgir em outros relatórios, será possível filtrar esse ID no Relatório de Distribuição de Falhas e obter uma visão bastante detalhada de exatamente onde e com que frequência esse ID foi reportado durante uma sessão com falha.

</div>

<div>

## <a name="filters"></a>Filtros

O filtro é uma maneira de retornar um conjunto de dados mais refinado e direcionado, ou ver os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Falha na Distribuição permite filtrar itens como tipo de atividade (sessão ponto a ponto ou de conferência) ou pelo ID diagnóstico que acompanha cada sessão com falha.

A tabela a seguir lista os filtros que você pode usar com o Relatório de Falha na Distribuição.

### <a name="failure-distribution-report-filters"></a>Filtros do Relatório de Falha na Distribuição.

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
<td><p>FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de atividade</strong></p></td>
<td><p>Tipo de atividade para filtrar. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Ponto a ponto</p></li>
<li><p>Conferência</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Categoria da sessão</strong></p></td>
<td><p>Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Êxito</p></li>
<li><p>Falha esperada</p></li>
<li><p>Falha inesperada</p></li>
</ul>
<p>Uma &quot;falha&quot; esperada é uma falha que deve ocorrer. Por exemplo, se um usuário configurou seu status para Não Perturbe, é previsto que qualquer chamada para ele irá falhar. Uma &quot;falha&quot; inesperada é uma falha que ocorre no que parece ser um sistema saudável de outra forma. Por exemplo, uma chamada não deveria ser terminada se o chamador for colocado em espera. Se isso ocorrer, será sinalizado como uma falha inesperada.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnóstico</strong></p></td>
<td><p>Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a>Métricas para os principais motivos diagnósticos

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base no ID diagnóstico relatado com mais frequência.

### <a name="metrics-for-top-diagnostic-reasons"></a>Métricas para os principais motivos diagnósticos

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
<td><p><strong>Rank</strong></p></td>
<td><p>Não</p></td>
<td><p>Classificação relativa das sessões com falha, com base no ID diagnóstico, que é um identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principais motivos diagnósticos</strong></p></td>
<td><p>Não</p></td>
<td><p>ID diagnóstico gerado em uma sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões com falha em que ID diagnóstico especificado foi gerado.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a>Métricas para as principais modalidades

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nas modalidades de sessão que apresentaram mais falhas.

### <a name="metrics-for-top-modalities"></a>Métricas para as principais modalidades

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
<td><p><strong>Rank</strong></p></td>
<td><p>Não</p></td>
<td><p>Classificação relativa com base na sessão com falha baseada no tipo de sessão (por exemplo, conferência de áudio/vídeo ou sessão de transferência de arquivo ponto a ponto).</p></td>
</tr>
<tr class="even">
<td><p><strong>Principais modalidades</strong></p></td>
<td><p>Não</p></td>
<td><p>Tipo de sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões com falha envolvendo a modalidade especificada.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a>Métricas para os principais pools

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos pools que apresentaram mais falhas.

### <a name="metrics-for-top-pools"></a>Métricas para os principais pools

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
<td><p><strong>Rank</strong></p></td>
<td><p>Não</p></td>
<td><p>Classificação relativa de sessões com falha com base no pool de registradores ou no servidor de borda onde a sessão foi conduzida.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principais pools</strong></p></td>
<td><p>Não</p></td>
<td><p>Nome do pool de registradores ou servidor de borda.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões com falha por pool de registradores ou servidor de borda.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a>Métricas para as principais fontes

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos computadores que apresentaram mais falhas.

### <a name="metrics-for-top-sources"></a>Métricas para as principais fontes

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
<td><p><strong>Rank</strong></p></td>
<td><p>Não</p></td>
<td><p>Classificação relativa das sessões com falha por computador.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principais fontes</strong></p></td>
<td><p>Não</p></td>
<td><p>Nome do computador envolvido na sessão com falha.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões com falha por computador.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a>Métricas para os principais componentes

A tabela a seguir lista as informações fornecidas no relatório de falha de distribuição, com base nos componentes do Microsoft Lync Server 2010 que apresentaram mais falhas.

### <a name="metrics-for-top-components"></a>Métricas para os principais componentes

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
<td><p><strong>Rank</strong></p></td>
<td><p>Não</p></td>
<td><p>Classificação relativa de sessões com falha com base no componente do Lync Server 2010 (por exemplo, ExumRouting, GroupChat ou MediationServer).</p></td>
</tr>
<tr class="even">
<td><p><strong>Principais componentes</strong></p></td>
<td><p>Não</p></td>
<td><p>Nome do componente envolvido na sessão com falha.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões com falha por componente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a>Métricas para os principais usuários "De"

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos usuários que apresentaram mais falhas quando tentaram chamar alguém (conhecidos como usuários "De").

### <a name="metrics-for-top-from-users"></a>Métricas para os principais usuários "Para"

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
<td><p><strong>Rank</strong></p></td>
<td><p>Não</p></td>
<td><p>Classificação relativa das sessões com falha, com base no usuário convidado a entrar na sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principais usuários "Para"</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do usuário convidado para entrar na sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões com falha por usuário.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a>Métricas para os principais usuários

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos usuários que apresentaram mais falhas quando o outro usuário tentou chamá-los (conhecidos como usuários "Para").


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
<td><p><strong>Rank</strong></p></td>
<td><p>Não</p></td>
<td><p>Classificação relativa das sessões com falha, com base no usuário que iniciou a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principais usuários "Para"</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do usuário que iniciou a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões com falha por usuário.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a>Métricas para os principais agentes do usuário

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base no software de ponto de extremidade que apresentou mais falhas.

### <a name="metrics-for-top-user-agents"></a>Métricas para os principais agentes do usuário

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
<td><p><strong>Rank</strong></p></td>
<td><p>Não</p></td>
<td><p>Classificação relativa de sessões com falha, com base no agente do usuário (software) envolvido na sessão. Por exemplo: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principais agentes do usuário</strong></p></td>
<td><p>Não</p></td>
<td><p>Nome do agente do usuário envolvido na sessão com falha.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões com falha por agente do usuário.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

