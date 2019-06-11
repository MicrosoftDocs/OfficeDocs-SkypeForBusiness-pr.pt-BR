---
title: 'Lync Server 2013: requisitos de DNS para servidores de chat persistentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f52fde1ee1034f453fe62f2aa3aa44d04b389c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a>Requisitos de DNS para servidores de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-28_

Esta seção descreve os registros DNS (sistema de nomes de domínio) necessários para a implantação de servidores de chat persistentes.

<div>

## <a name="dns-records-for-persistent-chat-servers"></a>Registros DNS para servidores de chat persistentes

A tabela a seguir especifica requisitos de DNS para a implantação do servidor de chat persistente.

### <a name="dns-requirements-for-a-persistent-chat-server"></a>Requisitos de DNS para um servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cenário da implantação</th>
<th>Requisitos de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Um servidor de chat persistente</p></td>
<td><p>Um registro A interno que resolve o nome de domínio totalmente qualificado (FQDN) do servidor para seu endereço IP.</p></td>
</tr>
<tr class="even">
<td><p>Pool de chat persistente</p></td>
<td><p>Um registro interno que resolve o nome de domínio totalmente qualificado (FQDN) dos servidores para seu endereço IP.</p>
<p><strong>Exemplo</strong></p>
<p>PersistentChatServer01.contoso.com 10.10.10.1</p>
<p>PersistentChatServer02.contoso.com 10.10.10.2</p>
<p>Um registro interno que resolve o nome de domínio totalmente qualificado (FQDN) dos servidores para seu endereço IP.</p>
<p><strong>Exemplo</strong></p>
<p>PersistentChatPool.contoso.com 10.10.10.1</p>
<p>PersistentChatPool.contoso.com 10.10.10.2</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

