---
title: Resumo de DNS-Federação de protocolo de presença e mensagens extensíveis (XMPP)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941996ea1167cf9baeee05567a00c71ea5ed4baa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Resumo de DNS-Federação de protocolo de presença e mensagens extensíveis (XMPP) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-04-08_

Para configurar o protocolo de presença e mensagens extensíveis (XMPP) para a sua implantação, crie dois registros DNS (sistema de nomes de domínio) em um servidor DNS externo que resolverá os registros para o serviço de borda de acesso do servidor de borda ou do pool de bordas.

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Resumo de DNS para o protocolo de mensagens extensíveis e de presença


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Local/tipo/porta</th>
<th>FQDN</th>
<th>Endereço IP/registro de host FQDN</th>
<th>Mapas para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5269 externo</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externa de proxy XMPP no serviço de borda do Access ou no pool de bordas. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync nos quais o contato com contatos do XMPP é permitido pela configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao Usuário compatível com o Lync. Um domínio XMPP permitido também deve ser configurado na política de parceiros federados do XMPP. Consulte os tópicos em <strong>Consulte também</strong> para obter detalhes adicionais</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>xmpp.contoso.com (por exemplo)</p></td>
<td><p>Endereço IP do serviço de borda de acesso em seu servidor de borda ou em um pool de bordas que hospeda o proxy XMPP</p></td>
<td><p>Aponta para o serviço de borda de acesso ou o pool de bordas que hospeda o serviço de proxy XMPP. Geralmente, o registro SRV que você cria aponta para esse registro de host (A ou AAAA)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando federação de XMPP no Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  


[Determinar requisitios de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

