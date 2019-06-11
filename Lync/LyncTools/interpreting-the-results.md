---
title: Interpretação dos resultados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a3dc473765a67db2e09f5a56db14b1ea8a41a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>Interpretação dos resultados

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-24_

A ferramenta de stress e desempenho do Lync Server 2013 (LyncPerfTool. exe) tem muitos contadores que você pode usar para compreender o que o cliente está fazendo e se está encontrando problemas.

<div>

## <a name="client-counters"></a>Contadores de cliente

Cada instância do LyncPerfTool. exe que está sendo executada tem uma instância separada dos contadores. Cada instância é nomeada pela ID do processo.

Se os clientes estiverem sobrecarregados, podem ocorrer problemas. Para evitar esses problemas, faça o seguinte:

1.  Monitore a CPU e o uso da memória nos computadores cliente. Se a CPU estiver consistentemente acima de 90%, reduza o número de usuários.

2.  Se o espaço da memória for alto, você poderá ter problemas se o arquivo da página não for grande o suficiente. Verifique se a carga comprometida não está atingindo o limite do computador. Se você estiver executando limites de memória, considere aumentar o tamanho do arquivo da página ou reduzir o número de usuários

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
<td><p>Número de pontos de extremidade conectados ao servidor no momento.</p></td>
</tr>
<tr class="odd">
<td><p>Logons com falha</p></td>
<td><p>Número total de falhas de entrada de ponto de extremidade.</p></td>
</tr>
<tr class="even">
<td><p>Tentativas de logon</p></td>
<td><p>Número total de tentativas de entrada no ponto de extremidade.</p></td>
</tr>
<tr class="odd">
<td><p>Pontos de extremidade desconectados</p></td>
<td><p>Número total de pontos de extremidade desconectados.</p></td>
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
<td><p>Chamadas de presença</p></td>
<td><p>Número total de tentativas de alteração de presença. Para diferentes tipos de alterações de presença, consulte o contador de desempenho de chamadas de presença (tipo de presença).</p></td>
</tr>
<tr class="even">
<td><p>Respostas de NNN para setpresence</p></td>
<td><p>Número total de códigos de resposta de nnn recebidos do servidor.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas de getpresence</p></td>
<td><p>Número total de tentativas de obter solicitação de presença.</p></td>
</tr>
<tr class="even">
<td><p>Respostas NNN para getpresence</p></td>
<td><p>Número total de códigos de resposta de nnn recebidos do servidor.</p></td>
</tr>
</tbody>
</table>


**Informações do serviço de catálogo de endereços**

Esta categoria inclui contadores usados para monitorar downloads de arquivos do serviço de catálogo de endereços (ABS) e catálogo de endereços da Web consulta de serviço.


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
<td><p>Tentativas de download de arquivo completo/Delta da ABS</p></td>
<td><p>Número total de solicitações de download de arquivos completas ou Delta tentadas.</p></td>
</tr>
<tr class="even">
<td><p>Downloads de arquivo completo/Delta do ABS bem-sucedido</p></td>
<td><p>Número total de solicitações de download de arquivos completas ou Delta tentadas.</p></td>
</tr>
<tr class="odd">
<td><p>Contadores relacionados ao serviço de consulta na Web do catálogo de endereços</p></td>
<td><p>Contadores relacionados ao download de arquivos do catálogo de endereços.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas de WS WS tentadas</p></td>
<td><p>Número total de tentativas de solicitações de serviço de consulta à Web do catálogo de endereços.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas do WS para ABS bem-sucedidas</p></td>
<td><p>Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta bem-sucedido.</p></td>
</tr>
<tr class="even">
<td><p>Falha nas chamadas ABS WS</p></td>
<td><p>Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta de erro.</p></td>
</tr>
</tbody>
</table>


**Informações de lista de distribuição (DL)**


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
<td><p>Chamadas tentadas</p></td>
<td><p>Número total de solicitações de serviço Web de expansão da lista de distribuição (DLX) tentadas.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas com êxito</p></td>
<td><p>Número total de solicitações de serviço Web DLX que retornaram um código de resposta bem-sucedido.</p></td>
</tr>
<tr class="odd">
<td><p>Falha nas chamadas</p></td>
<td><p>Número total de solicitações de serviço Web DLX que retornaram um código de resposta de erro.</p></td>
</tr>
</tbody>
</table>


