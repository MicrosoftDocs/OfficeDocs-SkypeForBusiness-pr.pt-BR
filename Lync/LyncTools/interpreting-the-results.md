---
title: Interpretação dos resultados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d02f69f8ea1c8eb7df004e063dba39f03bbe8b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>Interpretação dos resultados

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

A ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool.exe) tem vários contadores que você pode usar para entender o que o cliente está fazendo e se ele está encontrando problemas.

<div>

## <a name="client-counters"></a>Contadores de cliente

Cada instância do LyncPerfTool.exe que está sendo executada tem uma instância separada dos contadores. Cada instância é nomeada por ID de processo.

Se os clientes estiverem sobrecarregados, poderão ocorrer problemas. Para evitar esses problemas, faça o seguinte:

1.  Monitore a CPU e o uso de memória nos computadores clientes. Se a CPU estiver consistentemente acima de 90%, reduza o número de usuários.

2.  Se o espaço de memória for alto, você poderá encontrar problemas se o arquivo de paginação não for grande o suficiente. Verifique se o encargo de confirmação não está atingindo o limite no computador. Se você estiver executando limites de memória, considere aumentar o tamanho do arquivo de paginação ou reduzir o número de usuários

As tabelas a seguir listam os principais contadores de desempenho do LyncPerfTool.

**Informações gerais**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tempo gasto em minutos</p></td>
<td><p>Tempo gasto desde o início do processo.</p></td>
</tr>
<tr class="even">
<td><p>Pontos de extremidade ativos</p></td>
<td><p>Número de pontos de extremidade conectados atualmente ao servidor.</p></td>
</tr>
<tr class="odd">
<td><p>Logons com falha</p></td>
<td><p>Número total de falhas de entrada de ponto de extremidade.</p></td>
</tr>
<tr class="even">
<td><p>Tentativas de logon</p></td>
<td><p>Número total de tentativas de entrada de ponto de extremidade.</p></td>
</tr>
<tr class="odd">
<td><p>Pontos de extremidade desconectados</p></td>
<td><p>Número total de pontos de extremidade que foram desconectados.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Informações de presença**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas de setpresence</p></td>
<td><p>Número total de tentativas de alteração de presença. Para diferentes tipos de alterações de presença, confira contador de desempenho de chamadas de setpresence (tipo de presença).</p></td>
</tr>
<tr class="even">
<td><p>Respostas de NNN para setpresence</p></td>
<td><p>Número total de códigos de resposta nnn recebidos do servidor.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas de getpresence</p></td>
<td><p>Número total de tentativas de solicitação de presença de obtenção.</p></td>
</tr>
<tr class="even">
<td><p>Respostas de NNN para getpresence</p></td>
<td><p>Número total de códigos de resposta nnn recebidos do servidor.</p></td>
</tr>
</tbody>
</table>


**Informações do serviço de catálogo de endereços**

Esta categoria inclui contadores usados para monitorar downloads de arquivo do serviço de catálogo de endereços (ABS) e solicitações de serviço de consulta à Web do catálogo de endereços.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tentativa de downloads de arquivo completo/Delta do ABS</p></td>
<td><p>Número total de solicitações de download de arquivo completo ou Delta tentadas.</p></td>
</tr>
<tr class="even">
<td><p>Downloads de arquivo completo/Delta do ABS bem-sucedido</p></td>
<td><p>Número total de solicitações de download de arquivo completo ou Delta tentadas.</p></td>
</tr>
<tr class="odd">
<td><p>Contadores relacionados ao serviço de consulta da Web do catálogo de endereços</p></td>
<td><p>Contadores relacionados ao download de arquivos do catálogo de endereços.</p></td>
</tr>
<tr class="even">
<td><p>Tentativa de chamadas WS do ABS</p></td>
<td><p>Número total de tentativas de solicitações de serviço de consulta à Web do catálogo de endereços.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas WS WS bem-sucedidas</p></td>
<td><p>Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta bem-sucedido.</p></td>
</tr>
<tr class="even">
<td><p>Falha nas chamadas WS do ABS</p></td>
<td><p>Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta de erro.</p></td>
</tr>
</tbody>
</table>


**Informações da lista de distribuição (DL)**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tentativas de chamadas</p></td>
<td><p>Número total de solicitações de serviço Web de expansão de lista de distribuição (DLX) tentadas.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas com êxito</p></td>
<td><p>Número total de solicitações de serviço Web do DLX que retornaram um código de resposta bem-sucedido.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas com falha</p></td>
<td><p>Número total de solicitações de serviço Web do DLX que retornaram um código de resposta de erro.</p></td>
</tr>
</tbody>
</table>


**Informações básicas de VoIP**

