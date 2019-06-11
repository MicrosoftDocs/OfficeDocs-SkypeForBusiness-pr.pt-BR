---
title: 'Lync Server 2013: relatório de detalhes da conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac598c3f85211ad97f2d6266b74b6c524d76d006
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a>Relatório de detalhes da conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

O Relatório de Detalhe da Conferência fornece informações detalhadas sobre todos os usuários que participaram de uma conferência. Por exemplo, você pode ver tal informação como a data e hora que um usuário participou da conferência, a data e hora que o usuário saiu da conferência e o agente do usuário do ponto de extremidade que foi usado para conectar o usuário à conferência. Também é possível ver informações da função do usuário em cada conferência (por exemplo, Apresentador ou Participante). Talvez, o mais importante, você pode ver rapidamente quais usuários participaram com sucesso e concluíram a conferência e quais usuários não puderam participar e concluir a conferência.

<div>

## <a name="accessing-the-conference-detail-report"></a>Acessar o Relatório de Detalhe da Conferência

O Relatório de Detalhe da Conferência pode ser acessado pelos seguintes relatórios:

  - O [relatório de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-call-admission-control-report.md) (clicando na métrica de detalhes de uma conferência)

  - O [relatório lista de falhas no Lync Server 2013](lync-server-2013-failure-list-report.md) (clicando na métrica da conferência)

  - O [relatório de atividade do usuário no Lync Server 2013](lync-server-2013-user-activity-report.md) (clicando na métrica de URI de conferência)

No relatório de detalhes da conferência, você pode acessar o [relatório de diagnóstico no Lync Server 2013](lync-server-2013-diagnostic-report.md) clicando no relatório de diagnóstico (detalhe) métrica.

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
<th>Você pode classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>URI de conferência</strong></p></td>
<td></td>
<td><p>URI atribuído à conferência. Por exemplo:</p>
<p>sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDN do pool</strong></p></td>
<td></td>
<td><p>Nome de domínio totalmente qualificado do pool do Registrador ou Servidor de Borda envolvido em uma sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora inicial</strong></p></td>
<td></td>
<td><p>Data e hora de início da sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizador</strong></p></td>
<td></td>
<td><p>Endereço SIP do usuário que organizou a conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora final</strong></p></td>
<td></td>
<td><p>Data e hora em que a conferência terminou.</p></td>
</tr>
</tbody>
</table>


A tabela a seguir lista as informações oferecidas na Seção de Participação da Conferência do Relatório de Detalhe da Conferência.

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
<th>Você pode classificar este item?</th>
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
<td><p>Função (por exemplo, Apresentador) desempenhada pelo participante da conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conectividade</strong></p></td>
<td></td>
<td><p>Conectividade de rede (normalmente Interna ou Externa) para o participante.</p></td>
</tr>
<tr class="even">
<td><p>Hora da ingresso</p></td>
<td></td>
<td><p>Data e hora de ingresso do participante na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora da saída</strong></p></td>
<td></td>
<td><p>Data e hora de saída do participante da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente do usuário</strong></p></td>
<td></td>
<td><p>Identificador do software usado pelo ponto de extremidade do participante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relatórios de diagnóstico</strong></p></td>
<td></td>
<td><p>Fornece informações de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de ingresso na conferência e IDs de diagnósticos para sessões com falha.</p></td>
</tr>
</tbody>
</table>


A tabela a seguir lista as informações fornecidas na seção de modalidades de conferência do relatório de detalhes da conferência.

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
<th>Você pode classificar este item?</th>
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
<td><p><strong>Hora da ingresso</strong></p></td>
<td></td>
<td><p>Data e hora de ingresso do participante na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora da saída</strong></p></td>
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
<td><p>Fornece informações de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de ingresso na conferência e IDs de diagnósticos para sessões com falha.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