**Informações básicas de VoIP**

Os contadores de desempenho listados abaixo numeram os números de todas as chamadas de voz sobre IP (VoIP), incluindo chamadas para servidor de mediação, servidor de conferência A/V, servidor de borda, aplicativo de grupo de resposta e atendedor automático de conferência, quando esses cenários são habilitados.


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
<td><p>Número total de chamadas de voz recebidas recusadas.</p></td>
</tr>
<tr class="even">
<td><p>Tentativa de fazer chamadas de entrada/saída</p></td>
<td><p>Número total de chamadas de voz de entrada/saída tentadas.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas de entrada/saída estabelecidas</p></td>
<td><p>Número total de chamadas de voz de entrada/saída estabelecidas.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas recebidas NNN</p></td>
<td><p>Número total de códigos de resposta de nnn recebidos do servidor.</p></td>
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
<td><p>Número total de chamadas ativas para o aplicativo de grupo de resposta.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas tentadas</p></td>
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
<td><p>Número total de chamadas de entrada/saída de mensagens instantâneas já terminadas.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas recebidas NNN</p></td>
<td><p>Número total de códigos de resposta de nnn recebidos do servidor.</p></td>
</tr>
<tr class="even">
<td><p>Mensagens INSTANTÂNEAs recebidas/enviadas</p></td>
<td><p>Número total de mensagens recebidas ou enviadas para todas as sessões.</p></td>
</tr>
<tr class="odd">
<td><p>Tentativa de fazer chamadas de entrada/saída</p></td>
<td><p>Número total de tentativas de entrada/saída de mensagens instantâneas feitas.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas de entrada/saída estabelecidas</p></td>
<td><p>Número total de chamadas de entrada/saída de mensagens instantâneas estabelecidas.</p></td>
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
<td><p>Número total de chamadas de compartilhamento de aplicativo de entrada/saída contínuas.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas terminadas</p></td>
<td><p>Número total de chamadas de compartilhamento de aplicativo de entrada/saída já terminadas.</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas recebidas NNN</p></td>
<td><p>Número total de códigos de resposta de nnn recebidos do servidor.</p></td>
</tr>
<tr class="even">
<td><p>Tentativa de fazer chamadas de entrada/saída</p></td>
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


**Informações de chamada do CAA**


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
<td><p>Número total de chamadas em PSTN (rede telefônica pública comutada) de entrada/saída em andamento no momento.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas terminadas</p></td>
<td><p>Número total de chamadas PSTN de entrada/saída já terminadas.</p></td>
</tr>
<tr class="odd">
<td><p>Tentativa de fazer chamadas de entrada/saída</p></td>
<td><p>Número total de chamadas de entrada PSTN de entrada/saída tentadas.</p></td>
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
<td><p>Conferências de áudio/vídeo ativas</p></td>
<td><p>Número total de conferências contínuas de áudio/vídeo (A/V).</p></td>
</tr>
<tr class="odd">
<td><p>Conferências de compartilhamento de aplicativos ativos</p></td>
<td><p>Número total de conferências de compartilhamento de aplicativos contínuas.</p></td>
</tr>
<tr class="even">
<td><p>Número de participantes</p></td>
<td><p>Número total de participantes atualmente conectados a conferências.</p></td>
</tr>
<tr class="odd">
<td><p>Falha no cronograma da conferência</p></td>
<td><p>Número total de falhas ao tentar agendar uma conferência.</p></td>
</tr>
<tr class="even">
<td><p>Ingressar na falha na conferência</p></td>
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
<td><p>Número total de junções de IMMCU bem-sucedida</p></td>
<td><p>Número total de conferências de mensagens instantâneas Unidas.</p></td>
</tr>
<tr class="even">
<td><p>Número total de junções de DMCU bem-sucedida</p></td>
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

