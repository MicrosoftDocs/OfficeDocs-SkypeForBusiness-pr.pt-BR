---
title: 'Lync Server 2013: Resumo de porta-pool de diretor em escala, balanceador de carga de hardware'
description: 'Lync Server 2013: Resumo de porta-pool de diretores em escala, balanceador de carga de hardware.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564547"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Resumo de porta-pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-21_

Os requisitos de porta de firewall para um pool de diretor consistem nas portas usadas para estabelecer comunicação com o diretor a partir da interface interna do servidor de borda ou da interface de volta interna do proxy reverso. O Microsoft Lync Server 2013, por padrão, espera que as portas HTTP/TCP 8080 e HTTPS/TCP 4443 sejam abertas do proxy reverso para o diretor, bem como o pool de front-ends e o servidor front-end. Além disso, deve haver comunicação SIP (Session Initiation Protocol) da interface interna do servidor de borda para o diretor e para o pool de front-ends e servidor de front-end. O protocolo SIP usa SIP/MTLS/TCP 5061 do servidor de borda para o pool de front-ends e servidor front-end. Uma regra que permite a comunicação SIP/MTLS/TCP 5061 do diretor, do pool de front-ends e do servidor front-end para a interface interna do servidor de borda também deve ser criada.

### <a name="director-ports-and-protocols-for-firewall-definitions"></a>Portas e protocolos do Diretor para definições de firewall

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
<td><p>VIP do balanceador de carga de hardware diretor</p></td>
<td><p>Recebido inicialmente pelo lado externo do proxy reverso, a comunicação é enviada para os serviços Web de VIP e servidor de front-end do diretor HLB</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interface interna do proxy reverso</p></td>
<td><p>VIP do balanceador de carga de hardware diretor</p></td>
<td><p>Recebido inicialmente pelo lado externo do proxy reverso, a comunicação é enviada para os serviços Web de VIP e servidor de front-end do diretor HLB</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Diretor</p></td>
<td><p>Servidor front-end ou pool de front-ends</p></td>
<td><p>Comunicação entre servidores entre o VIP HLB do diretor e os servidores front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clientes internos</p></td>
<td><p>VIP do balanceador de carga de hardware diretor</p></td>
<td><p>O diretor fornece serviços Web para clientes internos e externos.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clientes internos</p></td>
<td><p>VIP do balanceador de carga de hardware diretor</p></td>
<td><p>O diretor fornece serviços Web para clientes internos e externos.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/5061</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>VIP do balanceador de carga de hardware diretor</p></td>
<td><p>Comunicação SIP do servidor de borda para o diretor e servidores front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualquer</p></td>
<td><p>Diretor</p></td>
<td><p>Comandos de controlador de serviço de registro centralizado (ClsController.exe) ou agente (ClsAgent.exe) e coleção de logs</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualquer</p></td>
<td><p>Diretor</p></td>
<td><p>Comandos de controlador de serviço de registro centralizado (ClsController.exe) ou agente (ClsAgent.exe) e coleção de logs</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualquer</p></td>
<td><p>Diretor</p></td>
<td><p>Comandos de controlador de serviço de registro centralizado (ClsController.exe) ou agente (ClsAgent.exe) e coleção de logs</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

