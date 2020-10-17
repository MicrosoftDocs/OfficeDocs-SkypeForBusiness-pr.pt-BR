---
title: 'Lync Server 2013: relatório detalhado de sessão ponto a ponto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93558a56962f34a38b80ebca8a0fd668394a4386
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524358"
---
# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a>Relatório detalhado de sessão ponto a ponto no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-06_

O Relatório Detalhado de Sessão Ponto a Ponto retorna informações detalhadas sobre uma sessão ponto a ponto. Por exemplo, se você selecionar uma sessão de mensagens instantâneas, o relatório informará o número de mensagens enviadas por cada um dos dois usuários na seção.

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Acessando o Relatório Detalhado de Sessão Ponto a Ponto

O Relatório Detalhado de Sessão Ponto a Ponto pode ser acessado a partir de qualquer um dos relatórios a seguir (todos os quais podem ser acessados a partir da home page Relatórios de Monitoramento):

  - Relatório de Inventário de Telefones IP

  - Relatório de Atividades do Usuário

  - Relatório de Controle de Admissão de Chamadas

  - Relatório de Lista de Falhas

A partir do relatório de detalhes de sessão ponto a ponto, você pode acessar o [relatório de diagnóstico no Lync Server 2013](lync-server-2013-diagnostic-report.md) clicando na métrica relatório de diagnóstico (detalhes). Você também pode acessar o Relatório das Principais Falhas clicando em uma destas duas métricas:

  - Resposta

  - ID de diagnóstico

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Usando o Relatório Detalhado de Sessão Ponto a Ponto da melhor maneira possível

O Relatório Detalhado de Sessão Ponto a Ponto inclui um grande número de métricas, muitas das quais os administradores de sistemas podem desconhecer. Muitas vezes, porém, você pode exibir uma dica de ferramenta que oferece uma breve descrição da métrica. Para isso, basta manter o cursor do mouse sobre o rótulo da métrica.

Observe que as métricas mostradas em determinado relatório dependerão do tipo de sessão ponto a ponto selecionada. Uma sessão de áudio/vídeo mostrará um conjunto de métricas diferente de uma sessão de mensagens instantâneas.

Você também pode manter o cursor do mouse sobre as métricas Código de resposta e ID de diagnóstico para obter uma descrição desses valores:

</div>

<div>

## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o relatório de Detalhes de Sessão Ponto a Ponto.

</div>

<div>

## <a name="session-information-metrics"></a>Métricas de informações da sessão

A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada sessão.

### <a name="session-information-metrics"></a>Métricas de informações da sessão

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
<td><p><strong>FQDN do pool</strong></p></td>
<td><p>Nome de domínio totalmente qualificado (FQDN) do pool de Registradores ou Servidor de Borda envolvido na sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora do convite</strong></p></td>
<td><p>Data e hora em que o convite de sessão foi originalmente enviado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora da resposta</strong></p></td>
<td><p>Data e hora em que a aceitação do convite foi recebida.</p></td>
</tr>
<tr class="even">
<td><p><strong>Do usuário</strong></p></td>
<td><p>Endereço SIP do usuário que iniciou a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Do agente usuário</strong></p></td>
<td><p>Software usado pelo ponto de extremidade do usuário que iniciou a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>É Usuário interno de origem</strong></p></td>
<td><p>Indica se o usuário que iniciou a sessão estava conectado à rede interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>É Usuário de origem integrado ao telefone de mesa</strong></p></td>
<td><p>Indica se o ponto de extremidade usado pelo usuário que iniciou a sessão está integrado ao seu telefone de mesa.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prioridade da Sessão</strong></p></td>
<td><p>Prioridade atribuída à sessão. As prioridades válidas são: Desconhecida; Não Urgente; Normal; Urgente; e Emergência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código de resposta</strong></p></td>
<td><p>Código de resposta SIP enviado quando a sessão falhou.</p></td>
</tr>
<tr class="even">
<td><p><strong>Front-End</strong>.</p></td>
<td><p>Nome do Servidor Front-End usado na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora da captura</strong></p></td>
<td><p>Data e hora em que a sessão de informações foi gravada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora final</strong></p></td>
<td><p>Data e hora em que a sessão foi encerrada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Para o usuário</strong></p></td>
<td><p>Endereço SIP do usuário que foi convidado para a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Para o agente do usuário</strong></p></td>
<td><p>Software usado pelo ponto de extremidade do usuário que foi convidado para a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>É Usuário interno de destino</strong></p></td>
<td><p>Indica se o usuário que foi convidado para a sessão estava conectado à rede interna.</p></td>
</tr>
<tr class="even">
<td><p><strong>É Usuário de destino integrado ao telefone de mesa</strong></p></td>
<td><p>Indica se o ponto de extremidade usado pelo usuário que foi convidado para a sessão está integrado ao seu telefone de mesa.</p></td>
</tr>
<tr class="odd">
<td><p><strong>É sessão repetida</strong></p></td>
<td><p>Indica se a sessão é uma tentativa para repetir uma sessão que falhou anteriormente.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnóstico</strong></p></td>
<td><p>Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros. Mantenha o mouse sobre o número de identificação para exibir informações adicionais sobre essa identificação.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a>Métricas para modalidades

A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada sessão de modalidade.

### <a name="metrics-for-modalities"></a>Métricas para modalidades

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
<td><p><strong>Modalidades</strong></p></td>
<td><p>Não</p></td>
<td><p>Modalidades usadas na sessão. Por exemplo, mensagens instantâneas ou transferência de arquivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Mensagens do usuário de origem</strong></p></td>
<td><p>Não</p></td>
<td><p>Número de mensagens enviadas pelo usuário que iniciou a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Mensagens do usuário de destino</strong></p></td>
<td><p>Não</p></td>
<td><p>Número de mensagens enviadas pelo usuário que foi convidado para a sessão.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a>Métricas para relatórios de diagnóstico

A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada relatório de diagnóstico.

### <a name="metrics-for-diagnostic-reports"></a>Métricas para relatórios de diagnóstico

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
<td><p>Quando você clica nesse item, o relatório mostra o Relatório de Diagnóstico da sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora do relatório</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora em que o relatório foi gravado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Solicitação</strong></p></td>
<td><p>Não</p></td>
<td><p>Tipo de solicitação SIP. Por exemplo, INVITE ou BYE.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnóstico</strong></p></td>
<td><p>Não</p></td>
<td><p>Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de conteúdo</strong></p></td>
<td><p>Não</p></td>
<td><p>Tipo de conteúdo de mídia usado na conferência. Por exemplo, um tipo de conteúdo comum é Application/sdp. O protocolo SDP  é um protocolo padrão de Internet usado para comunicados de sessão, convites de sessão e outras formas de início de sessão multimídia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Relatado por</strong></p></td>
<td><p>Não</p></td>
<td><p>Computador (isso é, o cliente ou servidor) que relatou o problema.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

