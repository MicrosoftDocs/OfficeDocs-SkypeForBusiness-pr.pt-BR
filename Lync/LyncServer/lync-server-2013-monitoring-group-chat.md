---
title: 'Lync Server 2013: monitorando o chat em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74897191cac7559237e961b7600a3ed478d11e58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Monitorar o chat em grupo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-08-04_

É altamente recomendável executar o [instalador de atualização cumulativa do servidor](http://support.microsoft.com/kb/968802) mais recente disponível no centro de download da Microsoft para melhorar o desempenho.

Pressupondo que você esteja executando a atualização cumulativa mais recente, use a seguinte tabela de teste de stress para métricas a fim de compreender se seus servidores de chat em grupo estão sendo executados na integridade ideal.

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
<td><p>Três servidores de chat em grupo em um pool de chat em grupo, cada um com 8 GB de memória e 8 processadores.</p></td>
</tr>
<tr class="even">
<td><p>Duas front-ends do Lync Server 2013 na Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60.000 usuários simultâneos em três servidores de chat em grupo.</p></td>
</tr>
<tr class="even">
<td><p>25.000 canais hospedados pelo pool de chat em grupo.</p></td>
</tr>
<tr class="odd">
<td><p>Tamanho do canal:</p>
<ul>
<li><p>Tamanho do canal pequeno: 30</p></li>
<li><p>Tamanho médio do canal: 150</p></li>
<li><p>Tamanho do canal grande: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Contagem de canais:</p>
<ul>
<li><p>Número pequeno de canais: 24.000</p></li>
<li><p>Número médio de canais médio 800</p></li>
<li><p>Número maior de canais 24</p></li>
<li><p>Total de canais 24.824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Convidar canais:</p>
<ul>
<li><p>Metade dos canais eram convidados canais</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Número de canais que um usuário ingressa:</p>
<ul>
<li><p>Pequeno: 12</p></li>
<li><p>Média: 2</p></li>
<li><p>Grande: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Taxa de junção:</p>
<ul>
<li><p>10 total/segundo, 3,33/segundo por servidor</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Taxa de logout:</p>
<ul>
<li><p>10 total/segundo, 3,33/segundo por servidor</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Tarifa de chat:</p>
<ul>
<li><p>20 totais/segundo, 6.66/segundo por servidor</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Os seguintes números de contador de desempenho provavelmente variam quando são usadas diferentes especificações de hardware ou perfis de usuário.



</div>

### <a name="performance-counter-to-be-monitored"></a>Contador de desempenho a ser monitorado

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contador de desempenho</th>
<th>Limites</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processo (ChannelService)-&gt;% tempo do processador</p></td>
<td><p>Mín: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