Os contadores de desempenho listados abaixo relatam números para todas as chamadas de VoIP (voz sobre IP), incluindo chamadas para servidor de mediação, servidor de conferência A/V, servidor de borda, aplicativo de grupo de resposta e atendedor automático de conferência, quando esses cenários estão habilitados.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas ativas</p></td>
<td><p>Número total de chamadas de voz de entrada/saída em andamento no momento.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas terminadas</p></td>
<td><p>Número total de chamadas de voz de entrada/saída já terminadas.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas recusadas</p></td>
<td><p>Número total de chamadas de voz de entrada recusadas.</p></td>
</tr>
<tr class="even">
<td><p>Tentativa de chamadas de entrada/saída</p></td>
<td><p>Número total de chamadas de voz de entrada/saída tentadas.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas de entrada/saída estabelecidas</p></td>
<td><p>Número total de chamadas de voz de entrada/saída estabelecidas.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas recebidas NNN</p></td>
<td><p>Número total de códigos de resposta nnn recebidos do servidor.</p></td>
</tr>
<tr class="odd">
<td><p>Taxa de aprovação de VoIP (%)</p></td>
<td><p>Total de chamadas estabelecidas/total de chamadas tentadas.</p></td>
</tr>
</tbody>
</table>


**Informações de chamada do serviço de grupo de resposta**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas ativas</p></td>
<td><p>Número total de chamadas ativas para o aplicativo grupo de resposta.</p></td>
</tr>
<tr class="even">
<td><p>Tentativas de chamadas</p></td>
<td><p>Número total de chamadas tentadas.</p></td>
</tr>
</tbody>
</table>


**Informações de chamada de mensagens instantâneas (IM)**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas ativas</p></td>
<td><p>Número total de chamadas de mensagens instantâneas de entrada/saída contínuas.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas terminadas</p></td>
<td><p>Número total de chamadas de mensagens instantâneas de entrada/saída já terminadas.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas recebidas NNN</p></td>
<td><p>Número total de códigos de resposta nnn recebidos do servidor.</p></td>
</tr>
<tr class="even">
<td><p>Mensagens IM recebidas/enviadas</p></td>
<td><p>Número total de mensagens recebidas ou enviadas para todas as sessões.</p></td>
</tr>
<tr class="odd">
<td><p>Tentativa de chamadas de entrada/saída</p></td>
<td><p>Número total de chamadas de mensagens instantâneas de entrada/saída tentadas.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas de entrada/saída estabelecidas</p></td>
<td><p>Número total de chamadas de mensagens instantâneas de entrada/saída estabelecidas.</p></td>
</tr>
</tbody>
</table>


**Informações de chamada de compartilhamento de aplicativo**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas ativas</p></td>
<td><p>Número total de chamadas de compartilhamento de aplicativo de entrada/saída em andamento.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas terminadas</p></td>
<td><p>Número total de chamadas de compartilhamento de aplicativo de entrada/saída já terminadas.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas recebidas NNN</p></td>
<td><p>Número total de códigos de resposta nnn recebidos do servidor.</p></td>
</tr>
<tr class="even">
<td><p>Tentativa de chamadas de entrada/saída</p></td>
<td><p>Número total de chamadas de compartilhamento de aplicativo de entrada/saída tentadas.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas de entrada/saída estabelecidas</p></td>
<td><p>Número total de chamadas de compartilhamento de aplicativo de entrada/saída estabelecidas.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Informações de chamada CAA**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas ativas</p></td>
<td><p>Número total de chamadas de rede telefônica pública comutada (PSTN) de entrada/saída em andamento no momento.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas terminadas</p></td>
<td><p>Número total de chamadas PSTN de entrada/saída já terminadas.</p></td>
</tr>
<tr class="odd">
<td><p>Tentativa de chamadas de entrada/saída</p></td>
<td><p>Número total de chamadas PSTN de entrada/saída tentadas.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas de entrada/saída estabelecidas</p></td>
<td><p>Número total de chamadas PSTN de entrada/saída estabelecidas.</p></td>
</tr>
</tbody>
</table>


**Informações de conferência**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Conferências de mensagens instantâneas ativas</p></td>
<td><p>Número total de conferências de mensagens instantâneas em andamento.</p></td>
</tr>
<tr class="even">
<td><p>Conferências ativas de áudio/vídeo</p></td>
<td><p>Número total de conferências de áudio/vídeo (A/V) em andamento.</p></td>
</tr>
<tr class="odd">
<td><p>Conferências de compartilhamento de aplicativos ativos</p></td>
<td><p>Número total de conferências de compartilhamento de aplicativos contínuos.</p></td>
</tr>
<tr class="even">
<td><p>Número de participantes</p></td>
<td><p>Número total de participantes conectados atualmente a conferências.</p></td>
</tr>
<tr class="odd">
<td><p>Falha no agendamento da conferência</p></td>
<td><p>Número total de falhas ao tentar agendar uma conferência.</p></td>
</tr>
<tr class="even">
<td><p>Falha de conferência de ingresso</p></td>
<td><p>Número total de falhas ao tentar se conectar a uma conferência.</p></td>
</tr>
</tbody>
</table>


**Contadores do cliente UCWA**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Contador de desempenho</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Número total de junções IMMCU com êxito</p></td>
<td><p>Número total de conferências de mensagens instantâneas Unidas.</p></td>
</tr>
<tr class="even">
<td><p>Número total de junções DMCU com êxito</p></td>
<td><p>Número total de conferências de A/V Unidas.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

