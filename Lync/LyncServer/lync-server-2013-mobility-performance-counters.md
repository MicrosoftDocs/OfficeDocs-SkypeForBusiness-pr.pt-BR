---
title: 'Lync Server 2013: contadores de desempenho da mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c0759ccd6a9203dfac87f0ec55f555d49d19ccc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Contadores de desempenho de mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

As tabelas a seguir listam os nomes e descrições dos contadores de desempenho que você pode usar para monitorar servidores que executam a API da Web de comunicação unificada (UCWA) e o serviço de mobilidade do MCX do Lync Server 2013.

O nome da categoria para os contadores na tabela UCWA é **LS:WEB – UCWA**.

O nome da categoria para os contadores na tabela do Serviço de Mobilidade Mcx é **LS:WEB – Mobile Communication Service**.

<div>

## <a name="performance-counters-for-ucwa"></a>Contadores de desempenho para UCWA


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contador</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Contagem de aplicativos ativos</p></td>
<td><p>O número atual de aplicativos</p></td>
</tr>
<tr class="even">
<td><p>Contagem da modalidade de compartilhamento do aplicativo ativa</p></td>
<td><p>O número atual da modalidade de compartilhamento do aplicativo</p></td>
</tr>
<tr class="odd">
<td><p>Contagem da modalidade de áudio ativa</p></td>
<td><p>O número atual da modalidade de áudio</p></td>
</tr>
<tr class="even">
<td><p>Contagem da modalidade de colaboração de dados ativa</p></td>
<td><p>O número atual da modalidade de colaboração de dados</p></td>
</tr>
<tr class="odd">
<td><p>Latência para baixar fotos do diretório ativo (ms)</p></td>
<td><p>Esse contador mostra o tempo médio (em milissegundos) para obter uma foto do diretório ativo</p></td>
</tr>
<tr class="even">
<td><p>Contagem da modalidade de tráfego de mensagens ativa</p></td>
<td><p>O número atual da modalidade de tráfego de mensagens</p></td>
</tr>
<tr class="odd">
<td><p>Contagem da modalidade de vídeo panorâmico ativa</p></td>
<td><p>O número atual da modalidade de vídeo panorâmico</p></td>
</tr>
<tr class="even">
<td><p>Contagem de downloads pendentes ativos</p></td>
<td><p>O número de downloads pendentes atualmente ativos; conexões de longa duração com o servidor</p></td>
</tr>
<tr class="odd">
<td><p>Contagem de sessões ativas</p></td>
<td><p>O número atual de pontos de extremidade registrados no UCWA por aplicativo e no total</p></td>
</tr>
<tr class="even">
<td><p>Contagem de instâncias de usuário ativas</p></td>
<td><p>O número atual de instâncias de usuário ativas</p></td>
</tr>
<tr class="odd">
<td><p>Instâncias de usuário ativas sem aplicativo</p></td>
<td><p>O número atual de instâncias de usuário sem aplicativo</p></td>
</tr>
<tr class="even">
<td><p>Contagem da modalidade de vídeo ativa</p></td>
<td><p>O número atual da modalidade de vídeo</p></td>
</tr>
<tr class="odd">
<td><p>Solicitações de criação de aplicativo recebidas por segundo</p></td>
<td><p>A taxa de solicitações de criação de aplicativo recebidas por segundo</p></td>
</tr>
<tr class="even">
<td><p>Falhas de entrada em MCU de AS</p></td>
<td><p>O número de falhas de entrada em MCU de AS</p></td>
</tr>
<tr class="odd">
<td><p>Falhas de entrada em MCU de AV</p></td>
<td><p>O número de falhas de entrada em MCU de AV</p></td>
</tr>
<tr class="even">
<td><p>Tempo médio para inicialização do aplicativo (ms)</p></td>
<td><p>O tempo médio para inicialização do aplicativo em milissegundos</p></td>
</tr>
<tr class="odd">
<td><p>Tempo médio de duração por sessão (ms)</p></td>
<td><p>O tempo médio de vida de uma sessão em milissegundos</p></td>
</tr>
<tr class="even">
<td><p>Falhas de entrada em MCU de dados</p></td>
<td><p>O número de falhas de entrada em MCU de dados</p></td>
</tr>
<tr class="odd">
<td><p>Latência para pesquisa de contatos no Exchange (ms)</p></td>
<td><p>Esse contador mostra o tempo médio (em milissegundos) para se pesquisar contatos no Exchange</p></td>
</tr>
<tr class="even">
<td><p>Latência para baixar fotos em HD no Exchange (ms)</p></td>
<td><p>Esse contador mostra o tempo médio (em milissegundos) para se baixar uma foto no Exchange</p></td>
</tr>
<tr class="odd">
<td><p>Respostas/segundo do HTTP 4xx</p></td>
<td><p>A taxa de respostas por segundo com o código HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Respostas/segundo do HTTP 5xx</p></td>
<td><p>A taxa de respostas por segundo com o código HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Falhas de entrada em MCU de IM</p></td>
<td><p>O número de falhas de entrada em MCU de IM</p></td>
</tr>
<tr class="even">
<td><p>Número de falhas ao baixar fotos do Active Directory</p></td>
<td><p>O número total de falhas ao baixar fotos do Active Directory</p></td>
</tr>
<tr class="odd">
<td><p>Número de falhas ao pesquisar contatos</p></td>
<td><p>O número total de falhas ao pesquisar contatos no Exchange</p></td>
</tr>
<tr class="even">
<td><p>Número de falhas de desserialização</p></td>
<td><p>O número total de falhas de desserialização</p></td>
</tr>
<tr class="odd">
<td><p>Número de falhas de obtenção de foto HD</p></td>
<td><p>O número total de falhas ao baixar fotos em HD do Exchange</p></td>
</tr>
<tr class="even">
<td><p>Excesso de inscrições por aplicativo</p></td>
<td><p>O número de solicitações de inscrição além do máximo permitido por aplicativo</p></td>
</tr>
<tr class="odd">
<td><p>Excesso de inscrições por lote</p></td>
<td><p>O número de solicitações de inscrição além do máximo permitido por lote</p></td>
</tr>
<tr class="even">
<td><p>Falhas de inscrição de presença</p></td>
<td><p>O número de falhas ao realizar inscrições de presença</p></td>
</tr>
<tr class="odd">
<td><p>Falhas ao se registrar pontos de extremidade</p></td>
<td><p>O número de falhas ao se registrar pontos de extremidade</p></td>
</tr>
<tr class="even">
<td><p>Solicitações recebidas/segundo</p></td>
<td><p>A taxa de solicitações recebidas por segundo</p></td>
</tr>
<tr class="odd">
<td><p>Solicitações bem-sucedidas/segundo</p></td>
<td><p>A taxa por segundo de solicitações bem-sucedidas (códigos de resposta HTTP 2xx/3xx)</p></td>
</tr>
<tr class="even">
<td><p>Solicitações de criação de aplicativo bem-sucedidas/segundo</p></td>
<td><p>A taxa de solicitações de criação de aplicativo bem-sucedidas por segundo</p></td>
</tr>
<tr class="odd">
<td><p>Contagem de downloads pendentes com tempo limite ultrapassado</p></td>
<td><p>O número de downloads pendentes que ultrapassaram o tempo limite</p></td>
</tr>
<tr class="even">
<td><p>Total de solicitações de criação de aplicativo recebidas</p></td>
<td><p>O número total de solicitações de criação de aplicativo recebidas desde que o serviço foi iniciado</p></td>
</tr>
<tr class="odd">
<td><p>Total de respostas de HTTP 4xx</p></td>
<td><p>O número total de respostas de HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Total de respostas de HTTP 5xx</p></td>
<td><p>O número total de respostas de HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Total de solicitações recebidas no Canal de Comando</p></td>
<td><p>O número total de solicitações recebidas no canal do comando</p></td>
</tr>
<tr class="even">
<td><p>Total de solicitações bem-sucedidas</p></td>
<td><p>O número total de solicitações que tiveram êxito</p></td>
</tr>
<tr class="odd">
<td><p>Total de sessões iniciadas</p></td>
<td><p>O número total de sessões iniciadas desde a inicialização do serviço</p></td>
</tr>
<tr class="even">
<td><p>Total de sessões encerradas devido ao tempo limite de ociosidade</p></td>
<td><p>O número total de sessões encerradas devido ao tempo limite de usuário ocioso</p></td>
</tr>
<tr class="odd">
<td><p>Total de aplicativos limitados</p></td>
<td><p>O número de aplicativos limitados</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Contadores de desempenho para Mobility Service (Mcx)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contador</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tempo médio de vida de uma sessão em milissegundos</p></td>
<td><p>O tempo médio de vida de uma sessão em milissegundos</p></td>
</tr>
<tr class="even">
<td><p>Assinaturas atuais de notificação por push</p></td>
<td><p>O número atual de assinaturas de notificação por push. Esse número, em conjunto com a Contagem de sessões atualmente ativas, representam o subconjunto de sessões atualmente ativas registradas para dispositivos Windows Mobile ou iPhone.</p></td>
</tr>
<tr class="odd">
<td><p>Contagem de polls de tempo limite de rede ativos no momento</p></td>
<td><p>O número de pools de rede que ultrapassaram o tempo limite</p></td>
</tr>
<tr class="even">
<td><p>Contagem de pools ativos no momento</p></td>
<td><p>O número de polls atualmente ativos (conexões de longa duração com o servidor)</p></td>
</tr>
<tr class="odd">
<td><p>Contagem de sessão ativa no momento</p></td>
<td><p>Número atual de pontos de extremidade registrados no Mobility Service</p></td>
</tr>
<tr class="even">
<td><p>Contagem de sessão ativa no momento com assinaturas de presença ativa</p></td>
<td><p>O número de sessões ativas no momento com assinaturas de presença ativa</p></td>
</tr>
<tr class="odd">
<td><p>Solicitações de notificação por push sem êxito/segundo</p></td>
<td><p>A taxa de notificações por push sem êxito por segundo</p></td>
</tr>
<tr class="even">
<td><p>Solicitações de notificação por push bem-sucedidas/segundo</p></td>
<td><p>A taxa de notificações por push bem-sucedidas por segundo</p></td>
</tr>
<tr class="odd">
<td><p>Solicitações de notificação por push limitadas/segundo</p></td>
<td><p>A taxa de notificações por push limitadas por segundo</p></td>
</tr>
<tr class="even">
<td><p>Solicitações de notificação por push/segundo</p></td>
<td><p>A taxa de notificações por push enviadas por segundo</p></td>
</tr>
<tr class="odd">
<td><p>Solicitações sem êxito/segundo</p></td>
<td><p>A taxa de solicitações sem êxito por segundo</p></td>
</tr>
<tr class="even">
<td><p>Solicitações recebidas/segundo</p></td>
<td><p>A taxa de solicitações recebidas por segundo</p></td>
</tr>
<tr class="odd">
<td><p>Solicitações rejeitadas/segundo</p></td>
<td><p>A taxa de solicitações receitadas por segundo</p></td>
</tr>
<tr class="even">
<td><p>Solicitações bem-sucedidas/segundo</p></td>
<td><p>A taxa de solicitações bem-sucedidas por segundo</p></td>
</tr>
<tr class="odd">
<td><p>Solicitações de início de sessão bem-sucedidas/segundo</p></td>
<td><p>A taxa de solicitações de Obter localização bem-sucedidas por segundo. As solicitações de início de uma sessão consomem grande parte do CPU no servidor. A carga de pico suportada é de 12/segundo. A sustentabilidade depende de outras cargas no servidor. Iniciar uma sessão normalmente significa um logon de um usuário que ficou desconectado durante um período extenso de tempo.</p></td>
</tr>
<tr class="even">
<td><p>Total de chamadas de voz de entrada recusadas</p></td>
<td><p>O número total de chamadas de voz de entrada recusadas</p></td>
</tr>
<tr class="odd">
<td><p>Total de chamadas de voz de entrada sem êxito</p></td>
<td><p>O número total de chamadas de voz de entrada que não tiveram êxito</p></td>
</tr>
<tr class="even">
<td><p>Total de chamadas de voz de saída sem êxito</p></td>
<td><p>O número total de chamadas de voz de saída que não tiveram êxito</p></td>
</tr>
<tr class="odd">
<td><p>Número total de sessões encerradas pelo usuário</p></td>
<td><p>O número total de sessões encerradas por usuários</p></td>
</tr>
<tr class="even">
<td><p>Total de solicitações de notificação por push</p></td>
<td><p>O número total de solicitações de notificação por push</p></td>
</tr>
<tr class="odd">
<td><p>Total de solicitações de notificação por push em êxito</p></td>
<td><p>O número total de solicitações de notificação por push que não tiveram êxito</p></td>
</tr>
<tr class="even">
<td><p>Total de solicitações de notificação por push bem-sucedidas</p></td>
<td><p>O número total de solicitações de notificação por push bem-sucedidas</p></td>
</tr>
<tr class="odd">
<td><p>Total de solicitações de notificação por push limitadas</p></td>
<td><p>O número total de solicitações de notificação por push limitadas</p></td>
</tr>
<tr class="even">
<td><p>Total de solicitações sem êxito</p></td>
<td><p>O número total de solicitações que não tiveram êxito</p></td>
</tr>
<tr class="odd">
<td><p>Total de solicitações recebidas no Canal de Comando</p></td>
<td><p>O número total de solicitações recebidas no canal do comando</p></td>
</tr>
<tr class="even">
<td><p>Total de solicitações rejeitadas</p></td>
<td><p>O número total de solicitações rejeitadas</p></td>
</tr>
<tr class="odd">
<td><p>Total de solicitações bem-sucedidas</p></td>
<td><p>O número total de solicitações feitas ao Mobility Service que tiveram êxito</p></td>
</tr>
<tr class="even">
<td><p>Contagem total de sessões iniciadas</p></td>
<td><p>O número total de sessões iniciadas desde a inicialização do Mobility Service</p></td>
</tr>
<tr class="odd">
<td><p>Total de sessões encerradas devido ao tempo limite de usuário ocioso</p></td>
<td><p>O número total de sessões encerradas devido ao tempo limite de usuário ocioso</p></td>
</tr>
<tr class="even">
<td><p>Total de chamadas de voz de entrada bem-sucedidas</p></td>
<td><p>O número total de chamadas de voz de entrada que tiveram êxito</p></td>
</tr>
<tr class="odd">
<td><p>Total de chamadas de voz de saída bem-sucedidas</p></td>
<td><p>O número total de chamadas de voz de saída que tiveram êxito</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

