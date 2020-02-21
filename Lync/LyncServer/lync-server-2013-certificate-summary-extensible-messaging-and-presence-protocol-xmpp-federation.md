---
title: 'Lync Server 2013: Resumo de certificado-Federação de protocolo de presença e Unificação de mensagens (XMPP)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45758175a04bad0cc673242087c0a4751c1b01bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Resumo de certificado-Federação de XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-23_

Os requisitos de certificado para ativar e estabelecer comunicações com mensagens extensíveis e parceiros de protocolo de presença (XMPP) requerem o registro adicional dos seus domínios XMPP. O registro incluído no certificado como um nome alternativo da entidade (SAN) será o domínio que pode participar das comunicações XMPP. O domínio pode ser o domínio no nível raiz (por exemplo, contoso.com) se você deseja habilitar XMPP para o domínio inteiro ou pode ser determinados domínios filho (por exemplo, corp.contoso.com, finance.contoso.com) se estiver habilitando XMPP para um subconjunto de usuários.

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Resumo do certificado para o protocolo Extensible Messaging and Presence


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nome da entidade</th>
<th>Nomes alternativos de entidade (SAN)/Ordem</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Atribuir ao serviço de borda de acesso do servidor de borda ou do pool de borda</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>As três primeiras entradas de SAN são as entradas de SAN normais para um servidor de borda completo. A contoso.com é a entrada exigida para federação com o parceiro XMPP no nível de domínio raiz. Essa entrada permitirá que o XMPP todos os domínios com o sufixo contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Exemplo de configuração de XMPP no Lync Server 2013 – Federação do XMPP com Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Planejar certificados de servidor de borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  


[Configurar certificados de borda para o Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Request-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

