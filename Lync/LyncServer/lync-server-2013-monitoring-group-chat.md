---
title: 'Lync Server 2013: Monitoring Group Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf44bbaa00412de24af21c493fd05b88bd6259af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531928"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a>Monitorando o chat do grupo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-08-04_

É altamente recomendável executar o [instalador de atualização cumulativa](https://support.microsoft.com/kb/968802) mais recente do servidor disponível no centro de download da Microsoft para melhorar o desempenho.

Supondo que você esteja executando a atualização cumulativa mais recente, use a seguinte tabela de teste de estresse para métricas para entender se seus servidores de chat de grupo estão sendo executados na integridade ideal.

### <a name="test-environment-and-user-model"></a>Ambiente de teste e modelo de usuário

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Três servidores de chat de grupo em um pool de chat de grupo, cada um com 8 GB de memória e 8 processadores.</p></td>
</tr>
<tr class="even">
<td><p>Dois front-ends do Lync Server 2013 na Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60.000 usuários simultâneos em três servidores de chat de grupo.</p></td>
</tr>
<tr class="even">
<td><p>25.000 canais hospedados pelo pool de chat de grupo.</p></td>
</tr>
<tr class="odd">
<td><p>Tamanho do canal:</p>
<ul>
<li><p>Tamanho do canal pequeno: 30</p></li>
<li><p>Tamanho médio do canal: 150</p></li>
<li><p>Tamanho de canal grande: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Contagem de canal:</p>
<ul>
<li><p>Números pequenos de canais: 24.000</p></li>
<li><p>Número de canais médios de 800</p></li>
<li><p>Número grande de canais 24</p></li>
<li><p>Total de canais 24.824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Canais de convite:</p>
<ul>
<li><p>Metade dos canais eram convidados canais</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Número de canais que um usuário ingressa:</p>
<ul>
<li><p>Pequeno: 12</p></li>
<li><p>Médio: 2</p></li>
<li><p>Grande: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Taxa de junção:</p>
<ul>
<li><p>10 no total/segundo, 3,33/segundo por servidor</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Taxa de logout:</p>
<ul>
<li><p>10 no total/segundo, 3,33/segundo por servidor</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Taxa de chat:</p>
<ul>
<li><p>20 no total/segundo, 6.66/segundo por servidor</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Os seguintes números de contadores de desempenho provavelmente variam quando especificações de hardware ou perfis de usuário diferentes são usados.



</div>

### <a name="performance-counter-to-be-monitored"></a>Contador de desempenho a ser monitorado

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contador de Desempenho</th>
<th>Limites</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processo (ChannelService)- &gt; % tempo do processador</p></td>
<td><p>Mín: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

