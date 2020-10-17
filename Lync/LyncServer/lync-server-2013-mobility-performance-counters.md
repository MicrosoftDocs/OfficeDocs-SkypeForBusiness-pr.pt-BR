---
title: 'Lync Server 2013: contadores de desempenho de mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37e36b4492814043317fcafb2612a28c9f4d7b91
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513598"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a>Contadores de desempenho de mobilidade no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

As tabelas a seguir listam os nomes e as descrições dos contadores de desempenho que você pode usar para monitorar servidores que executam a UCWA (Unified Communications Web API) e o serviço de mobilidade do Lync Server 2013 MCX.

O nome da categoria para os contadores na tabela UCWA é **ls: Web – UCWA**.

O nome da categoria para os contadores na tabela de serviço de mobilidade do MCX é **ls: Web-Mobile Communication Service**.

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
<td><p>Contagem de modalidades de compartilhamento de aplicativos ativos</p></td>
<td><p>O número atual da modalidade de compartilhamento de aplicativos</p></td>
</tr>
<tr class="odd">
<td><p>Contagem de modalidade de áudio ativa</p></td>
<td><p>O número atual de modalidade de áudio</p></td>
</tr>
<tr class="even">
<td><p>Contagem de modalidade de colaboração de dados ativa</p></td>
<td><p>O número atual de modalidade de colaboração de dados</p></td>
</tr>
<tr class="odd">
<td><p>Latência de obtenção de foto do Active Directory (MS)</p></td>
<td><p>Este contador mostra o tempo médio (em milissegundos) para recuperar uma foto do Active Directory</p></td>
</tr>
<tr class="even">
<td><p>Contagem de modalidades de mensagens ativas</p></td>
<td><p>O número atual de modalidade de mensagens</p></td>
</tr>
<tr class="odd">
<td><p>Contagem de modalidades de vídeo panorâmico ativa</p></td>
<td><p>O número atual da modalidade de vídeo panorâmico</p></td>
</tr>
<tr class="even">
<td><p>Contagem de obtenção pendente ativa</p></td>
<td><p>O número de ativos pendentes no momento; conexões de longa duração com o servidor</p></td>
</tr>
<tr class="odd">
<td><p>Contagem de sessão ativa</p></td>
<td><p>O número atual de pontos de extremidade registrados no UCWA por aplicativo e por total</p></td>
</tr>
<tr class="even">
<td><p>Contagem de instâncias de usuário ativas</p></td>
<td><p>O número atual de instâncias de usuário</p></td>
</tr>
<tr class="odd">
<td><p>Instâncias de usuários ativos sem aplicativo</p></td>
<td><p>O número atual de instâncias de usuário sem aplicativo</p></td>
</tr>
<tr class="even">
<td><p>Contagem de modalidade de vídeo ativa</p></td>
<td><p>O número atual da modalidade de vídeo</p></td>
</tr>
<tr class="odd">
<td><p>Solicitações de criação de aplicativo recebidas/segundo</p></td>
<td><p>A taxa de solicitações de criação de aplicativo recebidas por segundo</p></td>
</tr>
<tr class="even">
<td><p>Como falhas de junção de MCU</p></td>
<td><p>O número de falhas de ingresso no MCU</p></td>
</tr>
<tr class="odd">
<td><p>Falhas de ingresso do AV MCU</p></td>
<td><p>O número de falhas de ingresso no AV MCU</p></td>
</tr>
<tr class="even">
<td><p>Tempo médio de inicialização do aplicativo (MS)</p></td>
<td><p>O tempo médio de inicialização do aplicativo em milissegundos</p></td>
</tr>
<tr class="odd">
<td><p>Tempo de vida médio da sessão (MS)</p></td>
<td><p>O tempo médio de vida de uma sessão em milissegundos</p></td>
</tr>
<tr class="even">
<td><p>Falhas de ingresso no MCU de dados</p></td>
<td><p>O número de falhas de ingresso no MCU de dados</p></td>
</tr>
<tr class="odd">
<td><p>Latência de pesquisa de contato do Exchange (MS)</p></td>
<td><p>Este contador mostra o tempo médio (em milissegundos) para pesquisar o contato no Exchange</p></td>
</tr>
<tr class="even">
<td><p>Latência de obtenção de foto HD do Exchange (MS)</p></td>
<td><p>Este contador mostra o tempo médio (em milissegundos) para recuperar uma foto do Exchange</p></td>
</tr>
<tr class="odd">
<td><p>Respostas HTTP 4xx/segundo</p></td>
<td><p>A taxa de respostas por segundo com o código HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Respostas de HTTP 5xx/segundo</p></td>
<td><p>A taxa de respostas por segundo com o código HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Falhas de junção de IM MCU</p></td>
<td><p>O número de falhas de entrada de mensagens instantâneas de MCU</p></td>
</tr>
<tr class="even">
<td><p>Número de falhas ao baixar fotos do Active Directory</p></td>
<td><p>O número total de falhas para recuperar fotos do Active Directory</p></td>
</tr>
<tr class="odd">
<td><p>Número de falhas de pesquisa de contato</p></td>
<td><p>O número total de falhas ao pesquisar contatos no Exchange</p></td>
</tr>
<tr class="even">
<td><p>Número de falhas de desserialização</p></td>
<td><p>O número total de falhas de desserialização</p></td>
</tr>
<tr class="odd">
<td><p>Número de falhas de obtenção de foto de HD</p></td>
<td><p>O número total de falhas para recuperar fotos de HD do Exchange</p></td>
</tr>
<tr class="even">
<td><p>Sobre as assinaturas máximas por aplicativo</p></td>
<td><p>O número de solicitações de assinatura no máximo permitido por aplicativo</p></td>
</tr>
<tr class="odd">
<td><p>Sobre o máximo de inscrições por lote</p></td>
<td><p>O número de solicitações de assinatura no máximo permitido por lote</p></td>
</tr>
<tr class="even">
<td><p>Falhas de assinatura de presença</p></td>
<td><p>O número de falhas ao assinar a presença</p></td>
</tr>
<tr class="odd">
<td><p>Registrando falhas de pontos de extremidade</p></td>
<td><p>O número de falhas para registrar pontos de extremidade</p></td>
</tr>
<tr class="even">
<td><p>Solicitações recebidas/segundo</p></td>
<td><p>A taxa de solicitações recebidas por segundo</p></td>
</tr>
<tr class="odd">
<td><p>Solicitações bem-sucedidas/segundo</p></td>
<td><p>A taxa de solicitações bem-sucedidas por segundo (códigos de resposta HTTP 2xx/3xx)</p></td>
</tr>
<tr class="even">
<td><p>Solicitações de criação de aplicativo bem-sucedidas/segundo</p></td>
<td><p>A taxa de solicitações de criação de aplicativo bem-sucedidas por segundo</p></td>
</tr>
<tr class="odd">
<td><p>Contagem de obtenção pendente com tempo limite esgotado</p></td>
<td><p>O número de pendências que expiraram</p></td>
</tr>
<tr class="even">
<td><p>Total de solicitações de criação de aplicativos recebidas</p></td>
<td><p>O número total de solicitações de criação de aplicativos recebidas desde que o serviço foi iniciado</p></td>
</tr>
<tr class="odd">
<td><p>Total de respostas de HTTP 4xx</p></td>
<td><p>O número total de respostas HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Total de respostas de HTTP 5xx</p></td>
<td><p>O número total de respostas HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Total de solicitações recebidas no canal de comando</p></td>
<td><p>O número total de solicitações recebidas no canal do comando</p></td>
</tr>
<tr class="even">
<td><p>Total de solicitações bem-sucedidas</p></td>
<td><p>O número total de solicitações que tiveram êxito</p></td>
</tr>
<tr class="odd">
<td><p>Total de sessões iniciadas</p></td>
<td><p>O número total de sessões que foram iniciadas desde o início do serviço</p></td>
</tr>
<tr class="even">
<td><p>Total de sessões encerradas devido ao tempo limite de ociosidade</p></td>
<td><p>O número total de sessões encerradas devido ao tempo limite de usuário ocioso</p></td>
</tr>
<tr class="odd">
<td><p>Total de aplicativos limitado</p></td>
<td><p>O número de aplicativos regulados</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Contadores de desempenho para o serviço de mobilidade do MCX

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
<td><p>Tempo média de vida de uma sessão em milissegundos</p></td>
<td><p>O tempo médio de vida de uma sessão em milissegundos</p></td>
</tr>
<tr class="even">
<td><p>Assinaturas atuais de notificação por push</p></td>
<td><p>O número atual de assinaturas de notificação por push. Esse número, em conjunto com a contagem de sessão ativa no momento, representa o subconjunto de sessões ativas no momento que são registradas para dispositivos Windows Mobile ou iPhone.</p></td>
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
<td><p>Número atual de pontos de extremidade registrados no Serviço de Mobilidade</p></td>
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
<td><p>O número total de solicitações feitas ao Serviço de Mobilidade que tiveram êxito</p></td>
</tr>
<tr class="even">
<td><p>Contagem total de sessões iniciadas</p></td>
<td><p>O número total de sessões iniciadas desde a inicialização do Serviço de Mobilidade</p></td>
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

