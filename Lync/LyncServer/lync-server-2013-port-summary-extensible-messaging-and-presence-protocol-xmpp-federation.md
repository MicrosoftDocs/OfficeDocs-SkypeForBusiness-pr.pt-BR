---
title: Resumo da porta – Federação do protocolo de presença e de mensagens extensíveis (XMPP)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b36a74393a8c61d5281bb009d212ee0bb12cf0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Resumo de portas – Federação de protocolo de presença e mensagens extensíveis (XMPP) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

As portas e protocolos definidos para o proxy de protocolo de presença e mensagens extensível (XMPP) implantadas no servidor de borda permitem comunicações do parceiro federado do XMPP com o servidor de borda e também permite a comunicação do servidor de borda com o XMPP parceiro federado. Uma regra também é definida no firewall de face interna do servidor front-end ou do pool de front-ends para o servidor de borda ou o pool de bordas.

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Resumo de firewall para mensagens extensíveis e protocolo de presença


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP ou UDP/porta</th>
<th>Fonte (endereço IP)</th>
<th>Destino (endereço IP)</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP da interface do serviço de borda do Access</p></td>
<td><p>Porta de comunicação de servidor para servidor padrão para XMPP. Permite a comunicação com o servidor de borda XMPP o proxy de parceiros de XMPP federado</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Endereço IP da interface do serviço de borda do Access</p></td>
<td><p>Qualquer um</p></td>
<td><p>Porta de comunicação de servidor para servidor padrão para XMPP. Permite a comunicação do proxy do servidor de borda XMPP com parceiros do XMPP federado</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Qualquer um</p></td>
<td><p>IP de interface do servidor de borda interna</p></td>
<td><p>Tráfego de XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-end para o servidor de borda</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Exemplo de configuração de XMPP no Lync Server 2013 – federação XMPP com Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Gerenciar parceiros XMPP federados no Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

