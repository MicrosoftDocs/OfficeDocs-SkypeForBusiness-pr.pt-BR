---
title: 'Lync Server 2013: Resumo de porta - Diretor único'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5568a37093f161caef6717df5d3a3f09be6f18c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a>Resumo de porta - Diretor único no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

Os requisitos de porta do firewall para um único diretor consistem em portas que são usadas para estabelecer comunicação com o diretor da interface interna ou da rede de face interna do proxy reverso. O Microsoft Lync Server 2013 por padrão espera que as portas HTTP/TCP 8080 e HTTPS/TCP 4443 sejam abertas do proxy reverso para o diretor, bem como do pool de front-end e do servidor front-end. Além disso, deve haver comunicação SIP (Session Initiation Protocol) da interface interna do servidor de borda para o diretor e para o pool de front-end e o servidor front-end. O protocolo SIP usa SIP/MTLS/TCP 5061 do servidor de borda para o pool de front-ends e o servidor front-end. Uma regra que permita a comunicação SIP/MTLS/TCP 5061 do diretor, do pool de front-ends e do servidor front-end para a interface interna do servidor de borda também deve ser criada.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>Portas e protocolos de director único para definições de firewall

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/protocolo/TCP ou UDP/porta</th>
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interface interna de proxy inversa</p></td>
<td><p>Diretor</p></td>
<td><p>Inicialmente recebido pelo lado externo do proxy reverso, a comunicação é enviada para o diretor e serviços Web do servidor front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interface interna de proxy inversa</p></td>
<td><p>Diretor</p></td>
<td><p>Inicialmente recebido pelo lado externo do proxy reverso, a comunicação é enviada para o diretor e serviços Web do servidor front-end</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Diretor</p></td>
<td><p>Servidor front-end ou pool de front-end</p></td>
<td><p>Comunicação entre servidores entre o diretor e o servidor front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clientes internos</p></td>
<td><p>Serviços Web de diretor</p></td>
<td><p>O diretor fornece serviços Web para clientes internos e externos.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clientes internos</p></td>
<td><p>Serviços Web de diretor</p></td>
<td><p>O diretor fornece serviços Web para clientes internos e externos.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Diretor</p></td>
<td><p>Comunicação SIP do servidor de borda para o diretor e do servidor front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClasAgent. exe) e o conjunto de logs</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClasAgent. exe) e o conjunto de logs</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClasAgent. exe) e o conjunto de logs</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

