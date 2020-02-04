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
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Exceções de IPsec no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-27_

Para redes corporativas onde a segurança do protocolo Internet (IPsec) (consulte IETF RFC 4301-4309) foi implantada, o IPsec deve ser desabilitado no intervalo de portas usado para a entrega de vídeo de áudio, vídeo e panorama. Essa recomendação existe porque é necessário evitar atrasos na alocação das portas de mídia por causa da negociação IPsec.

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
<td><p>Qualquer um</p></td>
<td><p>Interno do Servidor de Borda A/V</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Entrada externa do Servidor de Borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>Externo do Servidor de Borda A/V</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Saída interna do Servidor de Borda A/V</p></td>
<td><p>Interno do Servidor de Borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>UDP &amp; TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Saída externa do Servidor de Borda A/V</p></td>
<td><p>Externo do Servidor de Borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Entrada do Servidor de Mediação</p></td>
<td><p>Qualquer um</p></td>
<td><p>Mediação</p>
<p>Servidor(es)</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Saída do Servidor de Mediação</p></td>
<td><p>Mediação</p>
<p>Servidor(es)</p></td>
<td><p>Qualquer um</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Entrada do Atendedor de Conferência</p></td>
<td><p>Qualquer um</p></td>
<td><p>Servidor Front-End executando o Atendedor de Conferência</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Saída do Atendedor de Conferência</p></td>
<td><p>Servidor Front-End executando o Atendedor de Conferência</p></td>
<td><p>Qualquer um</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Entrada de Conferência A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>Servidores Front-End</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Saída de Conferência A/V</p></td>
<td><p>Servidores Front-End</p></td>
<td><p>Qualquer um</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Entrada do Exchange</p></td>
<td><p>Qualquer um</p></td>
<td><p>Unificação de Mensagens do Exchange</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Entrada dos Servidores de Compartilhamento de Aplicativo</p></td>
<td><p>Qualquer um</p></td>
<td><p>Servidores de Compartilhamento de Aplicativos</p></td>
<td><p>TCP</p></td>
<td><p>Qualquer um</p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Saída do Servidor de Compartilhamento de Aplicativos</p></td>
<td><p>Servidores de Compartilhamento de Aplicativos</p></td>
<td><p>Qualquer um</p></td>
<td><p>TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="even">
<td><p>Saída do Exchange</p></td>
<td><p>Unificação de Mensagens do Exchange</p></td>
<td><p>Qualquer um</p></td>
<td><p>UDP e TCP</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>Qualquer um </p></td>
<td><p>Qualquer um</p></td>
<td><p>UDP</p></td>
<td><p>Intervalo especificado de portas de mídia</p></td>
<td><p>Qualquer um</p></td>
<td><p>Não autenticar</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

