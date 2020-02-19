---
title: 'Lync Server 2013: Resumo de porta-diretor único'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8515785f66101df3af0d7d35de565ba344e2b91a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a>Resumo de porta-diretor único no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

Os requisitos de porta de firewall para um único diretor consistem nas portas usadas para estabelecer comunicação com o diretor da interface interna ou da rede de face interna do proxy reverso. O Microsoft Lync Server 2013, por padrão, espera que as portas HTTP/TCP 8080 e HTTPS/TCP 4443 sejam abertas do proxy reverso para o diretor, bem como o pool de front-ends e o servidor front-end. Além disso, deve haver comunicação SIP (Session Initiation Protocol) da interface interna do servidor de borda para o diretor e para o pool de front-ends e servidor de front-end. O protocolo SIP usa SIP/MTLS/TCP 5061 do servidor de borda para o pool de front-ends e servidor front-end. Uma regra que permite a comunicação SIP/MTLS/TCP 5061 do diretor, do pool de front-ends e do servidor front-end para a interface interna do servidor de borda também deve ser criada.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>Portas e protocolos de diretor único para definições de firewall

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/Protocolo/TCP ou UDP/Porta</th>
<th>Endereço IP de origem</th>
<th>Endereço IP de destino</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interface interna do proxy reverso</p></td>
<td><p>Be</p></td>
<td><p>Recebido inicialmente pelo lado externo do proxy reverso, a comunicação é enviada para os serviços Web diretor e servidor front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interface interna do proxy reverso</p></td>
<td><p>Be</p></td>
<td><p>Recebido inicialmente pelo lado externo do proxy reverso, a comunicação é enviada para os serviços Web diretor e servidor front-end</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Be</p></td>
<td><p>Servidor Front-End ou pool de Front-Ends</p></td>
<td><p>Comunicação entre servidores entre o diretor e o servidor front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clientes internos</p></td>
<td><p>Serviços Web diretor</p></td>
<td><p>O diretor fornece serviços Web para clientes internos e externos.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clientes internos</p></td>
<td><p>Serviços Web diretor</p></td>
<td><p>O diretor fornece serviços Web para clientes internos e externos.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/5061</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Be</p></td>
<td><p>Comunicação SIP do servidor de borda para o diretor e o servidor front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Comandos e coleção de registros do controlador (ClsController.exe) ou agente (ClasAgent.exe) de serviços centralizados de registro</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Comandos e coleção de registros do controlador (ClsController.exe) ou agente (ClasAgent.exe) de serviços centralizados de registro</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Comandos e coleção de registros do controlador (ClsController.exe) ou agente (ClasAgent.exe) de serviços centralizados de registro</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

