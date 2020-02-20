---
title: Exceções IPsec do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Exceções de IPsec no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-27_

Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o protocolo IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorama. A recomendação vem da necessidade de evitar qualquer atraso na alocação das portas de mídia por causa da negociação IPsec.

A tabela a seguir explica as configurações de exceções recomendadas do IPsec.

### <a name="recommended-ipsec-exceptions"></a>Exceções recomendadas do IPsec

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome da regra</th>
<th>IP de origem</th>
<th>IP de destino</th>
<th>Protocolo</th>
<th>Porta de origem</th>
<th>Porta de destino</th>
<th>Requisito de autenticação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Entrada interna do Servidor de Borda A/V</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Interno do Servidor de Borda A/V</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Entrada externa do Servidor de Borda A/V</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Externo do Servidor de Borda A/V</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Saída interna do Servidor de Borda A/V</p></td>
<td><p>Interno do Servidor de Borda A/V</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>TCP &amp; UDP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Saída externa do Servidor de Borda A/V</p></td>
<td><p>Externo do Servidor de Borda A/V</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Entrada do Servidor de Mediação</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Mediação</p>
<p>Servidor (es)</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Saída do Servidor de Mediação</p></td>
<td><p>Mediação</p>
<p>Servidor (es)</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Entrada do Atendedor de Conferência</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Servidor Front End executando o Atendedor de Conferência</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Saída do Atendedor de Conferência</p></td>
<td><p>Servidor Front End executando o Atendedor de Conferência</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Entrada de Conferência A/V</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Servidores Front-End</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Saída de Conferência A/V</p></td>
<td><p>Servidores Front-End</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Entrada do Exchange</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Unificação de Mensagens do Exchange</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Entrada dos Servidores de Compartilhamento de Aplicativo</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Servidores de Compartilhamento de Aplicativos</p></td>
<td><p>TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Saída do Servidor de Compartilhamento de Aplicativos.</p></td>
<td><p>Servidores de Compartilhamento de Aplicativos</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Saída do Exchange</p></td>
<td><p>Unificação de Mensagens do Exchange</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>VIA</p></td>
<td><p>Intervalo especificado de portas de mídia</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não autenticar</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

